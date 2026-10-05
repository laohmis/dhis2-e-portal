# DHIS2 E-Portal

Static deployment package prepared from the DHIS2 E-Portal prototype. The page remains in `index.html`; the original Data Entry screenshots remain embedded, and the Surveillance 2.0 Data Analysis screenshots are stored in `assets/data-analysis/`. No build step is required.

## Run locally

Open `index.html` in a modern browser. For a local web server, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Deploy with GitHub and Cloudflare Pages

1. Create a new GitHub repository, for example `dhis2-e-portal`.
2. Upload the contents of this folder, including the `assets/data-analysis/` folder, to the repository root (not the parent folder).
3. In Cloudflare, open **Workers & Pages → Create application → Pages → Connect to Git** and select the repository.
4. Set the production branch to `main` (or the branch you uploaded).
5. Leave the framework preset as **None**. Leave the build command blank and set the build output directory to `/` (repository root). Save and deploy.
6. Open the generated `*.pages.dev` URL and check the navigation, language switch, image lightbox, Resources, both Surveillance 2.0 lessons, and DHIS2 Developments.

Cloudflare Pages redeploys automatically when you push later changes to the connected branch. This package is frontend-only and does not add a database or backend.
