# next-spa-strict

A minimal example demonstrating how to run Next.js strictly as a client-side Single Page Application (SPA) using hash-based routing.

## Overview

Instead of relying on Next.js multi-page transitions or file-system-based page routing, this project handles routing entirely on the client within a single page using a custom React context (`SPARouterContext`) driven by `window.location.hash`.

### Key Components

- **`context/spaRouter.js`**: Provides `SPARouterProvider` and the `useSPARouter` hook. Listens to `hashchange` events to track the current path, exposes a `navigate` function, and includes a `Route` component for conditional rendering.
- **`app/layout.js`**: Root layout that wraps the application in `SPARouterProvider`.
- **`app/page.js`**: The single page entry point that renders navigation controls and swaps view content based on the active hash path.
- **Material-UI (MUI)**: Used for interface components and layout styling.

## Project Structure

```
next-spa-strict/
├── nextjs-strict-spa-app/
│   ├── app/
│   │   ├── layout.js       # Root layout wrapping children in SPARouterProvider
│   │   ├── page.js         # Main SPA view with dynamic content switching
│   │   └── favicon.ico
│   ├── context/
│   │   └── spaRouter.js    # Hash-based SPA routing context and hook
│   ├── jsconfig.json       # Path alias configuration
│   ├── next.config.mjs     # Next.js configuration
│   └── package.json        # Dependencies and scripts
├── renovate.json           # Renovate dependency configuration
└── README.md
```

## Getting Started

1. Navigate to the application directory:
   ```bash
   cd nextjs-strict-spa-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

Inside the `nextjs-strict-spa-app` directory:

- `npm run dev`: Runs the development server with Turbopack.
- `npm run build`: Creates an optimized production build.
- `npm run start`: Starts the production server.
- `npm run lint`: Runs ESLint to check for code issues.
