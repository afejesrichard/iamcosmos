# Zenei Könyvtár

A self-contained, searchable browser for the music library exported from a Denon DJ Prime 2 (`m.db`). Everything is baked into a single `index.html` file: 7,266 tracks across 135 crates, with live search and a collapsible folder tree. No server, no build step, no internet connection required once the page loads.

## What's in here

- `index.html` — the entire app and all the data, in one file.
- `.nojekyll` — tells GitHub Pages to serve the files as-is and skip Jekyll processing.
- `README.md` — this file.

## Deploy to GitHub Pages

### Option A: web upload (no command line)

1. Create a new repository on GitHub (public is simplest for Pages on a free account).
2. On the repo page, click **Add file > Upload files**.
3. Drag in `index.html` and `.nojekyll`, then commit.
4. Go to **Settings > Pages**.
5. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick the `main` branch and the `/ (root)` folder, then **Save**.
6. Wait a minute or two. Your site appears at `https://<your-username>.github.io/<repo-name>/`.

### Option B: command line

```bash
git init
git add index.html .nojekyll README.md
git commit -m "Add music library browser"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages under **Settings > Pages** as described in steps 4 to 6 above.

## Updating the library later

The data lives inside `index.html`. To refresh it after changes on the Prime 2, regenerate the file from the new `m.db` and replace `index.html` in the repo. Everything else stays the same.

## Notes

- The page works offline. You can also just double-click `index.html` to open it locally without GitHub at all.
- About 2,200 tracks store artist and title together in one field rather than separately, so they show as a single combined line. Search covers the full string either way.
