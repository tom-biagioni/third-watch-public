# Third Watch Studios Website MVP

## Goal

Launch a simple public website for Third Watch Studios that establishes the studio identity, provides basic contact and press information, and can evolve into a fuller studio/game presence later.

## Hosting Decision

- Start with GitHub Pages.
- Use the existing `thirdwatchstudios.com` domain.
- Publish from the `main` branch using a `/docs` folder as the GitHub Pages source.
- Keep the initial site static: HTML, CSS, images, favicons, and metadata.
- Revisit Cloudflare Pages, Vercel, or Netlify only when the site needs richer build tooling, previews, server-side features, or a CMS.

## Domain Decision

Use `thirdwatchstudios.com` as the canonical domain.

Recommended GitHub Pages DNS setup:

- Apex/root `@` A records point to GitHub Pages:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- Optional IPv6 AAAA records:
  - `2606:50c0:8000::153`
  - `2606:50c0:8001::153`
  - `2606:50c0:8002::153`
  - `2606:50c0:8003::153`
- `www` CNAME points to `tom-biagioni.github.io`.
- Configure the custom domain in the repository's GitHub Pages settings.
- Add a `/docs/CNAME` file containing `thirdwatchstudios.com`.
- Enable HTTPS once GitHub Pages allows it.
- Verify the domain in GitHub account settings to reduce takeover risk.
- Avoid wildcard DNS records such as `*.thirdwatchstudios.com`.

## Source Structure Decision

Use this structure for the initial publishable site:

```txt
/docs
  /assets
  .nojekyll
  CNAME
  index.html
  site.webmanifest
  styles.css
  third-watch.tokens.css
```

The current starter page and assets live in:

```txt
third_watch_web_branding_kit/04_web_splash_starter/
```

Those files have been copied/adapted into `/docs` for the initial GitHub Pages plumbing pass.

## Brand Direction

Use the existing Third Watch Studios web branding kit as the source of truth for MVP:

- Dark, quiet, restrained visual field.
- Logo-led hero.
- Warm amber as a sparse focal accent.
- Fog stone text on deep sea navy/charcoal backgrounds.
- No bright nautical, pirate, fantasy guild, esports, or film-camera cues.
- Treat the current raster and temporary SVG logo assets as launchable for a starter site, but not as final production/trademark-ready vector identity.

## MVP Site Scope

The MVP should be small and focused:

- Single splash page only.
- Logo-led studio identity.
- Minimal positioning copy.
- Contact link or placeholder.
- Press kit link or placeholder only if needed for layout.
- Correct favicon, Open Graph image, title, and description.
- Mobile-responsive layout.
- Accessible semantic HTML.
- No CMS, backend, analytics, newsletter provider, or blog unless explicitly added later.
- Defer fuller content sections until after the GitHub Pages and domain plumbing is working.

## Candidate Copy

Primary tagline:

```txt
Stories endure after midnight.
```

Short description:

```txt
Third Watch Studios builds atmospheric narrative games about rescue, unstable worlds, and the human light that remains when impossible systems begin to fail.
```

Metadata:

```txt
Title: Third Watch Studios
Description: Narrative games of enduring depth.
Open graph title: Third Watch Studios
Open graph description: Stories endure after midnight.
```

## Open Decisions

- Confirm the final redirect behavior after DNS propagates. Current canonical target is `thirdwatchstudios.com`, with `www` expected to redirect to the apex domain through GitHub Pages.
- Public contact email address. The current `/docs` splash uses `hello@thirdwatchstudios.com` as a temporary launch candidate.
- Whether `Press Kit` should download assets immediately or point to a coming-soon section.
- Whether to include a first game/project teaser now.
- Whether to include a mailing list, Discord, Bluesky, YouTube, Steam, or other community/social links.
- Whether to stay plain HTML/CSS for MVP or introduce Astro once content expands.

## Implementation Checklist

- Create `/docs`. Done.
- Copy starter site assets into `/docs/assets`. Done.
- Add `/docs/index.html`. Done.
- Add `/docs/styles.css`. Done.
- Add `/docs/site.webmanifest`. Done.
- Add `/docs/CNAME`. Done.
- Replace placeholder email. Done with temporary launch candidate `hello@thirdwatchstudios.com`.
- Confirm all asset paths work from the site root. Done for local HTTP smoke test.
- Verify desktop rendering locally. Done.
- Verify mobile rendering locally. Done for 390px width with no horizontal overflow.
- Configure GitHub Pages source to `main` and `/docs`.
- Configure custom domain in GitHub Pages.
- Configure DNS records with the domain provider.
- Wait for DNS propagation and enable HTTPS.
- Test `https://thirdwatchstudios.com` and `https://www.thirdwatchstudios.com`.
