## Built with [Svelte](https://svelte.dev) + [Sapper](https://sapper.svelte.dev) + [MDSvex](https://mdsvex.pngwn.io/) + [svelte-mui](https://svelte-mui.ibbf.ru/)

Githubs: [Sapper template](https://github.com/sveltejs/sapper-template) • [mdsvex](https://github.com/pngwn/MDsveX) • [svelte-mui](https://github.com/vikignt/svelte-mui)

## Install

```
npx degit "sveltejs/sapper-template#rollup" svexiest
cd svexiest
npm i -D mdsvex
npm install
npm run dev
```

update these [package.json](./package.json) scripts

```javascript
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

Customize  `mdsvex({ ... })`as needed ([mdsvex readme](https://github.com/pngwn/MDsveX/blob/master/README.md))

You can do  `preprocess: mdsvex({ ... })` separately inside each client & server or definea  `preprocess` once up-front that you can re-use.

```javascript
const preprocess = [
  // you can use multiple preprocessors
	mdsvex({
		extension: '.svx',
	}),
]

export default {
  client: { //...
    plugins: [ //...
      svelte({ //...
				preprocess,
			}),
    	]
  },
  
  server: { //...
    plugins: [ //...
      svelte({ //...
				preprocess,
			}),
    	]
  },
    
```

## Deploy

### Netlify

[netlify.toml](./netlify.toml) uses  `npm run export to export a static Sapper site.

My project on Netlify automatically deploys from the github master branch when it changes.

## Vscode customizations

(Or [vscodium](https://vscodium.com))

[Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) • [Svelte 3 Snippets](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode)

Settings

```json
"files.associations": {"*.svx": "markdown",},
"emmet.excludeLanguages": [],
"emmet.includeLanguages": {"markdown": "html"},
```