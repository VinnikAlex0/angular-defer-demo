# Angular @defer Performance Demo

A monorepo demonstrating the performance benefits of Angular's `@defer` directive for component lazy loading.

## Overview

This project compares two identical Angular applications:
- **before-defer**: Traditional eager loading approach
- **after-defer**: Optimized with `@defer` lazy loading

## Quick Start

```bash
# Install dependencies
npm install

# Run before-defer demo (localhost:4200)
npm run serve:before-defer

# Run after-defer demo (localhost:4201)  
npm run serve:after-defer
```

## Project Structure

```
angular-defer-demo/
├── projects/
│   ├── before-defer/          # Eager loading version
│   └── after-defer/           # @defer lazy loading version
├── package.json               # Run scripts
└── angular.json               # Workspace configuration
```

## Angular @defer Directive

The `@defer` directive enables declarative lazy loading of components, reducing initial bundle size and improving performance.

### Basic Syntax

```html
@defer (when idle) {
  <app-heavy-component />
} @placeholder {
  <div>Loading...</div>
}
```

### Available Triggers

- `when idle` - Load when browser is idle
- `on viewport` - Load when entering viewport
- `on interaction` - Load on user interaction
- `on timer(2000)` - Load after specified delay
- `on hover` - Load on hover

## Performance Benefits

| Metric | Before @defer | After @defer | Improvement |
|--------|---------------|--------------|-------------|
| Initial Bundle Size | Larger | Smaller | Reduced |
| First Contentful Paint | Slower | Faster | Improved |
| Time to Interactive | Longer | Shorter | Better UX |

## Technical Details

- **Angular 20.1.0** with latest features
- **Standalone components** architecture
- **New control flow** (`@if`, `@for`, `@defer`)
- **Server-Side Rendering** support

## Build Commands

```bash
# Build applications
npm run build:before-defer
npm run build:after-defer

# Run tests
npm run test:before-defer
npm run test:after-defer
```

## Demo Flow

1. Start both applications
2. Compare initial load performance
3. Demonstrate different @defer triggers
4. Show bundle size differences
5. Measure performance metrics

---

Built with Angular 20.1.0 | Standalone Components | SSR Ready
