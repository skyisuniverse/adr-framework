https://nx.dev/docs/features/automate-updating-dependencies

The nx migrate command **automates updating your Nx workspace and plugins through the official [Nx CLI Command Reference](https://nx.dev/docs/reference/nx-commands)**. It runs in two distinct phases: generating version updates and package changes, followed by executing the actual code and config transformations.

Standard Migration Steps

- **Generate Updates**: Run `npx nx migrate latest` (or specify a target version) to analyze your workspace, update `package.json`, and generate a `migrations.json` file.

[A New UI for Nx Migration](https://nx.dev/blog/migrate-ui)

[Nx 23: 4x Faster Nx Agents, Agentic Nx Migrate, improved targetDefaults, .Net GA](https://nx.dev/blog/nx-23-release)

[Automate Updating Dependencies](https://nx.dev/docs/features/automate-updating-dependencies)

- **Install Packages**: Install the updated dependencies using your package manager (`npm install`, `yarn`, `pnpm`, or `bun`).

- **Run Migrations**: Execute `npx nx migrate --run-migrations` to apply code and configuration changes across your projects.

- **Clean Up**: Review your git diff, test your application, and delete the temporary `migrations.json` file.

[Advanced Update Process](https://nx.dev/docs/guides/tips-n-tricks/advanced-update)

[Nx Updates and Migration](https://www.youtube.com/watch?v=TRqPMi84Sgw)

## Common Options & Alternatives

- **Target Version**: Pass a specific version like `npx nx migrate 18.0.0` instead of `latest`.

- **Visual UI**: Use the `Nx Console` extension in VS Code or Cursor to run migrations via a dedicated sidebar UI. [Nx Console Migrate UI](https://nx.dev/docs/kb/console-migrate-ui)

- **Granular Control**: Use `--include=required` or `--create-commits` flags for more isolated or multi-major step updates.

If you are running into an issue, let me know:

- **What version** of Nx you are currently on and what version you are trying to reach
- **Any error messages** or failing checks during npm install or --run-migrations
