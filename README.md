# Brand new Template

loaded brand new template with Storybook and running it in Node 22.14.0 (updated package.json with latest versions of all)

Storybook Fails:

```
PS:\>yarn storybook
@storybook/core v8.6.12

info => Serving static files from C:\source\repos\setup\blank-setup\node_modules\.cache\storybook\default\coverage at /coverage
info => Starting manager..
info => Starting preview..
=> Failed to build the preview
Error [ERR_MODULE_NOT_FOUND]: Cannot find module 'C:\Users\Benjamin.Gray\AppData\Local\Yarn\Berry\cache\react-docgen-npm-7.1.1-0530992ae8-10c0.zip\node_modules\react-docgen\dist\config.js' imported from C:\Users\Benjamin.Gray\AppData\Local\Yarn\Berry\cache\react-docgen-npm-7.1.1-0530992ae8-10c0.zip\node_modules\react-docgen\dist\main.js
    at finalizeResolution (node:internal/modules/esm/resolve:275:11)
    at moduleResolve (node:internal/modules/esm/resolve:860:10)
    at defaultResolve (node:internal/modules/esm/resolve:984:11)
    at ModuleLoader.defaultResolve (node:internal/modules/esm/loader:685:12)
    at #cachedDefaultResolve (node:internal/modules/esm/loader:634:25)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:384:53)
    at new ModuleJobSync (node:internal/modules/esm/module_job:341:34)
    at ModuleLoader.importSyncForRequire (node:internal/modules/esm/loader:357:11)
    at loadESMFromCJS (node:internal/modules/cjs/loader:1385:24)
    at Module._compile (node:internal/modules/cjs/loader:1536:5)

WARN Broken build, fix the error above.
WARN You may need to refresh the browser.
```

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

-   [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
-   [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
	extends: [
		// Remove ...tseslint.configs.recommended and replace with this
		...tseslint.configs.recommendedTypeChecked,
		// Alternatively, use this for stricter rules
		...tseslint.configs.strictTypeChecked,
		// Optionally, add this for stylistic rules
		...tseslint.configs.stylisticTypeChecked,
	],
	languageOptions: {
		// other options...
		parserOptions: {
			project: ["./tsconfig.node.json", "./tsconfig.app.json"],
			tsconfigRootDir: import.meta.dirname,
		},
	},
});
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from "eslint-plugin-react-x";
import reactDom from "eslint-plugin-react-dom";

export default tseslint.config({
	plugins: {
		// Add the react-x and react-dom plugins
		"react-x": reactX,
		"react-dom": reactDom,
	},
	rules: {
		// other rules...
		// Enable its recommended typescript rules
		...reactX.configs["recommended-typescript"].rules,
		...reactDom.configs.recommended.rules,
	},
});
```
