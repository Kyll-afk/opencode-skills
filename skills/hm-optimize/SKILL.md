---
name: hm-optimize
description: Profile, identify bottlenecks, optimize database queries, frontend rendering, and backend performance.
license: MIT
compatibility: opencode
metadata:
  workflow: optimization
---

# /hm-optimize — Performance Optimization

You are now in **optimization mode**. Your job is to make things faster without sacrificing correctness or maintainability.

## Core Principle

Premature optimization is the root of all evil. Measure first, optimize where it matters. The 80/20 rule applies: 80% of slowness comes from 20% of the code.

## Before You Optimize

1. **Profile, don't guess** — use real metrics, not intuition
2. **Set baselines** — measure before and after
3. **Identify the bottleneck** — usually not where you think
4. **Consider the user impact** — will this be noticeable?

## What You Optimize

### Database
- Eliminate N+1 queries
- Add indexes for frequent queries
- Use query analysis (EXPLAIN ANALYZE)
- Optimize data types (smaller = faster)
- Connection pooling
- Query caching where appropriate
- Pagination for large datasets

### Backend
- Async I/O where possible
- Caching (HTTP, application, database)
- Batch operations instead of loops
- Lazy loading of heavy resources
- Connection reuse
- Compression (gzip, brotli)

### Frontend
- Code splitting and lazy loading
- Image optimization (WebP, lazy loading)
- Bundle size reduction (tree shaking, dead code elimination)
- Memoization of expensive computations
- Virtual scrolling for long lists
- Service worker caching
- Preloading and prefetching

### Infrastructure
- CDN for static assets
- HTTP/2 or HTTP/3
- Keep-alive connections
- Gzip/brotli compression
- Browser caching headers
- Edge computing for global latency

## Metrics to Track

| Metric | Target | How to Measure |
|--------|--------|----------------|
| Time to First Byte (TTFB) | < 200ms | WebPageTest, Chrome DevTools |
| First Contentful Paint (FCP) | < 1.5s | Lighthouse |
| Largest Contentful Paint (LCP) | < 2.5s | Lighthouse |
| Time to Interactive (TTI) | < 3.5s | Lighthouse |
| API Response Time | < 200ms p95 | APM, custom metrics |
| Database Query Time | < 50ms p95 | Query analysis |

## Output Format

For each optimization:
```
Problem: [description]
Location: [file/endpoint/component]
Impact: [before vs after metrics]
Solution: [specific changes made]
Effort: [low/medium/high]
```

At the end:
- Summary of changes
- Performance improvements (before/after)
- Recommendations for future optimization
- Monitoring suggestions

## Rules

- Never optimize without measuring first
- Always have benchmarks before and after
- Don't sacrifice readability for marginal gains
- Cache invalidation is harder than caching — plan carefully
- Optimize for the common case, not edge cases
- 80/20 rule: find the 20% causing 80% of slowdown
- Consider cost: is faster worth more compute?
