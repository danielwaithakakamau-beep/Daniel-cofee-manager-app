# DANIEL COFFEE FARM MANAGER APP

Track plots, harvests, tasks, expenses, weather, and profit for your coffee farm.  
Works offline. Optional online sync across phones and computers.

## Quick start (no account)

1. Download or clone this folder.
2. Open `index.html` in Chrome or Safari.
3. Optional: **Add to Home Screen** for an app-like icon.
4. Data is saved in the browser (localStorage).

## Online sync (two options)

### A) Built-in sync code (no signup)

1. Open the app → **More** → **Online Sync**.
2. Tap **Upload to Cloud** → copy the sync code.
3. On another device, open the same app → paste the code → **Restore from Cloud**.

### B) Firebase (your own cloud)

Use this if you want data under your Google account and more control.

1. Go to [Firebase Console](https://console.firebase.google.com/) → Create a project (free).
2. Add a **Web** app → copy the `firebaseConfig` object.
3. Enable **Firestore Database** → start in **test mode** (for personal use), or lock rules later.
4. In the farm app: **Settings (⚙️)** → paste your Firebase config → **Save**.
5. Use **Upload / Restore** under Online Sync (Firebase mode).

Example Firestore rule for personal use only (replace later for production):

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /farms/{farmId} {
      allow read, write: if true;  // personal farm only — tighten later
    }
  }
}
```

## GitHub

```bash
git clone <your-repo-url>
cd daniel-coffee-farm-manager-app
# open index.html or host with GitHub Pages
```

### GitHub Pages (optional)

1. Push this folder to a GitHub repository.
2. Repo **Settings** → **Pages** → Source: `main` branch, folder `/ (root)`.
3. Open the Pages URL on any device.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Full app (UI + logic) |
| `manifest.json` | Install as app (PWA) |
| `sw.js` | Offline cache |
| `icon-192.png` / `icon-512.png` | App icons |

## Features

- Plots (variety, trees, size, photos)
- Tasks (pruning, fertilizing, spraying, weeding…)
- Harvests (kg, quality)
- Expenses & profit calculator
- Weather / rainfall log
- English ↔ Kiswahili
- CSV export, JSON backup
- Online sync (code or Firebase)

## Privacy

- Default: all data stays on your device.
- Cloud sync only runs when you upload or restore.
- Do not share your Firebase config or sync codes publicly.
