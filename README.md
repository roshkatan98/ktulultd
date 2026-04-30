# Ktulu LTD Clone

Static mirror of `https://www.ktulultd.com/` prepared for deployment on `ktulu.mmds.dev`.

## Existing Features

- Static HTML clone of the current Wix-rendered home page
- Local copies of the visible home-page image assets
- Runtime patching so the page derives its active origin from the current host

## Planned Features

- DNS activation for `ktulu.mmds.dev`
- TLS certificate issuance after DNS is live
- Optional deeper de-Wix rebuild if a fully independent site is needed

## Local Structure

- `index.html`: mirrored site entry point
- `assets/`: local image assets referenced by the home page

## Deployment

- Web root target: `/var/www/ktulu.mmds.dev`
- Nginx vhost target: `/etc/nginx/sites-available/ktulu.mmds.dev`
