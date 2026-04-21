

### package.json Cheat Sheet

| Section / Field               | Description                                                                 | Example / Common Values |
|-------------------------------|-----------------------------------------------------------------------------|-------------------------|
| **name**                      | Name of your project (must be lowercase, no spaces)                         | `"tic-tac-toe"` or `"library-app"` |
| **version**                   | Current version of your project (semantic versioning)                       | `"1.0.0"` |
| **description**               | Short description of what the project does                                  | `"A browser-based Tic-Tac-Toe game"` |
| **main**                      | Entry point file (usually not critical for front-end projects)              | `"index.js"` |
| **type**                      | Defines module system (`"module"` enables ES6 `import/export`)              | `"module"` (recommended) |
| **scripts**                   | Custom commands you can run with `npm run <name>`                           | `"dev": "vite", "build": "vite build"` |
| **dependencies**              | Packages required for the app to run in production                          | `"lodash": "^4.17.21"` |
| **devDependencies**           | Packages needed only during development (testing, building, linting)        | `"vite": "^5.0.0"` |
| **keywords**                  | Array of keywords to help people find your package on npm                   | `["game", "tic-tac-toe"]` |
| **author**                    | Your name or username                                                       | `"Your Name"` |
| **license**                   | License type (commonly MIT for learning projects)                           | `"MIT"` |

### Most Important Fields for Odin Projects

| Field              | Why It Matters | Typical Value for Your Projects |
|--------------------|----------------|---------------------------------|
| **name**           | Identifies your project | `"tic-tac-toe"` or `"dashboard"` |
| **type**           | Enables modern ES6 `import/export` syntax | `"module"` |
| **scripts**        | Allows you to run commands easily with `npm run` | `"dev": "vite"` |
| **dependencies**   | Production packages (rarely needed early on) | Usually empty at first |
| **devDependencies**| Development tools (Vite, etc.) | Added when you install build tools |

### Common npm Scripts You’ll Use

| Script Name     | Command Example               | Purpose |
|-----------------|-------------------------------|---------|
| `dev`           | `npm run dev`                 | Start development server |
| `build`         | `npm run build`               | Create production build |
| `preview`       | `npm run preview`             | Preview the built version |
| `start`         | `npm start`                   | Run the final app |

### Quick Commands Reference

| Command                                 | What It Does |
|-----------------------------------------|--------------|
| `npm init -y`                           | Creates a default `package.json` |
| `npm install`                           | Installs all dependencies listed in `package.json` |
| `npm install <package>`                 | Installs a package and adds it to `dependencies` |
| `npm install <package> --save-dev`      | Installs a package and adds it to `devDependencies` |

### Best Practices Summary

- Always keep `type: "module"` for modern ES6 syntax (`import` / `export`).
- Use clear, kebab-case names for your project (`tic-tac-toe`, `restaurant-page`).
- Add useful scripts (`dev`, `build`) early.
- Keep `dependencies` minimal — only add what your app actually needs in production.
- Never commit `node_modules` folder (it should be ignored via `.gitignore`).

