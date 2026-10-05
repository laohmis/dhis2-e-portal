# DHIS2 E-Portal

Static deployment package prepared from the existing DHIS2 E-Portal prototype. The original page is preserved as `index.html`; its CSS, JavaScript, and 25 screenshots are embedded in that file, so no build step or asset folder is required.

## Run locally

Open `index.html` in a modern browser. For a local web server, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Deploy with GitHub and Cloudflare Pages

1. Create a new GitHub repository, for example `dhis2-e-portal`.
2. Upload `index.html`, `README.md`, and `.gitignore` from this folder to the repository root (or upload the folder contents, not the parent folder).
3. In Cloudflare, open **Workers & Pages → Create application → Pages → Connect to Git** and select the repository.
4. Set the production branch to `main` (or the branch you uploaded).
5. Leave the framework preset as **None**. Leave the build command blank and set the build output directory to `/` (repository root). Save and deploy.
6. Open the generated `*.pages.dev` URL and check the navigation, language switch, image lightbox, Resources, Surveillance 2.0 Data Entry, and DHIS2 Developments pages.

Cloudflare Pages redeploys automatically when you push later changes to the connected branch. This package is frontend-only and does not add a database or backend.
