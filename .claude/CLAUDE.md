# hatice-showcase

Single-page presentation for hatice — an autonomous issue orchestration system.

## Tech Stack
- Single `index.html` file — ALL changes go here
- Tailwind CSS via CDN (already configured with custom theme)
- No build tools, no bundler, no npm

## Design System — Claude Code Aesthetic (STRICT)

This design system is extracted from claude.ai's actual production design. Follow it exactly.

### Core Principle
**Warm minimalism with editorial typographic authority.** Nothing flashy. Nothing generic. Every element is intentional, spacious, and refined. Think high-end magazine layout, not SaaS landing page.

### Background & Surface
- Page background: `bg-sand-50` (#FAF9F5 — warm off-white, like quality paper)
- Cards/containers: NO shadows, NO backdrop-blur, NO glassmorphism. Use flat layout with generous spacing instead of card frames
- When a container is needed: `bg-sand-100` (#F5F0E8) with hairline border `border border-sand-200/50`
- NO gradients on content surfaces
- NO grain texture overlay

### Typography
- **Display headings:** `font-serif` (Instrument Serif) with `font-light` — the lighter the better, editorial feel
- **Body text:** `font-sans` (DM Sans) `font-light`
- **Code:** `font-mono` (JetBrains Mono) `text-sm`
- **Heading sizes:** Go big. text-6xl to text-8xl for main headings. text-4xl to text-5xl for section headings.

### Colors
- **Text primary:** `text-stone-900` — near-black with warm undertone, NEVER pure black
- **Text secondary:** `text-stone-400` — medium warm gray
- **Brand accent:** `text-ember-500` (#B5614A — terracotta/clay) — use sparingly for key highlights
- **Secondary accent:** `text-sage-500` (#5F7D55) — for success/active states only
- **Borders:** `border-stone-200/30` — hairline, barely visible

### Buttons
- Primary: `bg-stone-900 text-sand-50 rounded-lg px-6 py-2.5` — near-black, warm
- Secondary: `border border-stone-300/30 rounded-lg px-6 py-2.5` — hairline outline
- NO gradient buttons, NO colored buttons

### Layout
- Ultra-generous whitespace: sections use `py-32 px-6` minimum
- Content width: `max-w-5xl mx-auto`
- Full viewport hero: `min-h-screen`
- Let content breathe — when in doubt, add more space

### Animation
- CSS-only, subtle
- `@keyframes fadeUp` for entrance: `opacity 0→1, translateY(20px→0)`, 0.8s ease-out
- Staggered delays: 0.1s increments
- NO bouncing, NO spinning, NO pulsing
- Transitions on hover: `transition-all duration-300`

### Footer
- **Black background** `bg-stone-950` — high contrast against warm body
- Text in `text-stone-400`
- Creates a strong editorial bookend

### NEVER DO
- Glassmorphism (backdrop-blur, bg-white/60)
- Grain/noise texture overlays
- Neon or cyber colors
- Dark mode body
- Heavy shadows (shadow-lg, shadow-xl)
- Generic SaaS hero patterns
- Gradient backgrounds on sections
- Emojis as icons
- Inter, Roboto, or any generic font

## Architecture Reference

```
Linear/GitHub → hatice polls → dispatches Claude agents → isolated workspaces → code committed
```

Key components: Orchestrator, AgentRunner (Claude SDK), EventBus, Supervisor, Workspace, TrackerAdapter

## How to preview
```bash
npx live-server --port=3000
```
