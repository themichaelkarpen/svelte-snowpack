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

- set up app structure with public and src folders
- update config `mount` section to match
- [snowpack-website-example](https://www.snowpack.dev/tutorials/svelte)

<br>

**production builds**

Using `plugin-webpack` works except for the favicon. I don't like how all the svelte components get built into the directory though. It's bloated with many files, and not sure they are all needed.

Tried using native Snowpack with `optimize` object - and not the `plugin-webpack`. Visually this looks better, however it does not work on a production server with a non-root file path.

_Conclusion:_

- I much prefer Vite right now. My only blocker is I need `svelte-router-spa` to work in dev mode in Vite. It works with a production build but not in dev.
- Vite also seems faster and easier to use. Documentation is better as well.

<br>

**other items to experiment with**

see how `svelte-router-spa` works in dev and production

environment variables  
https://www.snowpack.dev/reference/configuration#env
https://www.snowpack.dev/reference/environment-variables

hostname, ports, routes and proxy
https://www.snowpack.dev/reference/configuration#devoptions.hostname
https://www.snowpack.dev/guides/routing#scenario-1-spa-fallback-paths

```
devOptions.hostname
devOptions.port
```

```js
// snowpack.config.mjs
import proxy from 'http2-proxy';

export default {
  routes: [
    {
      src: '/api/.*',
      dest: (req, res) => {
        // remove /api prefix (optional)
        req.url = req.url.replace(/^/api/, '');

        return proxy.web(req, res, {
          hostname: 'localhost',
          port: 3001,
        });
      },
    },
  ],
};

```
