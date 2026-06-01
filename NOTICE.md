# Notices

This repository includes and adapts third-party open-source software.

## potrace-wasm

- Project: `potrace-wasm`
- Repository: https://github.com/IguteChung/potrace-wasm
- Package version used as reference: `potrace-wasm@1.0.4`
- License: GNU General Public License version 2

The file `lib/potrace-wasm.js` is an Emscripten-generated Potrace WebAssembly
bundle with small browser-global exports added:

- `window.potraceReady`
- `window.potraceFromCanvas`
- `window.potraceFromImageData`

## Potrace

- Project: Potrace
- Website: https://potrace.sourceforge.net/
- Author: Peter Selinger
- License: GPL-compatible terms as distributed through the WASM port above

Potrace converts bitmap images into smooth vector paths.
