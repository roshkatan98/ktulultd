# Research

## 2026-04-30 Initial Clone And Deploy

### Problem

Mirror the public Ktulu LTD website into a shareable static deployment on another domain and publish the result to GitHub.

### Options

- Mirror the generated HTML exactly and keep Wix runtime dependencies
- Rebuild the site manually as a standalone non-Wix site

### Trade-offs

- Exact mirror is fast and visually close, but still depends on Wix runtime/CDN behavior
- Full rebuild removes Wix dependencies, but is much slower and requires manual recreation of animations and layout

### Risks

- Some deeper platform behavior remains Wix-dependent
- Public HTTPS cannot be completed until `ktulu.mmds.dev` has DNS

### Decision

Use the exact mirrored HTML, localize visible image assets, patch the runtime origin, deploy as a static nginx site, and publish the project to GitHub.

### Planned Subagents

- None
