# memovee

Developer-centric static site built with [Astro](https://astro.build), [Tailwind CSS v4](https://tailwindcss.com), and [daisyUI](https://daisyui.com), deployed to [Cloudflare Workers](https://workers.cloudflare.com) via Wrangler.

## Stack

- **Astro** — static site generation
- **Tailwind CSS v4** — via `@tailwindcss/vite`
- **daisyUI v5** — component layer (loaded through `@plugin "daisyui"` in `src/styles/global.css`)
- **Cloudflare Workers** — static assets deployment (assets-only, no Worker code)

## Requirements

- Node.js >= 22.12.0

## Commands

| Command             | Description                                    |
| ------------------- | ---------------------------------------------- |
| `npm run dev`       | Start the Astro dev server                     |
| `npm run build`     | Build the static site to `./dist`              |
| `npm run preview`   | Preview the built site locally                 |
| `npm run deploy`    | Build and deploy to Cloudflare Workers         |

## Cloudflare

- Worker name and config: `wrangler.jsonc` (static assets from `./dist`)
- Requires `wrangler login` before the first deploy
- Environments: build with `CLOUDFLARE_ENV=<env> npm run build` when using multiple environments

## Git flow

This repository uses [git-flow](https://github.com/nvie/gitflow):

- `master` — production
- `develop` — integration
- `feature/*`, `release/*`, `hotfix/*` branches
