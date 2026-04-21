

### Webpack Concepts Cheat Sheet

| Concept                  | Definition                                                                 | Key Points |
|--------------------------|----------------------------------------------------------------------------|------------|
| **Entry**                | The starting point of your application (the file Webpack begins bundling from) | Usually `src/index.js`. Can have multiple entry points. |
| **Output**               | Where Webpack should emit the bundled files and what they should be named | Typically `dist/main.js`. Configured with `output.path` and `output.filename`. |
| **Loaders**              | Transform non-JavaScript files (CSS, images, Sass, etc.) into modules that Webpack can process | Example: `style-loader`, `css-loader`, `babel-loader` |
| **Plugins**              | Perform a wide range of tasks (optimization, asset management, injection of scripts, etc.) | More powerful than loaders. Examples: `HtmlWebpackPlugin`, `MiniCssExtractPlugin` |
| **Mode**                 | Tells Webpack which built-in optimizations to use (`development`, `production`, `none`) | `development` = fast builds with good debugging<br>`production` = optimized, minified bundles |
| **Module**               | Any file that Webpack can understand after loaders process it               | JS, CSS, images, fonts, etc. |
| **Dependency Graph**     | The internal map Webpack creates showing how modules depend on each other   | Webpack starts from the entry point and builds this graph |
| **Bundle**               | The final JavaScript file(s) that Webpack produces                         | Contains all your code + dependencies |
| **Chunk**                | A piece of the output bundle (can be multiple chunks in one bundle)         | Used for code splitting |

### Core Webpack Workflow

| Step | What Happens |
|------|--------------|
| 1    | Webpack reads the **entry** point |
| 2    | Builds a **dependency graph** by following `import`/`require` statements |
| 3    | Applies **loaders** to transform files (e.g. CSS → JS) |
| 4    | Applies **plugins** for additional processing |
| 5    | Outputs the final **bundle(s)** to the **output** directory |

### Most Important Configuration Options

| Option                  | Purpose | Typical Value |
|-------------------------|---------|---------------|
| `entry`                 | Starting file | `./src/index.js` |
| `output`                | Where to put the bundle | `{ path: path.resolve(__dirname, 'dist'), filename: 'bundle.js' }` |
| `module.rules`          | Define loaders | Array of rules for `.css`, `.js`, images, etc. |
| `plugins`               | Add plugins | Array of plugin instances |
| `mode`                  | Development or Production | `"development"` or `"production"` |

### Loaders vs Plugins

| Feature       | Loaders                                      | Plugins |
|---------------|----------------------------------------------|---------|
| Purpose       | Transform individual files                   | Perform broader tasks on the whole bundle |
| Timing        | During the bundling process                  | At different stages of the build |
| Example       | `css-loader`, `babel-loader`                 | `HtmlWebpackPlugin`, `CleanWebpackPlugin` |

### Quick Takeaways

- Webpack is a **static module bundler** — it takes your code and dependencies and turns them into optimized bundles.
- Everything starts from the **entry** point.
- **Loaders** transform files, **Plugins** do everything else.
- **Mode** (`development` vs `production`) drastically changes how Webpack behaves.
- The goal is to create a single (or few) optimized files that the browser can efficiently load.

