# CanadaVisaPhotoCom — marketing site

Live site: **https://canada.visaphoto1tap.com/**

| Path | Purpose |
|------|---------|
| `index.html` | Landing; App Store CTA is a **"Coming soon"** badge — swap in the App Store link once Connect assigns an Apple ID |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `sitemap.xml` / `robots.txt` | SEO |
| `VisaPhotoApps/Marketing/Canada/xiaohongshu/` | Xiaohongshu post previews & export scripts |
| `VisaPhotoApps/Marketing/Canada/appstore/` | App Store screenshot campaign previews & export scripts |
| `screenshots/` | Real device screenshots — **5 of 6 captured** (missing `06-saved-photos.png`) |
| `demos/` | Real before/after export pairs — all 6 captured |

**Status:** real screenshots and demo pairs are mostly in. `index.html` has a real `#demos` wall and a real `#app` screenshot grid (currently 5 screens: home, checklist, paywall, exported, languages). **Still needed: `06-saved-photos.png`** (the "All Saved Photos" grid) — drop it into `screenshots/` and add its `<figure>` back into `index.html`'s `#app` grid + the App Store campaign slide that references it. Still pending: Apple ID / App Store Connect record.

## Before submitting to App Store Connect

1. Once `CanadaVisaPhoto/Info.plist`'s `AppStoreAppleID` is filled in, update the hero/footer CTA in `index.html` from "Coming soon" to a real App Store link.
2. Capture `06-saved-photos.png` (see Status above) — the last missing canonical screenshot.
3. Re-run exports after any new screenshot lands:
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
