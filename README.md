<p align="center">
  <img src="img/logo.png" alt="Pixkit" width="160" />
</p>

# Pixkit

A VS Code extension for optimizing images directly inside the editor. Resize, crop, rotate, compress and convert formats — without leaving VS Code, without uploading anything to the cloud.

Uses [ImageMagick](https://imagemagick.org) through [magick-wasm](https://github.com/dlemstra/magick-wasm). Pixkit is not affiliated with or endorsed by ImageMagick Studio LLC.

## Features

- **Resize** — width/height inputs, lock aspect ratio, quick percentage presets
- **Crop** — drag a region on the preview, or type exact coordinates
- **Rotate & Flip** — 90° presets, free-angle slider, horizontal / vertical flip
- **Compress** — quality slider (1–100) for lossy formats
- **Change format** — JPEG, PNG, WebP, AVIF, GIF, TIFF, BMP
- **Live preview** with output size estimate
- **Save As** dialog with a smart default filename (`photo.optimized.webp`) — never overwrites your source
- **Presets & one-click optimize** — right-click an image (or a selection) →
  **Optimize with Preset** to write optimized output straight to disk, no panel.
  Presets hold a format, quality, max size, and metadata-strip choice; edit them
  in the `pixkit.presets` setting, or use **Save as preset** in the panel.
  Remove one with **Pixkit: Delete Preset** from the command palette.

## Usage

1. **From the Explorer:** right-click any image file → **Optimize Image with Pixkit**.
2. **From the command palette:** `Cmd/Ctrl+Shift+P` → **Pixkit: Open Image** → pick a file.
3. **Drag & drop:** open the panel via the command palette, then drag an image into the preview area.

## Supported formats

Reads anything the bundled ImageMagick WebAssembly build can read. Writes JPEG, PNG, WebP, AVIF, GIF, TIFF and BMP. The extension checks which encoders the build has at startup and only shows formats it can produce. It runs the same on every OS and CPU, with no native binary.

## Development

```bash
npm install
npm run watch    # rebuild extension + webview on save
```

The webview is a Svelte 5 + Tailwind v4 SPA. Image decoding and encoding run in the webview on `@imagemagick/magick-wasm`. The extension host reads and writes files, and runs the same wasm for one-click preset optimization.

## License

MIT
