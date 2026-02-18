# Performance Optimization Deep Dive

> Comprehensive guide to optimizing web performance for AI-assisted development.

## Overview

Performance is critical for user experience, SEO, and conversion rates. This guide covers deep optimization strategies for vibecoding projects.

## Core Web Vitals Mastery

### Largest Contentful Paint (LCP)

LCP measures how quickly the largest content element renders. Target: under 2.5 seconds.

#### Image Optimization

**WebP/AVIF Conversion:**

```javascript
// Using sharp for image optimization
const sharp = require('sharp');

async function optimizeImage(inputPath, outputPath) {
  await sharp(inputPath)
    .webp({ quality: 80 })
    .toFile(outputPath);
}

// Batch convert images
for (const file of images) {
  await optimizeImage(file, `dist/${file.name}.webp`);
}
```

**Proper Sizing Strategy:**

```html
<!-- Responsive images with srcset -->
<img
  src="hero-800.webp"
  srcset="hero-400.webp 400w,
          hero-800.webp 800w,
          hero-1200.webp 1200w"
  sizes="(max-width: 600px) 400px,
         (max-width: 1200px) 800px,
         1200px"
  alt="Hero image"
  loading="eager"
  fetchpriority="high"
/>
```

**Image Component (AI Prompt):**

```
Create a responsive Next.js Image component that:
- Automatically serves WebP/AVIF based on browser support
- Includes blur placeholder for LCP optimization
- Uses proper srcset for different viewport sizes
- Has loading="eager" for above-fold images
- Implements proper lazy loading for below-fold images
```

#### Critical CSS Extraction

**Inline Critical CSS:**

```javascript
// Using critical to extract and inline CSS
const critical = require('critical');

critical.generate({
  base: 'dist/',
  src: 'index.html',
  target: 'index-critical.html',
  inline: true,
  dimensions: [{
    height: 667,
    width: 375
  }, {
    height: 900,
    width: 1440
  }]
});
```

**Vite Plugin for Critical CSS:**

```javascript
// vite.config.js
import { defineConfig } from 'vite';
import criticalPlugin from 'vite-plugin-critical';

export default defineConfig({
  plugins: [
    criticalPlugin({
      criticalCss: {
        inline: true,
        dimensions: [{ width: 375, height: 667 }]
      }
    })
  ]
});
```

#### Font Optimization

**Font Loading Strategy:**

```css
/* Font display swap for faster text display */
@font-face {
  font-family: 'Inter';
  src: url('/fonts/inter-var.woff2') format('woff2');
  font-display: swap;
  font-weight: 100 900;
}

/* Preload critical fonts */
<link
  rel="preload"
  href="/fonts/inter-var.woff2"
  as="font"
  type="font/woff2"
  crossorigin
/>
```

#### CDN Configuration

**Cloudflare Page Rules:**

```yaml
# Page Rules for Performance
- url: "*.{jpg,jpeg,png,gif,webp,avif,svg}"
  cache_level: "cache_everything"
  browser_cache_ttl: 604800
  polish: "webp"
  auto_minify: "html css js"

- url: "*.{js,css}"
  cache_level: "cache_everything"
  browser_cache_ttl: 604800
  minify: "js css"
```

### Interaction to Next Paint (INP)

INP measures responsiveness. Target: under 200ms.

#### JavaScript Task Scheduling

**Breaking Up Long Tasks:**

```javascript
// BAD: Long-running task blocks main thread
function processLargeArray() {
  const items = getThousandItems();
  for (let item of items) {
    heavyProcessing(item);
  }
}

// GOOD: Break into chunks with yield
async function processLargeArray() {
  const items = getThousandItems();
  const chunkSize = 50;

  for (let i = 0; i < items.length; i += chunkSize) {
    const chunk = items.slice(i, i + chunkSize);
    await Promise.all(chunk.map(heavyProcessing));
    // Yield to main thread
    await new Promise(resolve => setTimeout(resolve, 0));
  }
}
```

**Using requestIdleCallback:**

```javascript
// Process non-critical tasks during idle time
function processAnalytics() {
  const tasks = getAnalyticsTasks();

  const processChunk = (deadline) => {
    while (tasks.length > 0 && deadline.timeRemaining() > 10) {
      const task = tasks.shift();
      task();
    }

    if (tasks.length > 0) {
      requestIdleCallback(processChunk);
    }
  };

  requestIdleCallback(processChunk);
}
```

