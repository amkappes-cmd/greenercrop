# Greener Crop

Single-page marketing site for Greener Crop. Static HTML / CSS / JS. Hosted on GitHub Pages, pointed at `www.greenercrop.com` via CNAME.

**v2 changes:** expanded palette with tomato / amber / leaf / sky accents, and the Approach section now uses a hydroponic greenhouse background photo (see `assets/README-IMAGES.txt` for how to drop the image in).

## What's here

```
.
├── index.html              # The entire site
├── styles.css              # Brand styling (green palette)
├── script.js               # Nav, smooth scroll, reveal-on-scroll
├── assets/
│   └── favicon.svg
├── CNAME                   # Custom domain: www.greenercrop.com
├── .github/workflows/
│   └── pages.yml           # Auto-deploy to GitHub Pages on push to main
├── .gitignore
└── README.md
```

## Local preview

No build step. Open `index.html` directly, or run a local server:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Deploy to GitHub Pages

1. Push this repo to GitHub (public or private, both work with Pages).
2. In the repo: **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Push to `main`. The workflow in `.github/workflows/pages.yml` will build and deploy automatically.

### Custom domain

`CNAME` is already set to `www.greenercrop.com`. After the first successful deploy:

1. In **Settings → Pages**, confirm the custom domain shows `www.greenercrop.com`.
2. In your DNS provider (currently Wix, since the domain is registered there), add a CNAME record:
   - **Host:** `www`
   - **Points to:** `<your-github-username>.github.io`
3. For the apex `greenercrop.com`, add A records pointing to GitHub's Pages IPs:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
4. Tick **Enforce HTTPS** in Pages settings once DNS propagates.

## Lead capture

The site uses mailto-based contact. Every CTA links to `mailto:info@greenercrop.com` with a pre-filled subject line and body template. No form backend required.

If a form-based flow is wanted later, the easiest path is to replace the mailto CTAs with a Formspree or Netlify Forms endpoint and wire a form element into the `#contact` section.

## Content structure

Single page. Sections:

1. **Hero** - "From desert to oasis" positioning + headline stats
2. **Approach** - Five pillars (Farm Design, Crop Strategy, Input & Supplies, Farm Management, Data & Analytics)
3. **Outcomes** - The NO / LESS / MORE grid (the hydroponics proof)
4. **Clients** - Featured clients: Marathon Digital Holdings, Regency Group, Khalid Juffali Holding, USAID, Sharjah Asset Management
5. **Contact** - CTA + offices (Middletown, DE and Dubai, UAE)
6. **Footer** - Copyright and tagline

Regenerative farming, case studies, executive team, and careers have all been removed per scope.

## Editing

The site is a single HTML file. To change copy: edit `index.html`. To tweak brand: edit the `:root` custom properties at the top of `styles.css`.

## Brand palette

Kept from the existing Greener Crop identity:

| Token | Hex | Use |
|---|---|---|
| `--green-900` | `#1E3A24` | Dark section bg, headings |
| `--green-800` | `#2E5A3C` | Primary brand green |
| `--green-700` | `#3C7452` | Hover states |
| `--green-500` | `#6FA37B` | Mid-tone accent |
| `--green-300` | `#A4C3A2` | Sage highlights |
| `--green-100` | `#E8F0E4` | Soft section bg |
| `--paper` | `#FAFAF7` | Page background |
