## How next.js uses turborepo?

[vercel/next.js](https://github.com/vercel/next.js)

[vercel/next.js/packages](https://github.com/vercel/next.js/packages)

...

---

## How Turborepo can be used for ADR

[Setup Next.js Project Fast](https://share.google/aimode/NYHRksqpFpN5w6aPi)

> Consider I'd like to setup a project that would have a next.js frontend (similar to next.js docs) and a project scaffolder similar to create-next-app. In next.js's case it is implemented within a turborepo monorepo. Is there a way that would allow to setup my project in a similar way quickly and easily?

Yes, you can set this up quickly and easily. The most efficient way to bootstrap a project exactly like this is by using the official [Turborepo Starter Template - Monorepo with Turborepo](https://vercel.com/templates/next.js/monorepo-turborepo) or its command-line initializer.

- [Creating a Next.js App in a Turborepo Monorepo](https://www.pronextjs.dev/workshops/next-js-production-project-setup-and-infrastructure-fq4qc/creating-a-next-js-app-in-a-turborepo-monorepo-plp5r)

- [turborepo.dev/docs/getting-started](https://turborepo.dev/docs/getting-started)
  - [Use create-turbo (Start with a template)](https://turborepo.dev/docs/getting-started/installation)  / [Add to an existing repository](https://turborepo.dev/docs/getting-started/add-to-existing-repository)
  - Use an example ([next.js](https://github.com/vercel/next.js))

By running a single command, you will get a pre-configured monorepo that contains Next.js applications and shared packages, matching the architectural layout that Vercel uses for Next.js itself. ([Monorepo with Turborepo](https://vercel.com/templates/next.js/monorepo-turborepo))


### 🛠️ Quick Setup Guide

To bootstrap your repository, open your terminal and run the initializer command using your preferred package manager:

```bash
# Using pnpm (Recommended for Monorepos)
pnpm dlx create-turbo@latest

# Using npm
npx create-turbo@latest

# Using bun
bunx create-turbo@latest
```

### 📂 How to Structure Your Repo

During the setup wizard, name your project workspace. Once completed, you will get a folder structure explicitly built for this use case:

- **apps/docs**: This will serve as your Next.js documentation or marketing frontend. You can configure it to look and behave just like the Next.js documentation platform.
- **apps/cli** (or rename `apps/web`): This is where you will build your project scaffolder CLI tool (your version of create-next-app). You can write it in TypeScript and use Node.js CLI packages like commander, inquirer, or clack to handle user input.
- **packages/**: This directory holds shared configurations (like `@repo/eslint-config`, `@repo/typescript-config`) and components (`@repo/ui`), making it seamless to manage tools across your CLI and web apps.

### 🚀 Key Benefits of This Setup

- **Simultaneous Development**: You can run turbo dev from the root directory to instantly run your frontend application while testing your CLI logic concurrently.
- **Shared Typings and Utilities**: If your CLI generator outputs standard templates, you can host those template files or metadata inside a shared package under packages/templates, allowing your apps/docs frontend to showcase them and your apps/cli to pull from them directly.
- **Blazing Fast Builds**: Turborepo uses advanced caching mechanisms, meaning it will skip rebuilding parts of your project that haven't changed, significantly speeding up your local work and CI/CD pipelines.

Would you like assistance with **structuring the CLI package logic** inside the monorepo, or are you looking for recommendations on **interactive CLI libraries** to build the questionnaire flow?
