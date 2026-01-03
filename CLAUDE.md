# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Next.js 16.1.1 project using React 19.2.3 with TypeScript, configured with:
- **App Router** (not Pages Router)
- **Tailwind CSS v4** (configured via PostCSS plugin)
- **shadcn/ui** ("new-york" style variant with RSC support)
- **Geist fonts** (Geist and Geist Mono from next/font/google)

## Development Commands

```bash
# Start development server (http://localhost:3000)
npm run dev

# Production build
npm run build

# Start production server
npm start

# Lint code
npm run lint
```

## Project Structure

```
app/
  layout.tsx    # Root layout with font configuration
  page.tsx      # Home page
  globals.css   # Global styles with Tailwind directives

lib/
  utils.ts      # Contains cn() utility for merging Tailwind classes

components/     # Does not exist yet (will be created when adding shadcn/ui components)
  ui/           # shadcn/ui components will go here
```

## Path Aliases

The project uses `@/*` to reference files from the project root:
- `@/components` → `./components`
- `@/lib` → `./lib`
- `@/ui` → `./components/ui`
- `@/hooks` → `./hooks`

## shadcn/ui Configuration

The project is configured for shadcn/ui with:
- Style variant: `new-york`
- RSC (React Server Components): enabled
- Base color: `neutral`
- CSS variables: enabled
- Icon library: `lucide-react`

When adding shadcn/ui components, use:
```bash
npx shadcn@latest add [component-name]
```

Components will be installed to `@/components/ui/[component-name].tsx`

## Tailwind CSS v4

This project uses Tailwind CSS v4 configured via PostCSS plugin (`@tailwindcss/postcss`), not a traditional `tailwind.config.js` file. Tailwind directives are in `app/globals.css`.

## TypeScript Configuration

- Strict mode enabled
- Path alias: `@/*` maps to project root
- Target: ES2017
- Module resolution: bundler
- JSX: react-jsx
