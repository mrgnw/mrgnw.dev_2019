## Built with [Svelte](https://svelte.dev) + [Sapper](https://sapper.svelte.dev) + [MDSvex](https://mdsvex.pngwn.io/)

Github: [Sapper template](https://github.com/sveltejs/sapper-template) + [mdsvex](https://github.com/pngwn/MDsveX)

## Install

```
npx degit "sveltejs/sapper-template#rollup" svexiest
cd svexiest
npm i -D mdsvex
npm install
npm run dev
```

update these [package.json](./package.json) scripts

```
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
+  preprocess: mdsvex({ }),
 })
```

## Customize

Customize each `mdsvex({ ... })`as needed ([mdsvex readme](https://github.com/pngwn/MDsveX/blob/master/README.md))

I changed the extension because I lack taste.

```javascript
preprocess: mdsvex({
	extension: '.svx',
})
```

## Deploy

### Netlify

[netlify.toml](./netlify.toml) uses  `npm run export to export a static Sapper site.

My project on Netlify automatically deploys from the github master branch when it changes.