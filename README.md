# Lazone Expo + Medusa Starter (Monorepo)

Monorepo **Yarn workspaces** qui contient :

- `mobile/` : application mobile **Expo (expo-router)**.
- `medusa/` : backend **Medusa v2**.

## Prérequis

- Node.js (voir `medusa/package.json` pour la contrainte de version)
- Yarn Classic (v1)

## Installation

À la racine :

```bash
yarn install
```

## Démarrage

### Mobile (Expo)

```bash
yarn workspace mobile start
```

Raccourcis :

```bash
yarn workspace mobile ios
yarn workspace mobile android
yarn workspace mobile web
```

### Backend (Medusa)

Le nom du workspace Medusa est `medusa-starter-default`.

```bash
yarn workspace medusa-starter-default dev
```

Autres scripts utiles :

```bash
yarn workspace medusa-starter-default start
yarn workspace medusa-starter-default seed
```

### Docker (backend)

Les fichiers Docker sont dans `medusa/` (ex: `medusa/docker-compose.yml`).

## Qualité de code

### Lint

```bash
yarn lint
```

- `lint:medusa` lance ESLint depuis la racine sur `medusa/**/*.{js,ts,tsx}`
- `lint:mobile` délègue à `expo lint` via le workspace `mobile`

### Format

```bash
yarn format
```

Note: les fichiers Docker (`medusa/Dockerfile`, `medusa/docker-compose.yml`) sont exclus du formatage via `.prettierignore`.

## Git hooks

- Husky est activé via `yarn prepare`.
- Un hook `pre-commit` exécute `lint-staged`.

Si tu clones le repo et que les hooks ne sont pas actifs :

```bash
yarn prepare
```
