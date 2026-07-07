# Tailwind CSS Setup Guide

## 1. Create Project & Install Tailwind

```bash
mkdir my-project
cd my-project
npm init -y
npm install -D tailwindcss
```

## 2. Create Config File

```bash
npx tailwindcss init
```

## 3. Configure Content Paths

Edit `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## 4. Create Input CSS

Create `src/input.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 5. Build CSS

```bash
npx tailwindcss -i ./src/input.css -o ./src/output.css
```

To watch for changes automatically:

```bash
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch
```

## 6. Link CSS in HTML

```html
<link rel="stylesheet" href="src/output.css">
```

## 7. Use Tailwind Classes

```html
<div class="text-red-500 bg-purple-500">
    Hello world!
</div>
```

## NPM Scripts (Optional)

Add to `package.json` for convenience:

```json
"scripts": {
    "build": "tailwindcss -i ./src/input.css -o ./src/output.css",
    "watch": "tailwindcss -i ./src/input.css -o ./src/output.css --watch"
}
```

Then run:

```bash
npm run build
npm run watch
```
