# Svelte and Snowpack

> ✨ Bootstrapped with Create Snowpack App (CSA).
> https://www.snowpack.dev/tutorials/svelte

<br>

## Setup steps

install snowpack

```
npx create-snowpack-app svelte-snowpack --template @snowpack/app-template-minimal
```

<br>

install svelte

```
npm install svelte --save
npm install @snowpack/plugin-svelte --save-dev
```

update `snowpack.config.mjs` with `'@snowpack/plugin-svelte',` in plugins

<br>

install sass and bulma

```
npm install node-sass --save-dev
npm install bulma --save-dev
```

<br>

install `@snowpack/plugin-webpack` for production builds

```
npm install --save-dev @snowpack/plugin-webpack
```

update `snowpack.config.mjs` with `'@snowpack/plugin-webpack',` in plugins

<br>

set up app structure with public and src folders  
update config `mount` section to match  
[snowpack-website-example](https://www.snowpack.dev/tutorials/svelte)

TODO: try using images and see if they move from public to build properly
TODO: get css to build in same src/dist output file path
TODO: might want to move both css and images to an assets folder in /src so it builds properly to full path
TODO: get src/dist to minify js

<br>

environment variables
https://www.snowpack.dev/reference/configuration#env
https://www.snowpack.dev/reference/environment-variables

configure builds (vs dev)
https://www.snowpack.dev/reference/configuration#buildoptions.baseurl
https://github.com/snowpackjs/snowpack/discussions/2674

hostname: https://www.snowpack.dev/reference/configuration#devoptions.hostname
devOptions.hostname
devOptions.port
