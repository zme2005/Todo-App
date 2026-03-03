### Modern Todo – Vite + React

A minimal, modern todo application built with **React**, **TypeScript**, **Vite**, and **Tailwind CSS**, featuring local storage persistence and a dark/light mode toggle.

---

### Features

- **Add / delete todos** with instant UI updates.
- **Mark tasks as done/undone** with clear visual feedback.
- **Local storage persistence** so your tasks survive page reloads.
- **Dark / light mode toggle** stored in `localStorage`.
- **Responsive design** using Tailwind CSS.

---

### Tech Stack

- **Framework**: React + TypeScript
- **Bundler**: Vite
- **Styling**: Tailwind CSS
- **Icons**: `react-icons`

---

### Getting Started (Local Development)

1. **Install dependencies**

   ```bash
   npm install
   ```

2. **Run the dev server**

   ```bash
   npm run dev
   ```

3. Open the printed URL in your browser (usually `http://localhost:5173/`).

---

### Available Scripts

- **`npm run dev`** – Start the Vite development server.
- **`npm run build`** – Type-check with TypeScript and build the app for production to the `dist` folder.
- **`npm run preview`** – Preview the production build locally.
- **`npm run lint`** – Run ESLint on the project.

---

### Building for Production

To generate an optimized production build:

```bash
npm run build
```

The compiled assets will be output to the `dist` directory.

---

### Deployment (GitHub Pages)

This project is configured to be deployed to **GitHub Pages** using Vite’s `base` option.

- The `vite.config.ts` file sets:
  - `base: '/Todo-App/',` (update this if your repository name is different).
- A typical deployment flow:
  1. Push the project to a GitHub repository.
  2. Enable GitHub Pages (via GitHub Actions workflow).
  3. Serve the `dist` folder as the site output.

For detailed, step-by-step deployment instructions (including a sample GitHub Actions workflow), see **`DEPLOYMENT.md`** in the project root.

---

### Project Structure (Key Files)

- `src/App.tsx` – Main UI for the todo app.
- `src/hooks/useTask.ts` – Custom hook for task state and local storage handling.
- `src/Types/taskType.ts` – Type definition for tasks.
- `vite.config.ts` – Vite configuration (includes GitHub Pages `base` path).

---

### License

You can add your preferred license here (for example, MIT). If you plan to open source the project, include a `LICENSE` file in the repository.

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```
