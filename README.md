# Portfolio website — GitHub Pages

This repository is ready for GitHub Pages. Images are stored in `assets/images/` instead of being embedded into the HTML. Keep this folder when uploading.

## Deploy

1. Create a public GitHub repository (for example `portfolio`).
2. Upload **all contents** of this folder to the root of the repository. The `index.html` file must be in the root and the `assets/images/` folder must retain its path.
3. In repository **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/(root)`, and save.
4. Your site will appear at `https://YOUR-USERNAME.github.io/portfolio/`.

## Custom domain with Cloudflare

In GitHub repository **Settings → Pages**, set the custom domain first. Then add the GitHub Pages DNS records in Cloudflare, following GitHub's current documentation: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site . Enable HTTPS when available.

## Rover backend later

GitHub Pages is a static host and cannot itself run a rover API or relay live video. Run the API on your DigitalOcean server under an HTTPS subdomain such as `api.yourdomain.com`, and configure the portfolio's frontend to call that URL. Implement authentication and authorization on the backend, limit permitted commands, use secure connections, and test emergency stop and connection-loss behavior before enabling remote driving. Do not put server passwords or API secrets in the GitHub repository.

## Performance

The site uses separate image files, which allows browser caching and lazy loading. The images retain their original quality and animations. Large image files may still benefit from a later optimization pass. The Tailwind and Lucide libraries currently load from third-party CDNs, so an internet connection is needed for those resources.
