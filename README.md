# My Gym — standalone app

This is a self-contained version of your gym tracker. No build step, no account —
it's plain HTML/JS that runs in any browser and can be "installed" to your phone's
home screen as an app icon.

It saves your plan and completions in the browser's local storage on whichever
device/browser you open it in. That means: it does **not** sync with the version
you were using inside Claude, and it won't automatically sync between your phone
and laptop unless you open the same hosted URL on both.

## 1. Put it online (needed for "Add to Home Screen" to work properly)

Easiest free option, and you've already got a GitHub account (github.com/chiranth1825),
so this is basically zero setup:

1. Go to github.com → New repository → name it something like `my-gym` → Create.
2. On the repo page, click **Add file → Upload files**, then drag in all the files
   from this folder (`index.html`, `manifest.json`, `sw.js`, and the `icons` folder
   with its 3 PNGs, keeping that folder structure). Commit.
3. Go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait ~1 minute, then your app is live at:
   `https://chiranth1825.github.io/my-gym/`

If you'd rather use git from the command line:
```bash
cd mygym-pwa
git init
git add .
git commit -m "My Gym app"
git branch -M main
git remote add origin https://github.com/chiranth1825/my-gym.git
git push -u origin main
```
Then enable Pages the same way (step 3 above).

## 2. Add it to your phone's home screen

**Android (Chrome):** open the GitHub Pages URL → tap the ⋮ menu → "Add to Home
screen" / "Install app".

**iPhone (Safari):** open the URL → tap the Share icon → "Add to Home Screen".

You'll get a proper icon with no browser bar when you open it — it behaves like an
installed app. It also works offline after the first load, since it caches itself.

## 3. Updating it later

Edit the files, push the changes to the same repo, and GitHub Pages updates
automatically. Since the app caches itself for offline use, you may need to open
it and pull down to refresh once, or close and reopen it, to see the update.

## Files in this folder

- `index.html` — the whole app
- `manifest.json` — tells the phone how to display the installed icon
- `sw.js` — service worker, caches the app for offline use
- `icons/` — home-screen icons
