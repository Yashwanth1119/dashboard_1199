# Pricing dashboard

The standalone dashboard is in [`pricing-dashboard/index.html`](pricing-dashboard/index.html). It includes Bike, Auto, Car, Mini, Sedan, SUV, and Parcel categories. Open it locally in a browser, or deploy the `pricing-dashboard` folder as a static site. Price edits, manually entered quotes, and the light/dark preference are saved in the current browser only; there is no shared database or live feed from Rapido, Uber, or Ola. The Car and Parcel prices are editable starter assumptions, not rates supplied in your proposal.

## Free deployment option: GitHub Pages with Actions

I added a ready-to-run workflow at [`pricing-dashboard/.github/workflows/pages.yml`](pricing-dashboard/.github/workflows/pages.yml). To keep this prototype separate from the rest of this workspace, create a **new public GitHub repository** containing only the contents of the `pricing-dashboard` folder (including its `.github/workflows` folder). GitHub Pages is available for public repositories on GitHub Free.

Then:

1. Push the dashboard folder contents to the new repository's `main` branch.
2. In the repository, open **Settings → Pages** and set the source to **GitHub Actions**.
3. Open **Actions** and confirm the “Deploy pricing dashboard to GitHub Pages” workflow completes.
4. Open **Settings → Pages** for the published URL. Later pushes to `main` redeploy automatically.

GitHub's [Pages publishing-source guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) documents the Actions source setting and deployment flow; [GitHub Free includes Pages for public repositories](https://docs.github.com/en/pages/getting-started-with-github-pages).

I could not publish from this checkout: it has no configured Git remote, and the GitHub CLI is not installed or authenticated.

## Alternate free deployment option: Cloudflare Pages

Cloudflare Pages supports uploading a folder of static assets through Direct Upload. The dashboard is a single HTML file and does not need a build step.

1. Sign in to Cloudflare and open **Workers & Pages**.
2. Create an application, choose **Pages**, then **Direct Upload**.
3. Upload the `pricing-dashboard` folder from this project.
4. Deploy. Cloudflare will provide a `pages.dev` URL.

Cloudflare's [Direct Upload guide](https://developers.cloudflare.com/pages/get-started/direct-upload/) has the current steps. A public `pages.dev` URL can be viewed by anyone who has it. Direct Upload projects cannot later be switched to Git integration; create a separate Git-integrated project if you want automatic deployments.

Deployment needs a Cloudflare account and a signed-in session. No account credentials are stored in this project.
