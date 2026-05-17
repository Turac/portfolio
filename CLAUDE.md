# Portfolio — CLAUDE.md

## Stack

| Layer | Choice |
|---|---|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript (strict) |
| Styling | Tailwind CSS v3 |
| Component library | shadcn/ui (New York style, neutral base) |
| Icons | lucide-react |
| Dark mode | next-themes (`attribute="class"`, system default) |
| Font | Geist Sans / Geist Mono (Google Fonts) |

## Project structure

```
src/
  app/
    layout.tsx          # Root layout — ThemeProvider + Navbar shell
    page.tsx            # /
    work/page.tsx       # /work
    about/page.tsx      # /about
    contact/page.tsx    # /contact
    globals.css         # Tailwind + shadcn CSS variables (light + dark)
  components/
    navbar.tsx          # Sticky top nav with active-link highlighting
    theme-provider.tsx  # next-themes wrapper (client component)
    theme-toggle.tsx    # Sun/Moon icon button
    ui/                 # shadcn-generated primitives (do not edit by hand)
  lib/
    utils.ts            # cn() helper (clsx + tailwind-merge)
```

## Key conventions

- **App Router only** — no `pages/` directory.
- `"use client"` only where strictly needed (interactive components).
- shadcn components live in `src/components/ui/` and are generated via `npx shadcn add <component>`. Do not edit them directly; extend via composition.
- Max content width is `max-w-5xl` centered with `px-4` gutter — keep this consistent across all pages.
- Dark mode class is toggled on `<html>` by next-themes; CSS variables in `globals.css` handle the palette swap.

## Common commands

```bash
npm run dev       # start dev server (localhost:3000)
npm run build     # production build
npm run lint      # ESLint
npx shadcn add <component>   # add a shadcn/ui component
```
