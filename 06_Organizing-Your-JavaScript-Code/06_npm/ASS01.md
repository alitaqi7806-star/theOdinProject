
### Installing Packages with npm – Cheat Sheet

| Task                                | Command                                              | When to Use |
|-------------------------------------|------------------------------------------------------|-------------|
| **Initialize a project**            | `npm init -y`                                        | First step when starting a new project (creates `package.json`) |
| **Install a package** (production)  | `npm install <package-name>`                         | When the package is needed for the app to run (e.g. `lodash`, `uuid`) |
| **Install as dev dependency**       | `npm install <package-name> --save-dev`              | For tools used only during development (e.g. `vite`, `eslint`) |
| **Install from package.json**       | `npm install`                                        | After cloning a repo or deleting `node_modules` |
| **Install a specific version**      | `npm install <package>@<version>`                    | `npm install lodash@4.17.21` |
| **Update packages**                 | `npm update`                                         | Updates packages within the version range in `package.json` |
| **Uninstall a package**             | `npm uninstall <package-name>`                       | Removes package and updates `package.json` |

### Important Flags

| Flag                    | Meaning |
|-------------------------|--------|
| `--save` (default)      | Adds to `dependencies` (production) |
| `--save-dev` or `-D`    | Adds to `devDependencies` |
| `--global` or `-g`      | Installs globally (usually for CLI tools) |
| `--save-exact`          | Installs exact version (no `^` or `~`) |

### package.json Sections Explained

| Section              | Purpose |
|----------------------|--------|
| `dependencies`       | Packages required for the app to run in production |
| `devDependencies`    | Packages only needed during development (build tools, testing, linting) |
| `scripts`            | Custom commands you can run with `npm run <name>` |

### Common npm Workflow

| Step | Command | Purpose |
|------|---------|--------|
| 1    | `npm init -y` | Create `package.json` |
| 2    | `npm install lodash` | Add production package |
| 3    | `npm install vite --save-dev` | Add development tool |
| 4    | `npm run dev` | Run a script defined in `package.json` |

### Useful npm Scripts (Common Names)

| Script Name     | Typical Command                     | Purpose |
|-----------------|-------------------------------------|--------|
| `dev`           | `vite` or `vite dev`                | Start development server |
| `build`         | `vite build`                        | Create production build |
| `start`         | `node server.js`                    | Run the app |
| `test`          | `jest`                              | Run tests |

### Quick Tips

- Always run `npm install` after cloning a repository.
- Never commit the `node_modules` folder (it should be in `.gitignore`).
- Use `^` (caret) for most dependencies to allow minor updates.
- Prefer `npm install <package> --save-dev` for tools like Vite, ESLint, etc.

