[factory.com's Next.js WIKI](https://factory.com/open-source-wikis/next-js)

[Open-Source Wikis / Next.js / Packages / create-next-app](https://factory.com/open-source-wikis/next-js?page=packages%2Fcreate-next-app.md)

[Open-Source Wikis / Next.js / Turbopack](https://factory.com/open-source-wikis/next-js?page=turbopack%2Findex.md)

---

# Next.js solution

> Within next.js monorepo ( https://github.com/vercel/next.js ): - how is create-next-app package published to npm? What mechanism / tools / commands does next.js use for publishing?https://github.com/vercel/next.js/tree/canary/packages/create-next-app

Within the Next.js monorepo, the [create-next-app](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) package is published alongside all [other core monorepo packages](https://github.com/vercel/next.js/tree/canary/packages) (such as `next`, `@next/font`, etc.) **using a custom automated release workflow** rather than off-the-shelf monorepo publishing tools like Lerna or Changesets.

([factory.com's Next.js WIKI: Tooling](https://factory.com/open-source-wikis/next-js?page=how-to-contribute%2Ftooling.md)) (??)

The release and publishing pipeline is orchestrated by the following mechanisms, tools, and commands:

## 1. Automation Platform: GitHub Actions

All publishing actions are driven through continuous integration (CI) via GitHub Actions.

[vercel/next.js/.github](https://github.com/vercel/next.js/tree/canary/.github)

- Trigger: The publication happens during the execution of the main **build_and_deploy.yml** workflow.
  - [vercel/next.js/.github/workflows/build_and_deploy.yml](https://github.com/vercel/next.js/blob/canary/.github/workflows/build_and_deploy.yml)
- **Authentication**: It authenticates against npm securely using a repository secret token ($NPM_TOKEN), which is dynamically injected into the CI environment's global configuration file (`~/.npmrc`) right before triggering publication.

## 2. Core Publishing Mechanism: Custom Scripts

Instead of running a standard `npm publish` across the workspace directly, Next.js implements **custom internal tooling** built with **JavaScript** to handle **versioning**, **cross-dependencies**, and **publishing**.

The critical step in the workflow runs the following script:

```bash
./scripts/publish-release.js
```

[vercel/next.js/scripts/publish-release.js](https://github.com/vercel/next.js/blob/canary/scripts/publish-release.js)

## 3. How publish-release.js Works Behind the Scenes

When a release is triggered (e.g., a new canary tag or full production tag is cut), the publish-release.js tool executes the following lifecycle:

- **Dependency Synchronization**: It scans the packages under the packages/* workspace directory (including `packages/create-next-app`). It programmatically ensures that the versions of internal package dependencies (such as how `create-next-app` targets or pairs with specific `next` framework features) are strictly aligned and pinned correctly.

- **Execution Command**: The script programmatically fires an underlying npm publishing command on each workspace bundle. It enforces modern publishing standards, configuring flags for **npm provenance** (pinning specific versions like npm@10.4.0 or later during CI execution to structurally prove the build's origin securely on the registry).

- **Tag Enforcement**: It determines whether the package needs to be pushed with a standard tag (`latest`) or a pre-release flag (`canary`), mapping directly to the branch context that triggered the workflow.

---

If you are planning to set up a similar system, let me know:
- Are you looking to **replicate this exact behavior** in your own monorepo?
- What **package manager** (pnpm, Yarn, npm) are you currently using?
- Do you want to implement **provenance or canary/pre-release tags**?