#### Web Workers

**Offloading Heavy Computation:**

```javascript
// worker.js
self.onmessage = async (e) => {
  const { data, type } = e.data;

  switch (type) {
    case 'process':
      const result = await heavyComputation(data);
      self.postMessage({ type: 'result', payload: result });
      break;
  }
};

// main.js
const worker = new Worker('worker.js');

function computeExpensive(data) {
  return new Promise((resolve) => {
    worker.onmessage = (e) => resolve(e.data.payload);
    worker.postMessage({ type: 'process', data });
  });
}
```

### Cumulative Layout Shift (CLS)

CLS measures visual stability. Target: under 0.1.

#### Aspect Ratio Boxes

**Preventing Image Layout Shift:**

```css
/* Aspect ratio containers */
.image-container {
  aspect-ratio: 16 / 9;
  overflow: hidden;
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

**CSS Aspect Ratio for Ads/Embeds:**

```css
.ad-placeholder {
  min-height: 250px;
  background: #f0f0f0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.video-container {
  aspect-ratio: 16 / 9;
  position: relative;
}

.video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

#### Font Loading Strategies

**Font Subsetting and Preloading:**

```html
<!-- Preload critical font weights only -->
<link
  rel="preload"
  href="/fonts/inter-latin-400-normal.woff2"
  as="font"
  type="font/woff2"
  crossorigin
  font-weight="400"
/>

<!-- Use font-display: optional to avoid layout shift -->
<style>
  @font-face {
    font-family: 'Inter';
    font-display: optional;
    /* ... */
  }
</style>
```

## Bundle Size Optimization

### Tree-Shaking Deep Dive

**Enabling Tree-Shaking in Vite/Webpack:**

```javascript
// vite.config.js
export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
          utils: ['lodash', 'date-fns']
        }
      }
    },
    treeShaking: true
  }
});
```

**ES Modules for Better Tree-Shaking:**

```javascript
// GOOD: Named imports enable tree-shaking
import { debounce, throttle } from 'lodash-es';

// BAD: Default import includes all of lodash
import _ from 'lodash';
```

### Dynamic Imports Strategy

**Code Splitting:**

```javascript
// Dynamic import for routes
const Home = lazy(() => import('./pages/Home'));
const About = lazy(() => import('./pages/About'));
const Dashboard = lazy(() => import('./pages/Dashboard'));

// Suspense fallback
function App() {
  return (
    <Suspense fallback={<Loading />}>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/dashboard" element={<Dashboard />} />
      </Routes>
    </Suspense>
  );
}
```

**On-Demand Loading:**

```javascript
// Load heavy components on interaction
function SearchModal() {
  const [isOpen, setIsOpen] = useState(false);
  const [SearchResults, setSearchResults] = useState(null);

  const openSearch = async () => {
    setIsOpen(true);
    const module = await import('./SearchResults');
    setSearchResults(module.default);
  };

  return (
    <>
      <button onClick={openSearch}>Search</button>
      {isOpen && SearchResults && <SearchResults />}
    </>
  );
}
```

### Bundle Analysis

**Using Rollup Visualizer:**

```javascript
// vite.config.js
import { visualizer } from 'rollup-plugin-visualizer';

export default defineConfig({
  plugins: [
    visualizer({
      filename: 'dist/bundle-analysis.html',
      open: true
    })
  ]
});
```

**Bundle Budget Enforcement:**

```javascript
// Next.js next.config.js
module.exports = {
  compiler: {
    removeConsole: process.env.NODE_ENV === 'production'
  },
  webpack: (config) => {
    config.performance.budgets = [
      {
        asset: '**/*.js',
        maxSize: 244 * 1024, // 244KB
        maxEntrypointSize: 244 * 1024
      }
    ];
    return config;
  }
};
```

## Caching Strategies

### Browser Caching

**Cache-Control Headers:**

```javascript
// Express.js middleware
app.use((req, res, next) => {
  // Static assets - cache for 1 year
  if (req.path.match(/\.(js|css|woff2|ico)$/)) {
    res.setHeader('Cache-Control', 'public, max-age=31536000, immutable');
  }
  // HTML - no cache
  else if (req.path.endsWith('.html')) {
    res.setHeader('Cache-Control', 'no-store, must-revalidate');
  }
  // API responses
  else {
    res.setHeader('Cache-Control', 'public, max-age=60, s-maxage=300');
  }
  next();
});
```

