# Deployment

## How it works

ZUGO Bike is hosted on GitHub Pages. Push to `main` and the site is live in ~60 seconds. No build step required for HTML/JS. CSS requires a rebuild when Tailwind classes change.

## Push workflow

```bash
git add -A
git commit -m "description of change"
git push origin main
```

Verify at https://YOUR_USERNAME.github.io/zugo-bike/ after ~60 seconds.

## Version format

`vYYMMDD.NN` — date + daily counter (e.g. `v260406.01`)

After every push, read `version.json` to confirm the current version.

## Tailwind CSS

After adding new Tailwind utility classes:

```bash
npm run css:build
```

This compiles `styles/tailwind.css` → `styles/tailwind.out.css`. Commit both files.

## Live URLs

| Environment | URL |
|---|---|
| GitHub Pages | https://YOUR_USERNAME.github.io/zugo-bike/ |
| Custom domain | https://YOUR_DOMAIN/ (configure after DNS setup) |
| Store (Shopify) | https://www.zugobike.com |
| Repository | https://github.com/YOUR_USERNAME/zugo-bike |

## Environments

There is one environment: production. All pushes to `main` are live immediately.

Use feature branches for work in progress:

```bash
# Start a new feature
git checkout -b feature/blog-system

# When ready to go live
git push origin feature/blog-system
# Open a PR → merge to main → auto-deployed
```

## GitHub Pages setup (one-time)

1. Go to repo Settings → Pages
2. Set source to `main` branch, root `/`
3. Add `.nojekyll` file to root (already included — tells GitHub not to process files with Jekyll)
4. Custom domain: add a `CNAME` file with your domain, then configure DNS
