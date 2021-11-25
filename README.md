
# Issue Swiper with Svelte + Snowpack

I have follow the tuto to setup Swiper with Svelte and I have an issue when I launch my app through Snowpack:

```
Failed to init component
<App>
TypeError: Cannot read properties of undefined (reading '$$')

    at init (http://localhost:8080/_snowpack/pkg/swiper.svelte.v7.3.1.js:356:46)
    at new Swiper$1 (http://localhost:8080/_snowpack/pkg/swiper.svelte.v7.3.1.js:5153:3)
    at create_fragment (http://localhost:8080/App.svelte.js:287:11)
    at init (http://localhost:8080/_snowpack/pkg/svelte.internal.v3.44.2.js:1647:35)
    at new App (http://localhost:8080/App.svelte.js:382:3)
    at createProxiedComponent (http://localhost:8080/_snowpack/pkg/svelte-hmr.runtime.hot-api-esm.v0.13.5.js:242:9)
    at new ProxyComponent (http://localhost:8080/_snowpack/pkg/svelte-hmr.runtime.hot-api-esm.v0.13.5.js:482:20)
    at new Proxy<App> (http://localhost:8080/_snowpack/pkg/svelte-hmr.runtime.hot-api-esm.v0.13.5.js:581:11)
    at http://localhost:8080/index.js:4:11
```

My snowpack.config.js:

```js
/** @type {import("snowpack").SnowpackUserConfig } */
export default {
  mount: {
    /* ... */
  },
  plugins: [
    /* ... */
    '@snowpack/plugin-svelte'
  ],
  routes: [
    /* Enable an SPA Fallback in development: */
    // {"match": "routes", "src": ".*", "dest": "/index.html"},
  ],
  optimize: {
    /* Example: Bundle your final build: */
    // "bundle": true,
  },
  packageOptions: {
    /* ... */
  },
  devOptions: {
    /* ... */
  },
  buildOptions: {
    /* ... */
  },
};
```

my index.js:

```js
/* Add JavaScript code here! */
import App from "./App.svelte";

let app = new App({
  target: document.body,
});

export default app;`
```

my App.svelte:

```js
<script>
  /* component logic will go here */
  // Import Swiper Svelte components
  import { Swiper, SwiperSlide } from 'swiper/svelte';

  // Import Swiper styles
  import 'swiper/css';
</script>
<style>
  /* css will go here */
</style>
<div class="App">
  <header class="App-header">
    <a class="App-link" href="https://svelte.dev" target="_blank" rel="noopener noreferrer">
      Learn Svelte
    </a>
  </header>

  <Swiper
    spaceBetween={50}
    slidesPerView={3}
    on:slideChange={() => console.log('slide change')}
    on:swiper={(e) => console.log(e.detail[0])}
  >
    <SwiperSlide>Slide 1</SwiperSlide>
    <SwiperSlide>Slide 2</SwiperSlide>
    <SwiperSlide>Slide 3</SwiperSlide>
    <SwiperSlide>Slide 4</SwiperSlide>
    ...
  </Swiper>

</div>`
```

# New Project

> ✨ Bootstrapped with Create Snowpack App (CSA).

## Available Scripts

### npm start

Runs the app in the development mode.
Open http://localhost:8080 to view it in the browser.

The page will reload if you make edits.
You will also see any lint errors in the console.

### npm run build

Builds a static copy of your site to the `build/` folder.
Your app is ready to be deployed!

**For the best production performance:** Add a build bundler plugin like [@snowpack/plugin-webpack](https://github.com/snowpackjs/snowpack/tree/main/plugins/plugin-webpack) or [snowpack-plugin-rollup-bundle](https://github.com/ParamagicDev/snowpack-plugin-rollup-bundle) to your `snowpack.config.mjs` config file.

### Q: What about Eject?

No eject needed! Snowpack guarantees zero lock-in, and CSA strives for the same.
