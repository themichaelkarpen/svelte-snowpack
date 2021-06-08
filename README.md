# Svelte and Snowpack

> ✨ Bootstrapped with Create Snowpack App (CSA).
> https://www.snowpack.dev/tutorials/svelte

<br>

## Setup steps

install snowpack

```
npx create-snowpack-app svelte-snowpack --template @snowpack/app-template-minimal
```

install svelte

```
npm install svelte --save
npm install @snowpack/plugin-svelte --save-dev
```

update `snowpack.config.mjs` with `'@snowpack/plugin-svelte',` in plugins

_tip: making changes in this file requires a stop and restart of dev server_

install sass and bulma

```
npm install node-sass --save-dev
npm install bulma --save-dev
```

create first Svelte component and proceed build and other items from here

## Available Scripts

### npm start

Runs the app in the development mode.
Open http://localhost:8080 to view it in the browser.

The page will reload if you make edits.
You will also see any lint errors in the console.

### npm run build

Builds a static copy of your site to the `build/` folder.
Your app is ready to be deployed!

**For the best production performance:**  
Add a build bundler plugin like  
[@snowpack/plugin-webpack](https://github.com/snowpackjs/snowpack/tree/main/plugins/plugin-webpack)
or  
[snowpack-plugin-rollup-bundle](https://github.com/ParamagicDev/snowpack-plugin-rollup-bundle)  
to your `snowpack.config.mjs` config file.
