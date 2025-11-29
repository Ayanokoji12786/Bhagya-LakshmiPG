**Bhagya Lakshmi PG — Landing Page**

A simple static landing page for the Bhagya Lakshmi PG property (HTML + Tailwind via CDN). This repository contains a single HTML file that serves the site.

**Preview**
- **Local server:** Serve the project folder and open a browser at the given port.

```bash
cd "/Users/MAC/Desktop/LOLLL OHIOO"
# Python built-in web server
python3 -m http.server 8000
# open http://localhost:8000/

# or with Node's serve package
npx serve .
```

**Deploy to Netlify**
- **Via Git (recommended):** commit and push the project to your remote repo connected to Netlify; Netlify will auto-deploy.

```bash
git add .
git commit -m "Add landing page"
git push
```

- **Via Netlify web UI (Drag & Drop):** Zip or select the project folder and upload it in the Netlify Sites > New site > Deploy manually area.

- **Via Netlify CLI:**

```bash
npm install -g netlify-cli
netlify deploy --prod --dir=.
```

**Important:** Netlify expects the site's entry file to be named exactly `index.html` (no leading/trailing spaces). If your file is accidentally named ` index.html` (leading space), Netlify will not find it and you'll get a 404.

To fix the filename locally:

```bash
# from the project folder
mv " index.html" index.html
# then commit the change
git add index.html
git commit -m "Fix: rename index file"
git push
```

**Single Page Apps / Client-side routing**
- If you later add client-side routing (URLs like `/dashboard`), add a `_redirects` file to the publish folder with the following to fall back to `index.html`:

```
/*    /index.html   200
```

**Assets & Dependencies**
- Uses CDN-hosted resources; no build step required:
  - Tailwind CSS via `https://cdn.tailwindcss.com`
  - Google Fonts (`Inter`, `Poppins`)
  - Font Awesome (CDN)

**Troubleshooting**
- 404 on Netlify root: most commonly caused by `index.html` missing or misnamed; verify the publish directory contains a file named exactly `index.html`.
- Blank page or missing icons/fonts: check network access to the CDNs and correct URL paths.
- Broken anchor links: the page uses hash anchors (e.g., `#home`) — those work without special server redirects.

**Notes**
- The site is static and requires no build tools. If you later convert to a framework (React/Vue/Svelte) you will need a build step and a proper publish directory.

**Contact**
- For help with committing, renaming files, or adding Netlify redirects, open an issue or ask here and I can prepare the commands.
