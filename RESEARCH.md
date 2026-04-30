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

## 2026-04-30 Motion And Media Polish

### Problem

The standalone rebuild worked reliably, but it felt flatter than the original and did not surface all of the available imagery strongly enough.

### Options

- Keep the minimal static composition
- Add layered media, hover motion, and scroll-triggered entrance animations

### Trade-offs

- Minimal presentation is stable but visually underpowered
- Extra motion improves perceived quality, but must stay restrained to avoid looking noisy or breaking mobile usability

### Risks

- Over-animation can reduce readability or feel unprofessional
- Scroll-triggered reveals can hide content if implemented poorly

### Decision

Add layered image composition, subtle continuous image drift, card hover motion, and controlled intersection-based reveal animations with reduced-motion fallback.

## 2026-04-30 Standalone No-Wix Rebuild

### Problem

The mirrored deployment still depended on Wix-hosted runtime services and did not render identically on the target domain.

### Options

- Keep patching the mirrored Wix runtime
- Rebuild the page as a standalone static site using only local assets

### Trade-offs

- Continuing to patch Wix output is faster in the short term, but remains fragile and still depends on upstream Wix services
- A standalone rebuild takes manual implementation effort, but removes third-party runtime dependency and gives predictable hosting behavior

### Risks

- The rebuilt page may not be pixel-identical to the Wix source
- Manual recreation can miss hidden interactions or future content changes from the origin site

### Decision

Replace the mirrored Wix HTML with a self-hosted standalone page that recreates the layout, copy, images, and motion using local assets, inline CSS, and inline JavaScript only.

### Planned Subagents

- None
