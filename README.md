# CanadaVisaPhotoCom — marketing site

GitHub Pages (pending first push): **https://peterjiajunzhang.github.io/CanadaVisaPhotoCom/**

| Path | Purpose |
|------|---------|
| `index.html` | Landing; App Store CTA is a **"Coming soon"** badge — swap in the App Store link once Connect assigns an Apple ID |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `sitemap.xml` / `robots.txt` | SEO |
| `marketing/xiaohongshu-canada/` | Xiaohongshu post previews & export scripts |
| `marketing/appstore-canada/` | App Store screenshot campaign previews & export scripts |
| `screenshots/` | Real device screenshots (473×1024) — **does not exist yet** |
| `demos/` | Real before/after export examples — **does not exist yet** |

**Status:** the iOS app has not shipped yet (no Apple ID, no screenshots, no demo photos). This site, the xiaohongshu deck, and the App Store campaign are all built with illustrated mockups/placeholders standing in for real device screenshots, following the pattern used for `SchengenVisaPhotoCom` before its screenshots arrived.

## Before submitting to App Store Connect

1. Once `CanadaVisaPhoto/Info.plist`'s `AppStoreAppleID` is filled in, update the hero/footer CTA in `index.html` from "Coming soon" to a real App Store link.
2. Capture real device screenshots into a new `screenshots/` folder (473×1024): `01-home.png`, `02-checklist.png`, `03-ready.png`, `04-paywall.png`, `05-exported.png`, `06-saved-photos.png`, `07-languages.png`.
3. Capture real before/after export pairs into a new `demos/` folder as `demo-0N-original.jpg` / `demo-0N-result.jpg`.
4. Once those exist: replace the `.mock-phone` illustrations in `index.html`'s `#app` section with real `<img>` screenshots, add a `#demos` before/after wall (see `SchengenVisaPhotoCom/index.html`), export the App Store campaign, and rebuild the xiaohongshu deck with real screenshots.

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
