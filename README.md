# ⚡ ZeroJS Blog

A modern, high-performance static blog built with [Astro](https://astro.build). Designed around the **Zero JavaScript** philosophy: ultra-lean, static-first delivery with 0kB client-side runtime overhead and 100/100 Core Web Vitals.

Repository: [https://github.com/DevTechMike-Coder/ZeroJs_Blog](https://github.com/DevTechMike-Coder/ZeroJs_Blog)

## ✨ Highlights

- ⚡ **Zero Client-Side JavaScript:** 0kB JS runtime shipped to readers for lightning-fast paints.
- 🎨 **Modern Dark Aesthetic:** Glassmorphic cards, custom gradient accents, and animated SVG micro-icons (CSS keyframes).
- 🔤 **Editorial Typography:** Beautiful typography, styled code blocks, callouts, and blockquotes.
- 🛡️ **Type-Safe Content Collections:** Markdown & MDX content validation with tags, hero images, and reading metadata.
- 📡 **Open Web Standards:** Native RSS feed (`/rss.xml`), sitemap (`/sitemap-index.xml`), and semantic HTML5.
- 🚀 **100/100 Performance:** Perfect Lighthouse scores out of the box.

## 🚀 Project Structure

```text
├── public/
├── src/
│   ├── assets/            # Static images and fonts
│   ├── components/        # Reusable UI components
│   │   ├── icons/         # Animated SVG micro-icon components
│   │   │   ├── LightningIcon.astro
│   │   │   ├── LockIcon.astro
│   │   │   └── SparklesIcon.astro
│   │   ├── BaseHead.astro
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   └── HeaderLink.astro
│   ├── content/           # Markdown and MDX content collections
│   ├── layouts/           # Page layouts (BlogPost.astro)
│   ├── pages/             # Routes (index.astro, about.astro, blog/)
│   └── styles/            # Global CSS design system (global.css)
├── astro.config.mjs
└── package.json
```

## 🧞 Development Commands

All commands are run from the project root:

| Command           | Action                                           |
| :---------------- | :----------------------------------------------- |
| `npm install`     | Installs dependencies                            |
| `npm run dev`     | Starts local dev server at `localhost:4321`      |
| `npm run build`   | Compiles the production site to `./dist/`        |
| `npm run preview` | Previews the production build locally            |

## 📄 License

MIT