### Service Worker Caching

**Service Worker Strategies:**

```javascript
// sw.js - Stale-while-revalidate
self.addEventListener('fetch', (event) => {
  event.respondWith(
    caches.open('static-v1').then(async (cache) => {
      const cached = await cache.match(event.request);
      const fetchPromise = fetch(event.request).then((response) => {
        cache.put(event.request, response.clone());
        return response;
      });

      return cached || fetchPromise;
    })
  );
});
```

**Workbox Configuration:**

```javascript
// workbox-config.js
module.exports = {
  globDirectory: 'dist/',
  globPatterns: [
    '**/*.{html,js,css,png,svg,ico,woff2}'
  ],
  swDest: 'dist/sw.js',
  runtimeCaching: [
    {
      urlPattern: /^https:\/\/api\./i,
      handler: 'NetworkFirst',
      options: {
        cacheName: 'api-cache',
        expiration: {
          maxEntries: 50,
          maxAgeSeconds: 60 * 60 * 24 // 24 hours
        },
        cacheableResponse: {
          statuses: [0, 200]
        }
      }
    }
  ]
};
```

### CDN Edge Caching

**Vercel Edge Config:**

```javascript
// middleware.ts
import { NextResponse } from 'next/server';
import type { NextRequest } from 'next/server';

export function middleware(request: NextRequest) {
  // Set edge cache headers
  const response = NextResponse.next();
  response.headers.set(
    'Cache-Control',
    'public, max-age=0, s-maxage=3600'
  );
  return response;
}

export const config = {
  matcher: [
    '/api/:path*',
    '/static/:path*'
  ]
};
```

## Performance Monitoring

### Lighthouse CI Setup

**GitHub Action for Lighthouse:**

```yaml
# .github/workflows/lighthouse.yml
name: Lighthouse CI

on: [push]

jobs:
  lighthouse:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install dependencies
        run: npm ci

      - name: Build
        run: npm run build

      - name: Run Lighthouse CI
        uses: treosh/lighthouse-ci-action@v10
        with:
          urls: |
            https://example.com
          budgetPath: ./lighthouse-budget.json
          uploadArtifacts: true
```

**Lighthouse Budget:**

```json
// lighthouse-budget.json
{
  "budgets": [
    {
      "resourceSizes": [
        {
          "resourceType": "total",
          "budget": 170
        },
        {
          "resourceType": "script",
          "budget": 50
        },
        {
          "resourceType": "css",
          "budget": 15
        }
      ],
      "resourceCounts": [
        {
          "resourceType": "third-party",
          "budget": 10
        }
      ]
    }
  ]
}
```

### Real User Monitoring (RUM)

**Using Web Vitals Library:**

```javascript
import { onCLS, onFID, onLCP, onFCP, onTTFB } from 'web-vitals';

function sendToAnalytics({ name, delta, id }) {
  // Send to your analytics service
  gtag('event', name, {
    event_category: 'Web Vitals',
    event_label: id,
    value: Math.round(name === 'CLS' ? delta * 1000 : delta),
    non_interaction: true
  });
}

onCLS(sendToAnalytics);
onFID(sendToAnalytics);
onLCP(sendToAnalytics);
onFCP(sendToAnalytics);
onTTFB(sendToAnalytics);
```

### Performance Budgets

**Core Web Vitals Targets:**

| Metric | Good | Needs Improvement | Poor |
|--------|------|-------------------|------|
| LCP | ≤2.5s | ≤4.0s | >4.0s |
| INP | ≤200ms | ≤500ms | >500ms |
| CLS | ≤0.1 | ≤0.25 | >0.25 |

**Setting Up Alerts:**

```javascript
// Performance monitoring script
const PERFORMANCE_THRESHOLDS = {
  LCP: 2500,
  INP: 200,
  CLS: 0.1
};

function checkPerformanceMetric(metric, value) {
  if (value > PERFORMANCE_THRESHOLDS[metric]) {
    // Alert to monitoring service
    alertService.send({
      type: 'performance_degradation',
      metric,
      value,
      url: window.location.href
    });
  }
}
```

---

**Related Documents:**
- [UX Deep Dive](ux-deep-dive.md)
- [Security Deep Dive](security-deep-dive.md)
- [Testing Deep Dive](testing-deep-dive.md)
- [Delivery System README](../05-delivery-system/README.md)
