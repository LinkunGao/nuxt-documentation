# How to use Nuxt

## plugins

When we import a new moudle.

If the moudel include `window` / `document`. We need set `ssr:flase`

- In nuxt.config.js

```js
export default {
  plugins: [
    "@/plugins/topics",
    "@/plugins/current-content",
    "@/plugins/models",
    { src: "~/plugins/copper.js", ssr: false },
  ],
};
```

- In plugins folder

  we can create a `copper.js` import the moudle.

```js
import * as Copper from "gltfloader-plugin-test";

const container = document.createElement("div");
container.style.width = "100vw";
container.style.height = "100vh";
const baseRenderer = new Copper.copperRenderer(container, { guiOpen: true });
baseRenderer.animate();

export default (context, inject) => {
  inject("baseRenderer", () => {
    return baseRenderer;
  }),
    inject("baseContainer", () => {
      return container;
    }),
    inject("Copper", () => {
      return Copper;
    });
};
```
