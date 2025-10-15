# Webpack & Tailwind Starter

Build apps with Webpack and use Tailwind CSS

## Usage

### Install dependencies

```
npm Install
```

### Build for production

```
npm run build
```

### Run the development server (:3000)

```
npm run dev
```

What is PostCSS? PostCSS is like a pipeline for your CSS — you write CSS (or Sass), PostCSS runs tools like autoprefixer, minifier, or Tailwind, and outputs fast, browser-ready CSS.
It doesn’t style your page by itself —
it’s a processor that reads your CSS, runs it through one or more plugins, and then outputs the final CSS that browsers understand. 
PostCSS doesn’t “compile” like Sass does; instead, it processes CSS — applying rules, optimizations, and transformations via plugins.

You can use it to:
Autoprefix CSS for browser compatibility
Minify and optimize CSS for production
Use modern CSS features (nesting, variables, etc.)
Integrate frameworks like Tailwind CSS

Tailwind uses PostCSS under the hood.
When you install Tailwind, you’ll see a postcss.config.js automatically created.
So when you run:
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
→ Tailwind runs as a PostCSS plugin that expands all utility classes into actual CSS.

webpack vs npm
NPM is A package manager. It downloads and manages external libraries (dependencies).
Webpack is a module bundler. It	takes all your code and assets and bundles them into optimized files for the browser.

npm Scripts Often Call Webpack
{
  "scripts": {
    "build": "webpack --mode production",
    "dev": "webpack serve --mode development"
  }
}
You then run:
npm run dev


What does CSS-Loader, Post CSS-Loader and Style Loader do? What is the difference between them?
postcss-loader	Runs CSS through PostCSS plugins (like autoprefixer, Tailwind, cssnano). It	Processes CSS for optimization or transformation.
css-loader: Tells Webpack how to read and bundle CSS files. It Converts CSS into JavaScript modules. Webpack is a JavaScript module bundler. It knows how to bundle JS files by default — but not CSS. It is the css-loader that lets Webpack how to read and bundle CSS files..
style-loader: Takes processed CSS and injects it into the browser DOM.	Adds <style> tags dynamically in runtime
Execution order:
postcss-loader → css-loader → style-loader
1️. postcss-loader → runs PostCSS plugins (autoprefixer, etc.)
2️. css-loader → turns CSS into JS modules
3️. style-loader → injects those styles into <style> tags in the browser
