# NovaStack Landing

Production-grade marketing site for NovaStack AI, built with Next.js App Router, React, TypeScript, and Tailwind CSS.

This repository delivers a modular, section-based landing experience focused on product narrative, technical credibility, and conversion.

## Table of Contents

- [Overview](#overview)
- [Core Capabilities](#core-capabilities)
- [Technology Stack](#technology-stack)
- [Architecture](#architecture)
- [Local Development](#local-development)
- [NPM Scripts](#npm-scripts)
- [Quality and Build Notes](#quality-and-build-notes)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Overview

NovaStack Landing is a component-driven web experience composed of reusable section modules. The page is assembled in a clear top-to-bottom narrative: navigation, hero, feature depth, technical proof points, developer relevance, and final call-to-action.

## Core Capabilities

- App Router-based composition with predictable structure
- Reusable UI primitives powered by Radix-based components
- Tailwind CSS v4 design system workflow
- Analytics instrumentation via Vercel Analytics
- Font stack that combines readability and technical brand character
- Animated ASCII visual components for distinctive identity

## Technology Stack

| Layer | Technology |
| --- | --- |
| Framework | Next.js 16 |
| UI Runtime | React 19 |
| Language | TypeScript 5 |
| Styling | Tailwind CSS 4 |
| UI Primitives | Radix UI |
| Icons | Lucide React |
| Forms/Validation | React Hook Form + Zod |
| Analytics | @vercel/analytics |

## Architecture

```text
app/
  layout.tsx              # Metadata, fonts, root shell, analytics
  page.tsx                # Landing page composition entrypoint
  globals.css             # Global styles for app layer
components/
  landing/                # Marketing sections and ASCII visual modules
  ui/                     # Shared UI primitives
hooks/                    # Shared client hooks
lib/
  utils.ts                # Generic utility helpers
public/                   # Static assets (icons, images)
styles/
  globals.css             # Additional global style definitions
```

## Local Development

### Prerequisites

- Node.js 20 or newer
- pnpm 9 or newer

### Install Dependencies

```bash
pnpm install
```

### Start Development Server

```bash
pnpm dev
```

Application URL: http://localhost:3000

## NPM Scripts

| Command | Purpose |
| --- | --- |
| `pnpm dev` | Start Next.js development server |
| `pnpm build` | Create production build |
| `pnpm start` | Run production server |
| `pnpm lint` | Run ESLint across the codebase |

## Quality and Build Notes

Current build behavior is defined in `next.config.mjs`:

- `typescript.ignoreBuildErrors` is set to `true`
- `images.unoptimized` is set to `true`

Implications:

- Production builds currently do not fail on TypeScript errors
- Next.js image optimization pipeline is bypassed

Recommendation for stricter production quality:

1. Set `typescript.ignoreBuildErrors` to `false`
2. Re-enable image optimization if deployment target supports it
3. Add a CI gate that runs `pnpm lint` and `pnpm build`

## Deployment

### Vercel (Recommended)

1. Import the repository into Vercel.
2. Keep the default Next.js build settings.
3. Deploy.

### Self-Hosted / Manual

```bash
pnpm build
pnpm start
```

## Contributing

1. Create a branch from `main`.
2. Keep changes scoped to a single concern.
3. Validate locally with lint and build checks.
4. Open a pull request with a concise technical summary.

## License

This repository is currently private. Add a formal license before public distribution.
