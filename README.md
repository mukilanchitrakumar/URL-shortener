# Trimr — URL Shortener

A clean, minimal URL shortener that runs entirely in the browser. No backend, no server, no sign-up required.

---

## Features

- **Instant shortening** — paste a long URL and get a short link in one click
- **Custom aliases** — define your own slug (e.g. `trimr.io/my-link`)
- **Click tracking** — counts how many times each link is visited
- **Favicon preview** — automatically loads the destination site's icon
- **Stats dashboard** — total links created, total clicks, characters saved
- **Persistent storage** — all links are saved in `localStorage` and survive page refreshes
- **Redirect overlay** — smooth animated redirect when visiting a short link
- **Delete links** — remove any link from your history at any time
- **Copy to clipboard** — one-click copy for every link

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Structure | HTML5 |
| Styling | CSS3 (custom properties, animations, responsive) |
| Logic | Vanilla JavaScript (no frameworks) |
| Storage | Browser `localStorage` |
| Fonts | Google Fonts — Instrument Serif + Geist Mono |

No build tools. No npm. No dependencies. Just one HTML file.

---

## Getting Started

### Option 1 — Open directly

Download `index.html` and open it in any modern browser. That's it.

### Option 2 — Clone the repo

```bash
git clone https://github.com/your-username/trimr.git
cd trimr
open index.html
```

### Option 3 — Host on GitHub Pages

1. Fork this repository
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Visit `https://your-username.github.io/trimr`

---

## How It Works

```
User pastes URL
      ↓
App generates a random 7-character code (or uses custom alias)
      ↓
Mapping stored in localStorage: { code → original URL }
      ↓
Short link displayed: trimr.io/<code>
      ↓
Clicking the short link → looks up code → redirects to original URL
      ↓
Click count incremented and saved
```

Since this is a frontend-only app, the short links (e.g. `trimr.io/abc1234`) are **simulated** — they work within the app's interface rather than as real public URLs. To make them publicly resolvable, you would need to deploy a backend or use a service like Netlify redirects.

---

## File Structure

```
trimr/
└── index.html      # Entire app — HTML, CSS, and JS in one file
└── README.md       # Project documentation
```

---

## Browser Support

Works in all modern browsers that support:
- `localStorage`
- `navigator.clipboard`
- CSS custom properties
- `backdrop-filter`

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Firefox 90+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |

---

## Limitations

- Links are stored in the **browser's localStorage** — they are device-specific and will be lost if the browser data is cleared
- Short links are not publicly accessible URLs — they only work within the app
- No analytics beyond basic click counts

---

## Roadmap

- [ ] QR code generation for each short link
- [ ] Export links as CSV
- [ ] Dark mode toggle
- [ ] Link expiry / auto-delete after N days
- [ ] Deploy with a real redirect backend (e.g. Supabase, Firebase)

---

## License

MIT — free to use, modify, and distribute.
