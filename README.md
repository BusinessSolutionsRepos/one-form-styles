# one-form-styles

Tailwind CSS browser compiler bundle served to [modular-one-form](https://github.com/BusinessSolutionsRepos/modular-one-form) in iPaaS production.

Agents cache this file in `localStorage` as `tailwindCompilerCode`.

## Dark mode (v2)

The bundle ends with:

```js
window.tailwind.config = { darkMode: "class" };
```

This enables `dark:` utilities when `<html class="dark">` is set by One Form's theme toggle (`localStorage.oneform-theme`).

**Deploy order:** merge and push this repo first, then deploy modular-one-form. modular-one-form uses `TAILWIND_COMPILER_VERSION = "2"` to force agents to re-fetch the updated compiler.

## Updating the bundle

`index.js` is the minified Tailwind CDN runtime. To rebuild, follow Tailwind's CDN docs and re-append the dark-mode config block after the closing `})();`.
