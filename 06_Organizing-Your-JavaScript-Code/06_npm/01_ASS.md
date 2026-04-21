

### npm, Packages & Dependencies – Cheat Sheet

| Topic                        | Definition / Explanation                                                                 | Key Points & Examples |
|-----------------------------|------------------------------------------------------------------------------------------|-----------------------|
| **npm**                     | Node Package Manager – the world’s largest software registry and command-line tool       | Used to install, manage, and share JavaScript packages |
| **package.json**            | The manifest file for your project. Contains metadata, scripts, and dependencies         | Created with `npm init -y` |
| **Package**                 | A reusable piece of JavaScript code published to the npm registry                        | Example: `lodash`, `date-fns`, `uuid` |
| **Dependency**              | A package your project needs to function                                                 | Listed in `package.json` |
| **devDependency**           | Packages needed only during development (testing, building, linting, etc.)               | Example: `vite`, `eslint`, `prettier` |
| **Semantic Versioning**     | Versioning system: `major.minor.patch`                                                   | `^1.2.3` = compatible updates, `~1.2.3` = patch updates only |

### Core npm Commands

| Command                              | Purpose                                                      | Example |
|--------------------------------------|--------------------------------------------------------------|---------|
| `npm init -y`                        | Create a default `package.json` file                         | `npm init -y` |
| `npm install <package>`              | Install a package and add it to `dependencies`               | `npm install lodash` |
| `npm install <package> --save-dev`   | Install as a development dependency                          | `npm install vite --save-dev` |
| `npm uninstall <package>`            | Remove a package                                             | `npm uninstall lodash` |
| `npm update`                         | Update packages to latest compatible versions                | `npm update` |
| `npm run <script>`                   | Run a script defined in `package.json`                       | `npm run dev` |
| `npm install`                        | Install all dependencies listed in `package.json`            | `npm install` |

### package.json Key Fields

| Field                        | Purpose |
|------------------------------|--------|
| `name`                       | Name of your project |
| `version`                    | Current version of your project |
| `description`                | Short description |
| `main`                       | Entry point (usually `index.js`) |
| `scripts`                    | Custom commands (`"dev": "vite"`, `"build": "vite build"`) |
| `dependencies`               | Production dependencies |
| `devDependencies`            | Development-only dependencies |
| `type`                       | `"module"` → enables ES6 `import/export` syntax |

### Dependencies vs devDependencies

| Type              | When to Use                                      | Installed When? | Typical Packages |
|-------------------|--------------------------------------------------|-----------------|------------------|
| **dependencies**  | Needed for the app to run in production          | Always          | `lodash`, `axios`, `uuid` |
| **devDependencies** | Only needed during development & building      | Development     | `vite`, `eslint`, `prettier`, `jest` |

### Version Specifiers

| Specifier     | Meaning                                      | Example |
|---------------|----------------------------------------------|---------|
| `^` (caret)   | Compatible with newer minor and patch versions | `^1.2.3` |
| `~` (tilde)   | Compatible with newer patch versions only    | `~1.2.3` |
| `*`           | Any version                                  | `*` |
| `latest`      | Latest available version                     | `latest` |

### Best Practices Summary

| Practice                              | Recommendation |
|---------------------------------------|----------------|
| Always use `package.json`             | Never install packages without saving them |
| Prefer `^` for most dependencies      | Allows minor updates while staying safe |
| Keep `dependencies` minimal           | Only include packages actually used in production |
| Run `npm install` after cloning       | Ensures all dependencies are installed |
| Use meaningful script names           | `"dev"`, `"build"`, `"start"`, `"test"` |

### Quick Starter Commands

```bash
npm init -y                    # Create package.json
npm install lodash             # Production dependency
npm install vite --save-dev    # Development dependency
npm run dev                    # Run a script
```
