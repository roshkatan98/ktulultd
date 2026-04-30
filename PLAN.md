# Plan

## 2026-04-30 Clone Publish And Deploy

### What Will Be Built

- A static mirror project of the Ktulu LTD home page
- A GitHub repository for sharing the clone
- A server-side nginx deployment target for `ktulu.mmds.dev`

### Architecture

- Static files served by nginx
- Wix runtime loaded from upstream CDNs
- Local image assets served from the same site root

### Steps

1. Finalize the mirrored project files
2. Add project documentation
3. Initialize git and create the GitHub repository
4. Copy the site to `/var/www/ktulu.mmds.dev`
5. Add and enable an nginx server block
6. Reload nginx after config validation
7. Complete TLS after DNS exists

### Risks

- DNS for `ktulu.mmds.dev` is currently missing
- TLS issuance depends on DNS readiness

### Dependencies

- GitHub CLI authentication
- nginx
- certbot for later HTTPS enablement

## 2026-04-30 Standalone No-Wix Rebuild

### What Will Be Built

- A standalone static home page with no Wix runtime dependency
- Local-only image usage for all visible page media
- Lightweight self-hosted motion and mobile navigation behavior

### Architecture

- Single `index.html` file with inline CSS and JavaScript
- Local assets loaded from `assets/`
- nginx serves only local project files from `/var/www/ktulu.mmds.dev`

### Steps

1. Capture the current public page structure, copy, and assets
2. Rebuild the page layout manually in standalone HTML/CSS
3. Recreate core motion with small local JavaScript
4. Verify no Wix or other upstream runtime URLs remain
5. Deploy the standalone file to `/var/www/ktulu.mmds.dev`
6. Validate locally and push to GitHub

### Risks

- Visual differences from the Wix-rendered source can remain
- Some hidden Wix-only interactions will be intentionally dropped

### Dependencies

- Existing local image assets
- GitHub CLI authentication
- nginx
