# v0.1.0

Make the first version as easy as possible - just scaffold the file structure same as current latest ADR (make a release first) and release it as v0.1.0

## Prompt:

For a project Architecture Decision Records: 
https://github.com/skyisuniverse/architecture-decision-records

I want to create a project scaffolding tool similar to next.js's:
npx create-next-app@latest

that would allow to scaffold a project with one cli command. Next.js uses for it a package create-next-app that is kept within next.js/packages/ folder : 
https://github.com/vercel/next.js/tree/canary/packages/create-next-app

and also published as an npm package: 
https://www.npmjs.com/package/create-next-app


----

Questions:

1. Within next.js monorepo:
  - how is the main frontend built?
  - how is create-next-app published? What tools / commands does next.js use for building and publishing?

2. How can I implement similar functionality for ADR? (e.g. a **create-adr-app** project scaffolder and npm package publishing?)

----

## Solution:

- Monorepo file structure with **turbopack** (similar to next.js) ? 
- With **packages/create-adr-app** for scaffolding? (published to npm as a package)
