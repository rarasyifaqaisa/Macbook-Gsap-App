# MacBook GSAP App

A small React + Vite demo that showcases a 3D MacBook model with GSAP-powered scroll animations, video/textured screen sync, and interactive product controls.

## Quick links
- Project entry: [index.html](index.html)  
- React entry: [src/main.jsx](src/main.jsx)  
- App root component: [`App`](src/App.jsx) — [src/App.jsx](src/App.jsx)  
- Tailwind / global styles: [src/index.css](src/index.css)  
- Vite config: [vite.config.js](vite.config.js)  
- Scripts & deps: [package.json](package.json)

## Key components & stores
- Product & models
  - Product viewer: [src/components/ProductViewer.jsx](src/components/ProductViewer.jsx)  
  - Model switcher: [`ModelSwitcher`](src/components/three/ModelSwitcher.jsx) — [src/components/three/ModelSwitcher.jsx](src/components/three/ModelSwitcher.jsx)  
  - 3D models:
    - `MacbookModel` (video-textured): [src/components/models/Macbook.jsx](src/components/models/Macbook.jsx)  
    - `MacbookModel16`: [src/components/models/Macbook-16.jsx](src/components/models/Macbook-16.jsx)  
    - `MacbookModel14`: [src/components/models/Macbook-14.jsx](src/components/models/Macbook-14.jsx)  
  - Studio lights for the scene: [src/components/three/StudioLights.jsx](src/components/three/StudioLights.jsx)

- UI & layout
  - Navigation: [src/components/Navbar.jsx](src/components/Navbar.jsx)  
  - Hero: [src/components/Hero.jsx](src/components/Hero.jsx)  
  - Showcase: [src/components/Showcase.jsx](src/components/Showcase.jsx)  
  - Performance: [src/components/Performance.jsx](src/components/Performance.jsx)  
  - Features: [src/components/Features.jsx](src/components/Features.jsx)  
  - Highlights: [src/components/Highlights.jsx](src/components/Highlights.jsx)  
  - Footer: [src/components/Footer.jsx](src/components/Footer.jsx)

- State & constants
  - Global store: [`useMacbookStore`](src/store/index.js) — [src/store/index.js](src/store/index.js)  
  - Constants (nav links, features, performance images, feature sequence): [`featureSequence`, `features`, `performanceImages`](src/constants/index.js) — [src/constants/index.js](src/constants/index.js)

## Features
- 3D MacBook preview using [@react-three/fiber] and [drei] with multiple model variants.
- Screen video/textures synced with scroll via GSAP timelines: see [`featureSequence`](src/constants/index.js) and [`useMacbookStore`](src/store/index.js).
- Scroll-based animations with GSAP ScrollTrigger (registered in [src/App.jsx](src/App.jsx)).
- Responsive layout and controls with Tailwind + custom utilities in [src/index.css](src/index.css).

## Requirements
- Node.js (16+ recommended)
- npm (or yarn/pnpm)

## Install & run
```bash
# markdown
npm install
npm run dev
```

Available scripts (from [package.json](package.json)):
- npm run dev — start dev server (Vite)
- npm run build — build for production
- npm run preview — preview built site
- npm run lint — run eslint

## Assets & models
- Public assets are in the `public/` folder (images, videos, fonts, models). Notable files:
  - 3D models: public/models/*.glb (used by [useGLTF.preload] calls in model files)
  - Videos: public/videos/*.mp4 (referenced by [`featureSequence`](src/constants/index.js) and components)
  - Images: public/*.png, .svg used across components

## Notes & debugging
- GSAP ScrollTrigger is registered in [src/App.jsx](src/App.jsx). If animations don't fire, ensure `gsap.registerPlugin(ScrollTrigger)` is executed before components mount.
- The 3D screen uses a video texture in [src/components/models/Macbook.jsx](src/components/models/Macbook.jsx). If cross-origin issues appear, check video `crossOrigin` attributes and server headers.
- Color/scale/texture are managed by [`useMacbookStore`](src/store/index.js). Change via UI in [src/components/ProductViewer.jsx](src/components/ProductViewer.jsx).

## Contributing
- Fixes, improvements and PRs welcome. Keep code consistent with existing style (React + functional components, Zustand store, GSAP usage).

## License
This repository is a demo/template. See included asset licenses (model source and fonts) inside the project if redistributing.
