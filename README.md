# StarWar — Character Cards (React + TypeScript)

Lightweight React app that displays Star Wars characters and character cards. Built with Create React App (TypeScript template) and a small assets set of SVG character icons.

## What this project contains

- React + TypeScript front-end
- Character card components in `src/components/card`
- Pagination and search controls
- Character-related API services in `src/services/Character`
- Character SVG assets in `src/assets/character` with an aggregator module (`index.ts`) that re-exports them

## Quick start

1. Install dependencies

```powershell
npm install
```

2. Start the dev server

```powershell
npm start
```

Open http://localhost:3000 in your browser. The app will hot-reload on changes.

## Available scripts

- `npm start` — start dev server
- `npm test` — run tests
- `npm run build` — production build
- `npm run eject` — eject CRA config (irreversible)

## Character assets / images

All character SVGs live in `src/assets/character`. There's an `index.ts` aggregator that imports each SVG and exports them as named exports plus a default object map:

- Named import example:

```ts
import { ObiWanKenobi } from "src/assets/character";
```

- Default map example:

```ts
import characterImages from "src/assets/character";
// e.g. characterImages.ObiWanKenobi
```

Use these imports in components like:

```tsx
<img src={characterImages.ObiWanKenobi} alt="Obi-Wan Kenobi" />
```

If you add or remove SVGs, keep `src/assets/character/index.ts` in sync (it is currently auto-managed in this repo).

## Project structure (important parts)

- `src/components` — UI components (cards, pagination, search)
- `src/services/Character` — API client and service methods to fetch SWAPI data
- `src/store` / `src/slice` — Redux store and slices (characters state)
- `src/assets/character` — SVGs and the aggregator
- `src/utils` — helper functions (formatters, image maps)

## Notes & next steps

- There's a placeholder entry for some characters (for example Anakin) without a matching SVG; add images to `src/assets/character` and export them from the aggregator.
- If you'd like, I can:
  - Replace all individual SVG imports across the codebase with the single aggregator import
  - Run a TypeScript check / `npm run build` and fix any issues

## License & contact

This is a sample/demo project. Add your license or author details here.
