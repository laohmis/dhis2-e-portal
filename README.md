# DHIS2 E-Portal

A static learning portal prototype with step-by-step DHIS2 guidance, available in English and Lao. There is no build step, database, or backend. The whole site is plain HTML, CSS, and JavaScript plus image files.

**Live site:** https://laohmis.github.io/dhis2-e-portal/

## What is included

- Home, Program Guidance, DHIS2 Developments, DHIS2 Updates, and Resources pages
- Surveillance 2.0 lessons: **Data Entry** and **Data Analysis**
- English / Lao language switch (the choice is remembered in the browser)
- Click-to-enlarge screenshots

## Folder structure

```
dhis2-e-portal/
├── index.html                 # the whole portal (text, lessons, logic)
├── README.md
└── assets/
    ├── data-entry/            # Data Entry screenshots (SUR-DE-xxx.png)
    └── data-analysis/         # Data Analysis screenshots (SUR-DA-xxx.png)
```

Screenshots are separate image files, not embedded in `index.html`. This keeps the page small (about 230 KB) so it loads quickly, including on slow connections.

## Image naming rules

Each lesson step looks for an image named after its step ID. Names are **case-sensitive** and must match exactly.

- Data Entry: `assets/data-entry/SUR-DE-001.png`, `SUR-DE-010A-01.png`, `SUR-DE-014-02.png`, and so on
- Data Analysis: `assets/data-analysis/SUR-DA-001.png`, `SUR-DA-008-01.png`, and so on

If a step shows a broken image, check three things: the file exists in the right folder, the name matches the step ID exactly, and the file has been pushed to GitHub.

## Run locally

Open `index.html` in a modern browser. Or, to test it the way a web server serves it, run this from the project folder:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Update the site

1. Edit `index.html` and/or add screenshots to the matching `assets/` folder.
2. In GitHub Desktop, write a short summary and click **Commit to main**, then click **Push origin**.
3. Wait about one to three minutes for GitHub Pages to rebuild. The **Actions** tab shows a "pages build and deployment" run, and a green check means it is live.
4. Hard-refresh the site (Ctrl+Shift+R, or Cmd+Shift+R on Mac) if you still see the old version.

## Deployment (GitHub Pages)

The site is published from the `main` branch, root folder.

- Repository **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: **main**, folder **/ (root)**

The site address follows the pattern `https://<owner>.github.io/<repository>/`. Renaming the repository or the owner changes the address, and GitHub does not redirect old Pages links. GitHub Pages on a free account needs the repository to be **public**, so do not store sensitive content in it.

## Notes

- This is a frontend-only prototype. It does not store user data, logins, or progress on a server.
- Links to external resources (DHIS2 documentation, Google Drive folders, videos) open in a new tab and depend on those services being available.
- If the portal later needs user accounts, progress tracking, or feedback forms, a backend or database can be added without changing the lesson content.
