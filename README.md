# MoneyUp

A minimal, category-based budget tracker. Allocate money to categories —
Groceries, Transport, Skincare, Eating Out, or your own — and each one
starts as a full bar that drains like HP as you log spends against it.

No backend. Accounts are just a name paired with an auto-generated
9-digit ID, stored in the browser's `localStorage`.

## Files

- `index.html` — the entire app (markup, styles, logic)
- `manifest.json` — lets a phone add MoneyUp to the home screen like a native app
- `icon.svg` — the app icon used by the manifest and as the favicon
- `README.md` — this file

Everything is static. There is no build step, no `package.json`, no
dependencies to install.

## Run it locally

Just open `index.html` in a browser. For live-reload while editing in
VS Code, install the "Live Server" extension and click "Go Live" in the
bottom right.

## Put it on GitHub

```bash
git init
git add .
git commit -m "MoneyUp"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Deploy on Vercel (what your friend's site is running on)

1. Go to vercel.com and sign in with GitHub.
2. Click **Add New → Project**, then pick the repo you just pushed.
3. Framework preset: choose **Other** (this is a plain static site — no
   build command, no output directory needed).
4. Click **Deploy**. Vercel gives you a live URL like
   `moneyup.vercel.app` within a few seconds.

Every future `git push` to `main` redeploys automatically.

## A limit worth knowing

Accounts live in the browser's `localStorage`, not on a server. That
means:

- A 9-digit ID only logs someone back in on the **same browser, same
  device** it was created on.
- Clearing site data, using a different browser, or switching devices
  starts fresh — there's nothing on a server to recover from.

This is fine for personal use or a demo. Moving to real cross-device
accounts later would mean adding a small backend (or a service like
Supabase/Firebase) to store users and categories instead of
`localStorage` — a separate, bigger step from what's here.
