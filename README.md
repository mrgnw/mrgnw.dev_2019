## Built with [Svelte](https://svelte.dev) + [Sapper](https://sapper.svelte.dev) + [MDSvex](https://mdsvex.pngwn.io/)

Github: [Sapper template](https://github.com/sveltejs/sapper-template) + [mdsvex](https://github.com/pngwn/MDsveX)

### Install

```
npx degit "sveltejs/sapper-template#rollup" svexiest
cd svexiest
npm i -D mdsvex
npm install
npm run dev
```

update these [package.json](./package.json) scripts

```diff
"dev": "sapper dev  --ext '.svx .svexy .svelte'",
"export": "sapper export --ext '.svx .svexy .svelte'",
"start": "sapper dev --ext '.svx .svexy .svelte'",
```

[rollup.config.js](./rollup.config.js)

```diff
+ import { mdsvex } from 'mdsvex';
// add these anywhere you see svelte({ … })
svelte({
+  extensions: ['.svelte', '.svexy', '.svx'],
+  preprocess: mdsvex({}),
 })
```

### Netlify

 `npm run export` exports a static Sapper site, and that's what [netlify.toml](./netlify.toml) uses.