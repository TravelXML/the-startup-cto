# Sapan Kumar Mohanty — Personal Branding PWA

A full Progressive Web App (PWA) personal branding website, ready to deploy on GitHub Pages.

## 📁 File Structure

```
/
├── index.html          ← Main website (all sections)
├── offline.html        ← Shown when user is offline
├── 404.html            ← GitHub Pages SPA routing fix
├── manifest.json       ← PWA manifest (name, icons, theme)
├── sw.js               ← Service worker (caching, offline)
├── README.md           ← This file
└── icons/
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png     ← Android home screen
    ├── icon-384.png
    └── icon-512.png     ← Splash screen / PWA install
```

## 🚀 Deploy to GitHub Pages

### Option A — New repository (recommended)

1. Create a new GitHub repo named **`<your-username>.github.io`**
   - Example: `travelxml.github.io`
2. Upload ALL files maintaining this exact folder structure
3. Go to **Settings → Pages → Source → Deploy from branch → main / root**
4. Your site will be live at `https://travelxml.github.io`

### Option B — Existing repo subdirectory

1. Upload to a repo, e.g. `portfolio`
2. Enable GitHub Pages on that repo
3. Site lives at `https://travelxml.github.io/portfolio/`
4. Update `manifest.json` → change `"start_url": "/"` to `"/portfolio/"`
5. Update `sw.js` → update `PRECACHE_URLS` paths to include `/portfolio/` prefix

### Option C — GitHub CLI (fastest)

```bash
gh repo create travelxml.github.io --public
git init
git add .
git commit -m "Initial PWA deploy"
git remote add origin https://github.com/TravelXML/travelxml.github.io.git
git push -u origin main
```

## ✅ PWA Features Included

| Feature | Details |
|---|---|
| Installable | Add to Home Screen on Android, iOS, Desktop |
| Offline support | Full page cached, custom offline fallback |
| Service Worker | Cache-first for assets, network-first for HTML |
| Web App Manifest | Name, icons, theme color, shortcuts |
| App Shortcuts | "Book a Call" and "Contact" from long-press icon |
| Scroll progress bar | Gold progress indicator at top |
| Dark / Light mode | Toggle with preference saved to localStorage |
| Animated counters | Stats count up on scroll into view |
| Reveal animations | Scroll-triggered fade-in on all cards |
| Active nav tracking | Highlights current section in nav |
| Offline indicator | Yellow bar when connection lost |
| Install banner | Prompts install after 3s (dismissable) |
| Mobile hamburger | Full mobile responsive navigation |
| Back to top | Floating button after 500px scroll |
| SEO meta tags | og:title, og:description, og:image, Twitter card |
| Accessibility | Skip link, ARIA labels, roles, landmarks |

## 🔧 Customisation

### Change your photo
Add `<img>` tag in the hero section of `index.html` after `.hero-content` starts.

### Update contact details
Search for `astartupcto@gmail.com` and `9739803884` and replace.

### Change colour scheme
Edit CSS variables in `:root` in `index.html`:
```css
:root {
  --gold: #C9A84C;     /* Primary accent */
  --accent: #4A9B8E;   /* Secondary accent */
}
```

### Add Google Analytics
Paste your GA4 script just before `</head>` in `index.html`.

### Custom domain
1. Add a `CNAME` file with your domain: `sapankumarmohanty.com`
2. Set up DNS A records pointing to GitHub Pages IPs

## 📱 Testing PWA Locally

```bash
# Serve locally (required — service workers don't work with file://)
npx serve .
# or
python3 -m http.server 8080
```

Then open Chrome DevTools → Application → Service Workers to verify.

## 🎯 Lighthouse Score Targets

- Performance: 95+
- Accessibility: 100
- Best Practices: 100
- SEO: 100
- PWA: Pass

---

Built with pure HTML/CSS/JS. No framework. No build step. Deploy in 60 seconds.
