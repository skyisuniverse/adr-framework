# Monorepo (frontends + scaffolder)

[turborepo.dev Crafting your repository](https://turborepo.dev/docs/crafting-your-repository)

1. Structuring a repository
Design the directory structure of your monorepo.

2. Managing dependencies
Using dependencies for sharing code

3. Creating an internal package
Make a package in your repository

4. Configuring tasks
Design your task patterns

5. Running tasks
Run tasks as fast as possible

6. Caching
Never do the same work twice

7. Developing apps
Run many apps in parallel

8. Using environment variables
Account for variables in your environment

9. Constructing CI
Ship your applications

10. Upgrading
Upgrading your Turborepo version

11. Understanding your repository
Understanding your codebase with Turborepo

---

## Packages (frontends / backends / etc.) + Scaffolder

...

---

- [create-next-app](https://github.com/vercel/next.js/tree/canary/packages/create-next-app)
  - project scaffolder
- [devlow-bench](https://github.com/vercel/next.js/tree/canary/packages/devlow-bench)
  - DEVeloper workfLOW BENCHmarking tool used to run, record, and compare internal workflow performance scenarios inside the Next.js ecosystem.
- [eslint-config-next](https://github.com/vercel/next.js/tree/canary/packages/eslint-config-next)
  - The standard ESLint configuration package that ships out-of-the-box with Next.js projects to enforce core code quality rules
- [eslint-plugin-internal](https://github.com/vercel/next.js/tree/canary/packages/eslint-plugin-internal)
  - ESLint rules tailored for internal use within the Next.js monorepo codebase.
- [eslint-plugin-next](https://github.com/vercel/next.js/tree/canary/packages/eslint-plugin-next)
  - Official ESLint plugin providing linting rules specifically for Next.js applications (e.g., catching unoptimized images or bad link patterns).
- [font](https://github.com/vercel/next.js/tree/canary/packages/font)
  - Built-in automatic self-hosting font utilities (@next/font) that optimize Google Fonts and local custom web fonts to prevent layout shift.
- [next-bundle-analyzer](https://github.com/vercel/next.js/tree/canary/packages/next-bundle-analyzer)
  - Webpack bundle analyzer plugin (@next/bundle-analyzer) used to visually map and review production bundle sizes.
- [next-codemod](https://github.com/vercel/next.js/tree/canary/packages/next-codemod)
  - Automated script runner for migrating and updating Next.js codebases when breaking changes or API updates occur.
- [next-env](https://github.com/vercel/next.js/tree/canary/packages/next-env)
  - Internal environment variable utility built to load and prioritize .env files within Next.js.
- [next-mdx](https://github.com/vercel/next.js/tree/canary/packages/next-mdx)
  - Official integration plugin (@next/mdx) allowing Next.js applications to compile Markdown and MDX files into standard pages.
- [next-playwright](https://github.com/vercel/next.js/tree/canary/packages/next-playwright)
  - Experimental Playwright testing helpers for asserting features like Instant Navigation behavior in Next.js web applications.
- [next-plugin-storybook](https://github.com/vercel/next.js/tree/canary/packages/next-plugin-storybook)
  - Experimental plugin layer designed to make Next.js setups compatible with Storybook component isolation environments.
- [next-polyfill-module](https://github.com/vercel/next.js/tree/canary/packages/next-polyfill-module)
  - Polyfill builder layer compiled for modern ES module JavaScript targets in older browsers.
- [next-polyfill-nomodule](https://github.com/vercel/next.js/tree/canary/packages/next-polyfill-nomodule)
  - Fallback polyfill bundler designated for legacy browser compatibility engines.
- [next-routing](https://github.com/vercel/next.js/tree/canary/packages/next-routing)
  - Experimental internal compiler routing core created to handle server adapter routing layouts and dynamic paths.
- [next-rspack](https://github.com/vercel/next.js/tree/canary/packages/next-rspack)
  - Partnered experimental build connector built for using the fast Rspack Rust-based bundler instead of traditional Webpack inside Next.js.
- [next-swc](https://github.com/vercel/next.js/tree/canary/packages/next-swc)
  - Rust-based Next.js native compiler engine (built on SWC) used for fast minification, transpilation, and build piping.
- [next](https://github.com/vercel/next.js/tree/canary/packages/next)
  - The primary Next.js framework core code engine containing all the runtime routing, server-rendering, and operational logic.
- [react-refresh-utils](https://github.com/vercel/next.js/tree/canary/packages/react-refresh-utils)
  - Developer utility wrappers hook-wired to handle hot reloading and React Fast Refresh states safely inside the development compiler.
- [third-parties](https://github.com/vercel/next.js/tree/canary/packages/third-parties)
  - A component toolkit library (`@next/third-parties`) providing high-performance wrapper integrations for popular external services like Google Tag Manager, YouTube Embeds, and Google Maps.

Let me know if you would like me to unpack the **usage commands** or show you **how to configure** any specific package from this list!
