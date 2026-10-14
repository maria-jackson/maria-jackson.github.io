# Maria Jackson - Tech Essays

A simple Jekyll + Minima site for a few essays hosted with GitHub Pages.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000

## GitHub Pages

1. In the GitHub repo, go to Settings -> Pages.
2. Set Source to "Deploy from a branch".
3. Choose the `main` branch and the `/ (root)` folder.
4. Save.
5. Wait for the site to build. Once the certificate is ready, GitHub will enable HTTPS.

## Custom domain

The domain is configured in the `CNAME` file:

```text
mariajackson.dev
```

If you use Cloudflare, keep the records set to DNS only (grey cloud) until GitHub confirms the cert is active.
