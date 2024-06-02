Svelte animation bug
===

In Svelte 5 (Next 139 tested here), the fade animate flickers.

## To reproduce

```sh
npm install
npm run dev
```

Click the add button. You'll see a flicker instead of a smooth fade.
