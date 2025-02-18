![OrbitKit](https://github.com/ixahmedxi/orbitkit/blob/main/cover.png?raw=true)

## Note

> [!IMPORTANT]
> OrbitKit is built on top of a very opinionated tech stack, which might not work for every use case/business idea. I offer monorepo architecture consulting or even building something completely custom for you, if you are interested be sure to [DM me on X/Twitter](https://twitter.com/ixahmedxii).

## Features

- Next.js Web Application
- Astro Marketing Website
- File uploads with Uploadthing
- ESM Only
- TailwindCSS
- Lucia auth with github and google oauth
- Typesafe Next.js routes
- Drizzle ORM
- Neon DB
- Rate limiting with [Unkey](https://unkey.dev)
- Dedicated ShadCN UI primitives package
- Storybook
- Radix UI Colors for auto light/dark mode
- Next themes
- Shared tooling configuration
- Spell checking
- Markdown linting
- Turborepo task caching
- ESLint for linting
- Prettier formatting
- Commitlint with pnpm scopes
- Lint staged
- Husky
- TS Reset for the applications
- Packages built using tsup

And much more!

## Todos

OrbitKit is not in final form yet, there are many things in the plans for it but it is in a usable primitive state. Checkout the [Roadmap](https://github.com/users/ixahmedxi/projects/6) for more info.

## Getting Started

### Installation

```bash
# Clone the repository
git clone --depth 1 https://github.com/ixahmedxi/orbitkit.git <your-project-name>

#or use
npx degit ixahmedxi/orbitkit

# Install Dependencies
pnpm install
```

### Setting up environment variables

Checkout the `.env.example` file inside the `apps/web` directory for the environment variables you need to get the project running. You should create an UploadThing and Neon DB accounts and copy the environment variables from their dashboard to a `.env.local` file in `apps/web`.

You will also need to create a GitHub Oauth token as well as for Google authentication as well.

### Explaining the architecture

- `apps` folder is where the applications live like the Next.js app and the Astrojs marketing website
- `packages/config` folder is where packages that configure and ship out presets of tool configuration throughout the monorepo, for example `packages/config/tailwind` that ships out a tailwind configuration preset as the single source of truth.
- `packages` hosts all of the packages that get consumed by applications, for example `packages/ui` that ships all of Shadcn UI primitives, some packages are internal (meaning they do not have a build step like the auth package) and some do like the ui package.
- There is a core package, `packages/core` that is empty and should be used for business logic sharing.
- `packages/env` is where we define the environment variable types, it is an internal package that gets away with not needing a build step by using `jiti` to run the typescript file in the `next.config.js` file of the web application.

### Running the project

```bash
# Dev
pnpm turbo dev

# Build
pnpm turbo build

# Typecheck
pnpm turbo typecheck

# Lint
pnpm turbo lint

# Storybook
pnpm turbo storybook

# Start apps in production mode
pnpm turbo start
```

If you're familiar with turborepo / pnpm workspaces, running stuff around this repo will be easy to figure out.

## Issues

If you have any issues / problems with using OrbitKit, be sure to create an issue here on GitHub and I will help you out with it.
