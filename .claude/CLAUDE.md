# hatice-showcase

Single-page presentation for hatice — an autonomous issue orchestration system.

## Tech Stack
- Single `index.html` file — ALL changes go here
- Tailwind CSS via CDN (already configured with custom theme)
- No build tools, no bundler, no npm

## Frontend Design Skill

You MUST follow these guidelines for all visual work:

### Design Thinking
Before coding, commit to a BOLD aesthetic direction:
- **Tone**: Luxury/refined editorial aesthetic — warm, organic, intentional
- **Differentiation**: This should feel like a hand-crafted design studio piece, not generic AI output
- **One memorable thing**: The seamless blend of warm organic textures with precise technical content

### Aesthetics Rules
- **Typography**: Use the fonts already configured (Instrument Serif for display, DM Sans for body, JetBrains Mono for code). These are distinctive, characterful choices. Pair them with confidence — large serif headings, light sans body.
- **Color & Theme**: Commit to the warm sand palette. Dominant warm tones with sharp ember/sage accents. No timid, evenly-distributed palettes.
- **Motion**: CSS-only animations. Focus on high-impact moments: staggered fade-in reveals on page load (animation-delay), subtle hover states. One well-orchestrated entrance > scattered micro-interactions.
- **Spatial Composition**: Asymmetry welcome. Generous negative space. Grid-breaking hero elements. Overlap where it creates depth.
- **Backgrounds & Visual Details**: Grain texture overlay on body. Gradient meshes. Layered transparencies (glassmorphism cards). Decorative geometric accents.

### NEVER
- Use generic AI aesthetics (Inter, Roboto, purple gradients, cookie-cutter layouts)
- Use dark mode or dark backgrounds
- Use neon/cyber colors
- Add npm dependencies or extra files
- Make it look like every other AI-generated landing page

## Design System — Claude Code Aesthetic

### Colors (already in tailwind.config)
- **Background:** `bg-sand-50` (warm cream #faf9f6)
- **Cards:** `bg-white/60 backdrop-blur-sm border border-sand-200`
- **Text primary:** `text-stone-800`
- **Text secondary:** `text-stone-400`
- **Accent warm:** `text-ember-500` (#b5614a)
- **Accent green:** `text-sage-500` (#5f7d55)

### Typography
- **Headings:** `font-serif` (Instrument Serif) — elegant, large sizes (text-5xl+)
- **Body:** `font-sans` (DM Sans) — clean, font-light weight
- **Code:** `font-mono` (JetBrains Mono)

### Layout Principles
- Generous whitespace — sections use `py-24 px-6` minimum
- Max content width: `max-w-5xl mx-auto`
- Cards: `rounded-2xl p-8 shadow-sm`
- Staggered fade-in animations via CSS `@keyframes`

### CSS Techniques to Use
```css
/* Grain overlay on body */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  opacity: 0.03;
  background-image: url("data:image/svg+xml,..."); /* noise pattern */
  pointer-events: none;
  z-index: 50;
}

/* Staggered fade-in */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.fade-up { animation: fadeUp 0.8s ease-out both; }
.fade-up-1 { animation-delay: 0.1s; }
.fade-up-2 { animation-delay: 0.2s; }
```

## Architecture Reference

```
Linear/GitHub → hatice polls → dispatches Claude agents → isolated workspaces → code committed
```

Key components: Orchestrator, AgentRunner (Claude SDK), EventBus, Supervisor, Workspace, TrackerAdapter

## How to preview
```bash
npx live-server --port=3000
```
