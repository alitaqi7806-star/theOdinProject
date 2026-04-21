

### Dependencies vs devDependencies Cheat Sheet

| Aspect                          | **dependencies**                                      | **devDependencies**                                      |
|---------------------------------|-------------------------------------------------------|----------------------------------------------------------|
| **Definition**                  | Packages required for the app to run in production    | Packages needed only during development and building     |
| **Purpose**                     | Used by the final user-facing application             | Used by developers (testing, building, linting, etc.)    |
| **Installed with**              | `npm install <package>`                               | `npm install <package> --save-dev`                       |
| **Location in package.json**    | `"dependencies"` section                              | `"devDependencies"` section                              |
| **Included in production build**| Yes                                                   | No                                                       |
| **Example Packages**            | `lodash`, `axios`, `uuid`, `date-fns`                 | `vite`, `eslint`, `prettier`, `jest`, `tailwindcss`      |
| **When to use**                 | When the package is needed at runtime                 | When the package is only used during development         |
| **Impact on final bundle size** | Increases final bundle size                           | Does not increase final bundle size                      |
| **Installed when running**      | `npm install` (in production)                         | Only when running `npm install` in development           |

### Quick Decision Guide

| Question                                           | Answer → Use This Section      |
|----------------------------------------------------|--------------------------------|
| Will the user-facing app need this package?        | `dependencies`                 |
| Is this only for development (testing, building, formatting)? | `devDependencies`         |
| Is this a runtime library (e.g. utility functions)?| `dependencies`                 |
| Is this a build tool or testing framework?         | `devDependencies`              |

### Common Examples in Odin Projects

| Package                  | Type                | Reason |
|--------------------------|---------------------|--------|
| `lodash`                 | dependencies        | Used in the running app |
| `uuid`                   | dependencies        | Generates IDs at runtime |
| `vite`                   | devDependencies     | Development server & bundler |
| `eslint`                 | devDependencies     | Code linting during development |
| `prettier`               | devDependencies     | Code formatting tool |
| `jest`                   | devDependencies     | Testing framework |

### Useful npm Commands

| Command                                           | Effect |
|---------------------------------------------------|--------|
| `npm install <package>`                           | Adds to `dependencies` |
| `npm install <package> --save-dev`                | Adds to `devDependencies` |
| `npm install`                                     | Installs both `dependencies` and `devDependencies` |
| `npm install --production`                        | Installs only `dependencies` (for production) |

### Best Practices

- Keep `dependencies` as small as possible.
- Put everything related to building, testing, or formatting in `devDependencies`.
- Always use `--save-dev` flag for tools like Vite, ESLint, Prettier, etc.
- Run `npm install` after cloning any repository to get both types of dependencies.

