# html-potrace-wasm

A minimal static HTML demo that converts local images to SVG in the browser
with Potrace WebAssembly.

No upload. No backend. No build step.

## What it does

- Loads a PNG, JPEG, WebP, GIF, or BMP from your computer.
- Draws it to a canvas in the browser.
- Applies a simple black/white threshold preview.
- Sends the canvas pixel data to Potrace WASM.
- Shows the generated SVG and lets you download it.

This project is intentionally small. It is meant to be a clean starting point
for people who want to understand the shortest practical path from:

```text
image file -> canvas -> ImageData -> Potrace WASM -> SVG
```

## Try it locally

Because WebAssembly loading is more reliable over HTTP than from `file://`,
serve this folder with any static file server:

```sh
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Files

```text
index.html              Minimal browser UI and conversion flow
lib/potrace-wasm.js     Potrace WASM bundle adapted for browser globals
LICENSE                 GPL-2.0
NOTICE.md               Third-party attribution
```

## Browser API exposed by the bundle

The bundled script exposes these globals:

```js
await window.potraceReady;
const svg = await window.potraceFromCanvas(canvas);
const svg = await window.potraceFromImageData(imageData.data, width, height);
```

## Notes

Potrace works best for high-contrast, single-color artwork such as icons,
logos, stamps, signatures, and line art. It is not a general photo vectorizer.
This demo intentionally produces a single black SVG path.

## License

GPL-2.0. See [LICENSE](./LICENSE) and [NOTICE.md](./NOTICE.md).

This project includes a Potrace WASM bundle derived from
[`IguteChung/potrace-wasm`](https://github.com/IguteChung/potrace-wasm), which
is licensed under GPL-2.0.
