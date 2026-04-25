# Deploy Path Assessment

Scope: formal static hosting for `zhexi-trip-site`, with HTTPS delivery and a live verification path. This note only records the deploy plan and fallback order; it does not change the site itself.

## Current tool state

- `vercel` is installed and runnable in PATH.
- `netlify`, `wrangler`, and `surge` are not installed in this environment.
- The workspace is a dirty tree outside this repo as well, so deployment work must stay scoped to `/Users/zhangyu/.openclaw/workspace/zhexi-trip-site`.

## Commands attempted

Verified local tooling:

```bash
which vercel
vercel --version
which netlify || true
which wrangler || true
which surge || true
```

Checked Vercel deploy syntax:

```bash
vercel --help
vercel deploy --help
```

Observed blocker:

- `vercel deploy --help` printed the expected deploy options, then hit an EPERM error while trying to write package-update cache files under `~/Library/Caches/com.vercel.cli/package-updates/`.
- The error path was:
  - `/Users/zhangyu/Library/Caches/com.vercel.cli/package-updates/vercel-latest.lock`
  - `/Users/zhangyu/Library/Caches/com.vercel.cli/package-updates/vercel-latest.log`

## Primary deploy path

Use Vercel first, because it is already present and produces a proper HTTPS static URL with no browser security warning.

Recommended command sequence from the repo root:

```bash
vercel deploy --prod --yes
```

If Vercel needs project linking or login, resolve that in place and retry:

```bash
vercel login
vercel link
vercel deploy --prod --yes
```

If a prebuilt flow becomes necessary later, the supported sequence is:

```bash
vercel build
vercel deploy --prebuilt --prod --yes
```

## Expected blockers

- Vercel auth not available in the current shell.
- First-time project linking prompt.
- The current EPERM cache-write issue in the Vercel CLI package-update path.
- If the CLI cannot complete in this environment, deployment should stop and move to the next provider rather than trying to use ngrok or any insecure tunnel.

## Fallback order

1. Vercel CLI.
2. Netlify CLI.
3. Cloudflare Pages via `wrangler`.
4. Surge.

Current reality on this machine:

- Only Vercel is immediately executable.
- The other three are fallback targets conceptually, but they require installation before they can be used.

Suggested commands if Vercel is blocked:

```bash
npm i -g netlify-cli
netlify deploy --dir . --prod
```

```bash
npm i -g wrangler
wrangler pages deploy . --project-name zhexi-trip-site
```

```bash
npm i -g surge
surge . zhexi-trip-site.surge.sh
```

## Live verification checklist

- Capture the production URL returned by the deploy tool.
- Confirm the URL uses HTTPS and opens without browser warnings.
- Run `curl -I <url>` and confirm `200` or an expected redirect to the deployed site.
- Load the page in a browser and verify the itinerary renders on mobile width.
- Confirm the map section shows real route geometry and clickable POIs.
- Confirm the image section shows real photos instead of placeholders.
- Confirm the static asset paths resolve without mixed-content or certificate errors.
- After verification, update `delivery.md` with:
  - deployed URL
  - major changes
  - image sources
  - remaining limitations

## Decision

Use Vercel as the first deploy path. If the cache permission issue or auth/linking blocks completion, switch immediately to the next provider in the list instead of retrying a tunnel-based workaround.
