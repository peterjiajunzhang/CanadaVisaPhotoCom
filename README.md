# CanadaVisaPhotoCom — marketing site

Live site: **https://canada.visaphoto1tap.com/**

| Path | Purpose |
|------|---------|
| `index.html` | Landing with live iPhone App Store download |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `sitemap.xml` / `robots.txt` | SEO |
| `VisaPhotoApps/Marketing/Canada/xiaohongshu/` | Xiaohongshu post previews & export scripts |
| `VisaPhotoApps/Marketing/Canada/appstore/` | App Store screenshot campaign previews & export scripts |
| `screenshots/` | Real device screenshots — **all 6 captured** |
| `demos/` | Real before/after export pairs — all 6 captured |


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

## 2026-11-17 website update

The previous homepage called edited exports IRCC-ready and attributed app export settings to IRCC and ICAO. The current page describes the app’s 420×540 JPEG and background replacement, cites IRCC’s unaltered-photo rule, and compares TRV framing with separate PR card requirements. The previous wording is available in the parent commit.

The iPhone download buttons share the App Store Connect campaign `canada-website-20261117` with the matching Visa Photo 1-Tap links. The provider token is the one issued for this developer account. The structured app listing URL remains clean.

## Page-level store attribution

Coverage includes 1 pages with existing store actions. Guide indexes, policy and support pages without store links retain their original navigation.

Website attribution uses one campaign for each canonical page and destination app. Repeated links to the same app on a page share its campaign. iPhone links retain the developer's existing provider token. Google Play uses its supported campaign parameter for eligible US links. The previous shared campaigns remain in deployment history and existing campaign records.

Direct store links still work if the counter cannot load. A real store link click sends the canonical page path and store/app target to a first-party counter. It uses no cookies or user/device identifiers, sends no photos, and stores aggregate counts. Automated checks use a separate QA flag. The counter records supported browser activations of direct store links. Store reports provide downloads when their reporting thresholds are met. Choosing a country site attributes the eventual download to the page that links directly to the store. [Website analytics disclosure](https://us.visaphoto1tap.com/privacy.html#website-analytics)
