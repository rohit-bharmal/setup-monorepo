# setup-monorepo
---

````markdown
# Nx Monorepo: React + TypeScript (TSX) Components

This monorepo is built using [Nx](https://nx.dev/) to manage scalable front-end projects with **React**, **TypeScript**, and optionally **Tailwind CSS**. Ideal for component libraries, multi-app setups, and shared utilities.

---

## 📦 Tech Stack

- [Nx](https://nx.dev/)
- [React](https://react.dev/)
- [TypeScript (TSX)](https://www.typescriptlang.org/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/) *(optional)*
- [Jest](https://jestjs.io/) (unit testing)
- [ESLint](https://eslint.org/) + [Prettier](https://prettier.io/)

---

## 🧱 Monorepo Structure

```txt
apps/
  my-app/             # Example React application
libs/
  ui/                 # Shared React components (TSX)
  utils/              # Shared utilities and helpers
````

---

## 🚀 Getting Started

### 1. Install Nx CLI

```bash
npm install -g nx
```

### 2. Create Workspace

```bash
npx create-nx-workspace@latest my-monorepo
```

**During setup:**

* Choose: `apps and libs`
* Choose: `React` as the framework
* Name your app (e.g., `my-app`)
* Choose: `Vite` as the bundler
* Enable TypeScript, ESLint, and testing

### 3. Navigate to Project

```bash
cd my-monorepo
```

### 4. Serve the App

```bash
nx serve my-app
```

---

## 🧩 Generating Libraries and Components

### Generate a React Library

```bash
nx generate @nx/react:library ui
```

### Generate a Component in the Library

```bash
nx generate @nx/react:component button --project=ui
```

---

## 🎨 Optional: Tailwind CSS Setup

To enable Tailwind CSS in your Nx workspace:

### 1. Install Tailwind

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### 2. Configure Tailwind

Edit `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './apps/**/*.{js,ts,jsx,tsx}',
    './libs/**/*.{js,ts,jsx,tsx}'
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 3. Add Tailwind to CSS

In `apps/my-app/src/styles.css` (or `libs/ui/src/lib/ui.css`), add:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 4. Import Styles

In `main.tsx` (or `index.tsx`):

```tsx
import './styles.css';
```

Tailwind is now ready for use in your components.

---

## 🧪 Testing

Run unit tests for any project:

```bash
nx test ui
nx test my-app
```

---

## 🧹 Linting & Formatting

Lint code:

```bash
nx lint ui
```

Format codebase:

```bash
nx format:write
```

---

## 🧰 Useful Commands

Generate a new app:

```bash
nx generate @nx/react:app another-app
```

Generate a shared utility lib:

```bash
nx generate @nx/js:library utils
```

Check what's affected by changes:

```bash
nx affected:graph
```

---

## 📦 Publishing Components (Optional)

To publish the `ui` library as an npm package:

1. Build the library:

   ```bash
   nx build ui
   ```

2. Navigate to the output folder:

   ```bash
   cd dist/libs/ui
   ```

3. Publish:

   ```bash
   npm publish --access public
   ```

> ✅ Make sure `package.json` inside the library is correctly configured with `name`, `version`, and `main`.

---

## 📚 Learn More

* [Nx Documentation](https://nx.dev/)
* [React](https://react.dev/)
* [TypeScript](https://www.typescriptlang.org/)
* [Tailwind CSS](https://tailwindcss.com/)
* [Vite](https://vitejs.dev/)
* [Jest](https://jestjs.io/)

---
