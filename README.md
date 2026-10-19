METROPOLE — New York × Tokyo

> "The city never sleeps. Neither does ambition."

A luxury, scroll-driven 3D web experience where an entire skyline rises from the ground as you scroll — towers climb, a golden spire crowns the city, night falls, and ten thousand windows light up.

Fine city living, rendered in real time.

---

✨ Experience

- 🏙️ Scroll-animated 3D city — 50 procedurally placed skyscrapers rise one by one around the camera across a 7-phase cinematic journey
- 🗼 The Spire — a signature golden tower with ring balconies and a blinking beacon that crowns the skyline
- ⛩️ Golden gate — a torii-inspired monument rising over the central avenue
- 🌃 Day → night cycle — the sky darkens, 900 stars fade in, and every tower's procedurally-lit windows glow warm gold
- 🚗 Living avenues — car light trails (gold & red) flow through the streets at night
- 🎥 Cinematic orbiting camera with smooth mouse parallax
- 💎 Editorial luxury design — oversized serif typography, Roman numerals, champagne-gold accents, generous whitespace

🧱 Tech Stack

Layer	Technology	
3D Rendering	[Three.js](https://threejs.org/) (r158)	
Animation	[GSAP 3](https://gsap.com/) + ScrollTrigger	
Smooth Scroll	[Lenis](https://lenis.darkroom.engineering/)	
Typography	Cormorant Garamond & Inter (Google Fonts)	

Zero build step. Zero dependencies to install. Fully static. Everything loads from CDN — it runs on any static host.

📁 Project Structure

```
metropole/
├── index.html      # The entire experience (markup + styles + 3D engine)
└── README.md
```

🚀 Getting Started

Run locally

```bash
# Option A — just open it
open index.html

# Option B — local server (recommended)
npx serve .
# or
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

☁️ Deployment

This is a pure static site — no server code, no build. It deploys to any static host.

Option 1 — Vercel (recommended, 30 seconds) ⚡
1. Push your repo to GitHub
2. Go to [vercel.com](https://vercel.com) → Add New → Project → import the repo
3. Vercel auto-detects it as static — no settings needed, just hit Deploy
4. Live at `https://metropole.vercel.app` (free HTTPS + global CDN)

> No GitHub? Even easier: run `npx vercel` inside the project folder — done.

Option 2 — GitHub Pages (also works fine!) 📄
1. Push the repo to GitHub
2. Settings → Pages → Source: `main` branch, `/ (root)`
3. Live at `https://<your-username>.github.io/metropole/` in 1 minute

Option 3 — Netlify / Cloudflare Pages
Drag-and-drop the folder at [app.netlify.com/drop](https://app.netlify.com/drop) or use [pages.cloudflare.com](https://pages.cloudflare.com) — zero config.

🎮 Controls

Input	Action	
Scroll	Raises the city (7 phases: Grid → Foundations → The Rise → Glass & Steel → The Spire → City Lights → The Metropolis)	
Mouse move	Cinematic camera parallax	

⚙️ Customization

Everything lives in `index.html`:

What	Where	
Phase titles & timings	`phases[]` array in the `<script>` block	
Skyline density & height	`spots[]` generation loop (grid `gx`/`gz` range, height formula)	
Night-glow intensity	`towerMat.emissiveIntensity`, `starMat.opacity` in `applyBuild()`	
Colors (ink, gold, bone)	`:root` CSS variables	
Copy, stats, quotes, plans	Plain HTML sections — edit freely	

🌐 Browser Support

Chrome · Edge · Firefox · Safari (WebGL required). Best experienced on desktop with a mouse.

---

© MMXXVI Metropole Estates — a concept experience. Crafted with Three.js, GSAP & too much espresso. ☕
