# SB Plugins Monorepo

Prerequisites

- Node (compatible version for the repo)
- pnpm (v10+ recommended)

1. Install workspace dependencies (run from the repository root)

```bash
pnpm install
```

2. Run a command across the whole workspace, use `pnpm -r` or `pnpm --parallel -r` as appropriate.

## Field Plugins

### `ai-tags`

Run the plugin:

```bash
pnpm --filter ai-tags dev
```

Build the plugin:

```bash
pnpm --filter ai-tags build
```

Run tests for the plugin:

```bash
pnpm --filter ai-tags test
```
