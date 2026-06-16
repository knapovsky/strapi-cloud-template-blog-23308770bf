# Strapi Cloud Template Blog

A Strapi v4 blog CMS project generated from the Strapi blog template. It includes content types for articles, authors, categories, global site settings, SEO components, seeded demo content, and upload assets.

> Maintenance notice: this repository was generated from an older Strapi template. Before public deployment, upgrade dependencies, run an audit, and review secrets/configuration.

## Features

- Strapi v4 headless CMS
- blog-oriented content model
- article collection type with draft/publish support
- author and category relations
- global site settings single type
- reusable shared components for media, quotes, rich text, sliders, and SEO
- GraphQL plugin enabled
- users-permissions and i18n plugins included
- SQLite via `better-sqlite3` for simple local development
- seeded demo data and upload assets under `data/`

## Technology stack

- Node.js >= 16 and <= 20, as defined in `package.json`
- npm >= 6 or Yarn
- Strapi 4.13.6
- SQLite / `better-sqlite3`
- GraphQL plugin

## Repository structure

```text
.
├── config/                   # Strapi server, database, middleware, API config
├── data/                     # Template seed data and sample uploaded images
├── database/migrations/      # Migration placeholder
├── public/                   # Public assets and upload placeholder
├── src/
│   ├── admin/                # Optional admin customisation examples
│   ├── api/                  # Content types, controllers, routes, services
│   │   ├── about/
│   │   ├── article/
│   │   ├── author/
│   │   ├── category/
│   │   └── global/
│   ├── components/shared/    # Reusable content components
│   ├── extensions/           # Strapi extension placeholder
│   ├── bootstrap.js
│   └── index.js
├── .env.example              # Example environment variables
├── package.json
├── yarn.lock
└── README.md
```

## Content model

The template defines these main content types:

- `Article` — blog posts with title, short description, slug, cover media, author, category, and dynamic content blocks
- `Author` — author profile data and related articles
- `Category` — article categorisation
- `About` — about-page content
- `Global` — site-wide name, description, favicon, and default SEO metadata

Reusable shared components:

- `shared.media`
- `shared.quote`
- `shared.rich-text`
- `shared.slider`
- `shared.seo`

## Local setup

1. Install dependencies:

   ```bash
   npm install
   ```

   or, if you prefer Yarn:

   ```bash
   yarn install
   ```

2. Create a local `.env` from the example:

   ```bash
   cp .env.example .env
   ```

3. Replace every placeholder secret in `.env` with real random values.

4. Start the development server:

   ```bash
   npm run develop
   ```

   or:

   ```bash
   yarn develop
   ```

5. Open the Strapi admin panel at:

   ```text
   http://localhost:1337/admin
   ```

## Available scripts

```bash
npm run develop   # Start Strapi with auto-reload
npm run start     # Start Strapi without auto-reload
npm run build     # Build the admin panel
npm run strapi    # Run the Strapi CLI
```

Yarn equivalents:

```bash
yarn develop
yarn start
yarn build
yarn strapi
```

## Environment variables

`.env.example` documents the required values:

```text
HOST=0.0.0.0
PORT=1337
APP_KEYS=...
API_TOKEN_SALT=...
ADMIN_JWT_SECRET=...
TRANSFER_TOKEN_SALT=...
JWT_SECRET=...
```

Generate strong unique values for every secret before running outside a disposable local environment.

## Deployment checklist

Before deploying publicly:

- upgrade Strapi and official plugins to supported versions
- run `npm audit` or an equivalent dependency scan
- rotate all local/admin/API/JWT secrets
- confirm `.env` is not committed
- review CORS, middleware, upload, and database configuration
- configure a production database instead of local SQLite if required
- rebuild the admin panel with `npm run build`
- review seeded demo content and uploaded images
- configure backups for database and uploads

## Security notes

Do not commit real `.env` files, production databases, generated build caches, private uploads, API tokens, or admin credentials. The current `.env.example` is intentionally sanitized.

## License

`package.json` declares this project as MIT licensed. Review Strapi and plugin licenses before redistribution or commercial deployment.
