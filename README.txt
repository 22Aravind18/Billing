KHATA BILLING — PWA PACKAGE
============================

WHAT'S INSIDE
  index.html            The whole app (UI + logic). This is the only file
                         that changes when you rebrand/edit the app.
  manifest.json          App name, colors, icons — used by PWABuilder to
                         generate the Android app.
  sw.js                  Offline caching (service worker).
  icons/                 App icons (192, 512, maskable 512, apple-touch).

HOW TO USE WITH PWABUILDER
  1. Upload this whole folder (keep the folder structure exactly as-is)
     to any static host — GitHub Pages, Netlify, Vercel, Firebase Hosting,
     or your own server. Free static hosts all work fine.
  2. Open the hosted URL in Chrome once first and confirm the app loads,
     you can log in, and add a product to the cart — this proves the
     hosting is serving the files correctly with the right paths.
  3. Go to https://www.pwabuilder.com, paste your hosted URL, and let it
     scan the site. It will detect manifest.json and sw.js automatically.
  4. Generate the Android package. No manual manifest edits should be
     needed — it's already production-shaped (icons, theme colors,
     standalone display, start_url all set).

IF YOU WANT TO CHANGE THE APP NAME ANDROID SHOWS
  Edit "name" and "short_name" in manifest.json before running PWABuilder.
  (The in-app "Shop Name" in Settings is separate — that's what prints on
  bills and shows inside the app; manifest name is what Android shows on
  the home screen / app drawer.)

IMPORTANT — LOCAL FILE TESTING
  Opening index.html directly by double-clicking it (file:// address) will
  run the billing app fine, but the browser will NOT register the service
  worker or fully honor the manifest from a file:// URL — that's a browser
  security rule, not a bug. Always test the installable/offline behavior
  from a hosted https:// URL (or http://localhost during development).

DATA & BACKUPS
  All data (products, bills, settings) lives in IndexedDB, inside the
  browser/app on that one device — it does not sync anywhere. Use
  Settings → Backup & Restore regularly, especially before clearing
  browser storage, reinstalling the app, or switching devices.
