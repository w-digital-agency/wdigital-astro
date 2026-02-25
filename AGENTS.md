# AGENTS.md

## Cursor Cloud specific instructions

This is a static Astro website (WDigital Agency). There is **no backend, no database, and no external services** required for local development.

### Services

| Service | Command | Port | Notes |
|---------|---------|------|-------|
| Astro dev server | `npm run dev` | 4321 | Only service needed |

### Key commands

See `package.json` scripts and the README for the full list. Summary:

- **Dev server**: `npm run dev` (port 4321)
- **Build**: `npm run build` (outputs to `dist/`)
- **Type check**: `npm run check` (requires `@astrojs/check` and `typescript` — install with `npm install @astrojs/check typescript` if missing)
- **Lint**: `npm run lint` (currently a no-op echo placeholder)

### Caveats

- `npm run check` exits with errors in `src/components/Analytics.astro` due to inline Google Analytics/GTM scripts in strict TypeScript mode. These are pre-existing and do not affect builds or runtime.
- The `astro check` command will interactively prompt to install `@astrojs/check` and `typescript` if they are not present as dependencies. These are installed by the update script so this should not occur in practice.
- Google Analytics (Partytown) is disabled in dev mode (`!import.meta.env.DEV`), so analytics-related features won't fire locally.
