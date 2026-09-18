# English Foundations Hub — MVP

English Foundations Hub is a lightweight, static academic-support web app for university EFL students. It is designed for deployment on **Vercel**. Students use it through a normal browser URL; no Google Play or other app store is required.

## What is included

- A 24-question, skill-mapped Foundation Check with a recommended pathway
- A Foundation Map containing ten priority skills
- An interactive S1 unit: feedback, retry flow, challenge, and mastery check
- Quick Fix, My Foundation, Academic Support, and Project Team/Credits screens
- English/Arabic switching with RTL layout support
- Browser-only progress in `localStorage` — no accounts, database, or backend
- Optional PWA installation using the browser’s **Add to Home Screen** command

## Run locally

This project has no build step or package dependencies. You can either open `index.html` directly for a basic preview, or use a local static web server for a full PWA preview.

For example, from this folder:

```bash
python3 -m http.server 4173
```

Then visit `http://localhost:4173`. The service worker only registers on `localhost` or HTTPS, so use the local server when testing offline support.

## Deploy to Vercel

1. Create a GitHub repository and upload this project folder.
2. Sign in at [vercel.com](https://vercel.com) and choose **Add New → Project**.
3. Import the GitHub repository.
4. Leave the framework preset as **Other**. Do not add a build command or output directory.
5. Click **Deploy**.
6. Open the URL Vercel provides. Future commits to the connected branch deploy automatically.

`vercel.json` supplies the small set of required static headers. The app uses hash-based in-page routes, so it works correctly without server-side route rewrites.

## PWA notes

The web manifest, icons, theme metadata, and service worker are included. On supported mobile browsers, students can use the browser menu’s **Add to Home Screen** option. This remains a website and does not require app-store installation. The first online visit saves the app shell for basic offline access.

## Project structure

- `index.html` — application shell and mobile/PWA metadata
- `app.js` — views, interaction, language switching, and local progress
- `data.js` — skill and question content
- `styles.css` — responsive and RTL-aware styles
- `manifest.webmanifest`, `service-worker.js`, and `icons/` — optional PWA support
