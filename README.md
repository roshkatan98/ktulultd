# Ktulu LTD Clone

Standalone static rebuild of `https://www.ktulultd.com/` prepared for deployment on `ktulu.mmds.dev`.

## Existing Features

- Standalone home page with no Wix runtime dependency
- Local copies of the visible home-page image assets
- Inline CSS and JavaScript for layout, motion, and mobile navigation

## Planned Features

- Optional expansion into additional standalone pages
- Optional contact form implementation behind a local backend endpoint

## Local Structure

- `index.html`: standalone site entry point
- `assets/`: local image assets referenced by the home page

## Deployment

- Web root target: `/var/www/ktulu.mmds.dev`
- Nginx vhost target: `/etc/nginx/sites-available/ktulu.mmds.dev`
