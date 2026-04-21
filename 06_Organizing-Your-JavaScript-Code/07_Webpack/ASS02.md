

### Webpack Asset Management Cheat Sheet

| Asset Type       | Loader / Technique                          | Configuration Example | Notes |
|------------------|---------------------------------------------|-----------------------|-------|
| **JavaScript**   | Built-in (no loader needed)                 | —                     | Webpack handles JS files by default |
| **CSS**          | `css-loader` + `style-loader`               | `{ test: /\.css$/, use: ['style-loader', 'css-loader'] }` | `style-loader` injects CSS into the DOM |
| **CSS** (Production) | `css-loader` + `MiniCssExtractPlugin`   | Use `MiniCssExtractPlugin.loader` instead of `style-loader` | Extracts CSS into separate `.css` files |
| **Images**       | `asset/resource` (Webpack 5+)               | `{ test: /\.(png\|jpg\|gif)$/, type: 'asset/resource' }` | Emits file and returns URL |
| **Images**       | `asset/inline`                              | `{ test: /\.(png\|jpg)$/, type: 'asset/inline' }` | Inlines as base64 data URL |
| **Images**       | `asset` (auto)                              | `{ test: /\.(png\|jpg)$/, type: 'asset' }` | Automatically chooses inline or resource based on size |
| **Fonts**        | `asset/resource`                            | `{ test: /\.(woff\|woff2\|ttf)$/, type: 'asset/resource' }` | Emits font files to output folder |
| **SVG**          | `asset/resource` or `asset/inline`          | Same as images        | Can be inlined or emitted as file |
| **Other Assets** | `asset/resource`                            | `{ test: /\.(pdf\|doc)$/, type: 'asset/resource' }` | Generic file handling |

### Recommended Webpack 5 Asset Rules

| Asset Type          | Recommended Rule (Webpack 5) |
|---------------------|------------------------------|
| Images              | `type: 'asset'` (auto) or `type: 'asset/resource'` |
| Fonts               | `type: 'asset/resource'` |
| SVGs                | `type: 'asset/resource'` or `type: 'asset/inline'` |
| JSON                | Built-in support (no loader needed) |
| CSS                 | `css-loader` + `style-loader` (dev) or `MiniCssExtractPlugin` (prod) |

### Basic webpack.config.js Example (Asset Management)

```js
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
    clean: true
  },
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader']
      },
      {
        test: /\.(png|jpg|gif|svg)$/i,
        type: 'asset/resource'
      },
      {
        test: /\.(woff|woff2|ttf|eot)$/i,
        type: 'asset/resource'
      }
    ]
  }
};
```

### Key Concepts Summary

| Concept                    | Explanation |
|----------------------------|-----------|
| **Asset Modules**          | Webpack 5+ built-in way to handle files (replaces `file-loader`, `url-loader`) |
| **type: 'asset'`**         | Automatic choice between inline and separate file based on size |
| **type: 'asset/resource'`**| Always emits a separate file and returns URL |
| **type: 'asset/inline'`**  | Always inlines as base64 data URL |
| **Loaders**                | Transform source files before bundling (e.g. CSS → JS) |
| **Plugins**                | Extend Webpack functionality (e.g. extract CSS, generate HTML) |

### Quick Tips

- Use `type: 'asset/resource'` for most images and fonts in production.
- Use `style-loader` during development for fast HMR (Hot Module Replacement).
- Use `MiniCssExtractPlugin` in production for better performance.
- Always set `output.clean: true` to clean the `dist` folder before each build.

