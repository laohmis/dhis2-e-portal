# DHIS2 E-Portal

A static learning portal prototype with step-by-step DHIS2 guidance, available in English and Lao. There is no build step, database, or backend. The whole site is plain HTML, CSS, and JavaScript plus image files.

**Live site:** https://laohmis.github.io/dhis2-e-portal/

## What is included

**Program Guidance**

| Program | Learning area | Status |
|---|---|---|
| Surveillance 2.0 | Data Entry | Available |
| Surveillance 2.0 | Data Analysis | Available |
| Surveillance 2.0 | Standard Reports | Available |
| Surveillance 2.0 | Data Quality | Coming soon |
| Mother and Child (MCH) | Data Entry, Data Analysis, Standard Reports, Data Quality | Coming soon (program is open, lessons to be added) |
| HIV | - | Coming soon |
| TB | - | Coming soon |

**Other sections:** Home, DHIS2 Developments, DHIS2 Updates, and Resources.

**Features:** English / Lao language switch (the choice is remembered in the browser), click-to-enlarge screenshots, step-by-step navigation with a progress bar.

## Folder structure

```
dhis2-e-portal/
├── index.html                 # the whole portal (text, lessons, logic)
├── README.md
└── assets/
    ├── data-entry/            # Surveillance 2.0 Data Entry   (SUR-DE-xxx.png)
    ├── data-analysis/         # Surveillance 2.0 Data Analysis (SUR-DA-xxx.png)
    └── standard-report/       # Surveillance 2.0 Standard Report (SUR-SR-xxx.png)
```

Screenshots are separate image files, not embedded in `index.html`. This keeps the page small so it loads quickly, including on slow connections. Each new lesson gets its own folder under `assets/`.

## Image naming rules

Each lesson step looks for an image named after its step ID. Names are **case-sensitive** and must match exactly, including the file extension.

- Data Entry: `assets/data-entry/SUR-DE-001.png`, `SUR-DE-010A-01.png`, `SUR-DE-014-02.png`, and so on
- Data Analysis: `assets/data-analysis/SUR-DA-001.png`, `SUR-DA-008-01.png`, and so on
- Standard Report: `assets/standard-report/SUR-SR-001.png`, `SUR-SR-009-01.png`, and so on

The final "Lesson Completed" step of each lesson has no screenshot.

If a step shows a broken image, check three things: the file exists in the right folder, the name and extension match the step ID exactly, and the file has been pushed to GitHub. The page and its images must use the same format. If `index.html` asks for `.png`, the files must be `.png`.

## Content register

Lesson steps are prepared in the **DHIS2 E-Portal Content Register** (Excel). Each row has a Content ID, program, learning area, lesson, step title, screenshot ID, and the instruction text. The Content ID and Screenshot ID in the register are the names used in the portal and the image files. Tip: set the Step ID column to **Text** format in Excel, otherwise values such as `9-1` are converted to dates.

## Run locally

Open `index.html` in a modern browser. Or, to test it the way a web server serves it, run this from the project folder:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Add or update a lesson

1. Prepare the steps (title, instruction, screenshot name) in the content register, in English and Lao.
2. Save the screenshots in a new folder under `assets/` (for example `assets/standard-report/`), named exactly as in the register.
3. Add the lesson to `index.html` (steps, groups, translations, and the learning area card).
4. In GitHub Desktop, write a short summary and click **Commit to main**, then **Push origin**. Include the new images in the same commit.
5. Wait one to three minutes for GitHub Pages to rebuild. The **Actions** tab shows a "pages build and deployment" run, and a green check means it is live.
6. Hard-refresh the site (Ctrl+Shift+R, or Cmd+Shift+R on Mac) if you still see the old version.

## Deployment (GitHub Pages)

The site is published from the `main` branch, root folder.

- Repository **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: **main**, folder **/ (root)**

The site address follows the pattern `https://<owner>.github.io/<repository>/`. Renaming the repository or the owner changes the address, and GitHub does not redirect old Pages links. GitHub Pages on a free account needs the repository to be **public**, so do not store sensitive content in it.

## Notes

- This is a frontend-only prototype. It does not store user data, logins, or progress on a server.
- Lao text should be reviewed by a Lao speaker before wider sharing.
- Links to external resources (DHIS2 documentation, Google Drive folders, videos) open in a new tab and depend on those services being available.
- If the portal later needs user accounts, progress tracking, or feedback forms, a backend or database can be added without changing the lesson content.
