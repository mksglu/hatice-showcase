# hatice-showcase

Single-page presentation for hatice — an autonomous issue orchestration system.

## Tech Stack
- Single `index.html` file — ALL changes go here
- Tailwind CSS via CDN (already configured with custom theme)
- No build tools, no bundler, no npm

## Design System — Claude Code Aesthetic

Follow this design language strictly:

### Colors (already in tailwind.config)
- **Background:** `bg-sand-50` (warm cream #faf9f6)
- **Cards:** `bg-white/60 backdrop-blur-sm border border-sand-200`
- **Text primary:** `text-stone-800`
- **Text secondary:** `text-stone-400`
- **Accent warm:** `text-ember-500` (#b5614a)
- **Accent green:** `text-sage-500` (#5f7d55)

### Typography
- **Headings:** `font-serif` (Instrument Serif) — elegant, large
- **Body:** `font-sans` (DM Sans) — clean, light weight
- **Code:** `font-mono` (JetBrains Mono)

### Layout Principles
- Generous whitespace — sections use `py-24 px-6` minimum
- Max content width: `max-w-5xl mx-auto`
- Cards: `rounded-2xl p-8 shadow-sm`
- Subtle grain/texture overlays welcome
- Staggered fade-in animations via CSS

### Do NOT
- Use dark mode or dark backgrounds
- Use neon/cyber colors
- Use generic sans-serif headings
- Add npm dependencies or extra files

## Architecture Reference

```
Linear/GitHub → hatice polls → dispatches Claude agents → isolated workspaces → code committed
```

Key components: Orchestrator, AgentRunner (Claude SDK), EventBus, Supervisor, Workspace, TrackerAdapter

## How to preview
```bash
npx live-server --port=3000
```
