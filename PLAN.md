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
