# CanadaVisaPhotoCom — marketing site

Live site: **https://canada.visaphoto1tap.com/**

| Path | Purpose |
|------|---------|
| `index.html` | Landing; App Store CTA is a **"Coming soon"** badge — swap in the App Store link once Connect assigns an Apple ID |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `sitemap.xml` / `robots.txt` | SEO |
| `VisaPhotoApps/Marketing/Canada/xiaohongshu/` | Xiaohongshu post previews & export scripts |
| `VisaPhotoApps/Marketing/Canada/appstore/` | App Store screenshot campaign previews & export scripts |
| `screenshots/` | Real device screenshots — **all 6 captured** |
| `demos/` | Real before/after export pairs — all 6 captured |

**Status:** all real screenshots and demo pairs are in. `index.html` has a real `#demos` wall and a full 6-screen real `#app` screenshot grid. Still pending: Apple ID / App Store Connect record (CTA still shows "Coming soon").

## Before submitting to App Store Connect

1. Once `CanadaVisaPhoto/Info.plist`'s `AppStoreAppleID` is filled in, update the hero/footer CTA in `index.html` from "Coming soon" to a real App Store link.
2. Re-run exports after any future screenshot changes:
   ```bash
   cd VisaPhotoApps/Marketing/Canada/appstore && npm run export
   cd VisaPhotoApps/Marketing/Canada/xiaohongshu && npm run export
   ```

**Product facts baked into this site** (source: `VisaPhotoApps/docs/canada-visa-photo-spec.md`):
- **Temporary Resident Visa** (visitor / study / work permit) photo spec — 35×45mm, 420×540 px export, same aspect/pixel minimum as Schengen.
- Head height (chin to crown) **31–36 mm**; JPEG target 240 KB, minimum 60 KB, sRGB.
- **ICAO Doc 9303 is explicitly cited by IRCC** — this is one of the few countries (besides Schengen) where an ICAO-alignment claim is defensible in copy.
- Explicitly **not** the PR card / citizenship / passport photo program (50×70mm) — don't let copy conflate the two.
- Accent color: flag red `#FF0000`.

**iOS app repo:** [VisaPhotoApps](https://github.com/peterjiajunzhang/VisaPhotoApps) — scheme `CanadaVisaPhoto`.

Clone on a new machine:

```bash
git clone https://github.com/peterjiajunzhang/CanadaVisaPhotoCom.git
git clone https://github.com/peterjiajunzhang/VisaPhotoApps.git
```

Open **`VisaPhotoApps/README.md`** for full workstation setup.

## Static CSS, icons and images

The homepage and privacy policy no longer load Tailwind or Lucide at runtime. The only third-party script left is the Cloudflare Web Analytics beacon.

- **CSS**: `assets/tailwind.css` is prebuilt with Tailwind CSS v3.4.17 from `index.html` and `privacy.html`, using `tailwind.config.cjs` (the theme that used to be inline in the page) and `assets/tailwind.input.css`. After changing any class in `index.html` or `privacy.html`, rebuild it and commit the output:

  ```bash
  npx tailwindcss@3.4.17 -c tailwind.config.cjs -i assets/tailwind.input.css -o assets/tailwind.css --minify
  ```

- **Icons**: Lucide icons are inline `<svg>` in `index.html`. Licence: `assets/licenses/lucide.txt` (ISC).
- **App icons**: `assets/icons/*.webp` are resized copies of each app's `AppIcon.png`, the same files the US site uses; see `assets/icons/provenance.json`. `AppIcon.png` stays as the favicon and social image.
- **Images**: PNG or JPG files over about 300 kB have a WebP copy next to them, and the page uses the WebP. The originals stay in the repo. Images below the fold use `loading="lazy"` and have their real `width`/`height`.
