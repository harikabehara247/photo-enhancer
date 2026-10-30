# AI Photo Enhancer

Make small or low-resolution photos sharper and bigger with a free AI upscaler (ESRGAN). Enlarge images 2× or 4× in your browser, with no upload and no watermark.

**Live demo:** https://harikabehara247.github.io/photo-enhancer/

## About

Old phone photos, screenshots and images saved from chats are often too small to print or reuse. Enlarging them normally makes them blurry. An AI upscaler predicts the missing detail instead, so edges stay crisp and text stays readable at the larger size.

This enhancer runs the open ESRGAN model in your browser with your device’s graphics chip. Photos are processed by the AI up to about 2 megapixels at 2×. Logos, text and screenshots use the sharp text mode, which works on large files and keeps transparent backgrounds. For a cleaner portrait, combine it with the Background Remover.

## Features

- **Real AI upscaling** — Uses an ESRGAN (RDN) super-resolution model, not simple stretching, to rebuild edges and texture.
- **Sharp text and logos** — A dedicated text and logo mode rebuilds letters and edges in the logo’s own colours, removes JPEG noise and keeps transparent backgrounds.
- **Private** — Your photo is processed on your device; nothing is uploaded.
- **Before and after** — A comparison slider shows exactly what changed before you download.

## How to use

1. **Add a photo** — Choose a JPG, PNG or WebP image. Small and low-resolution photos benefit the most.
2. **Choose 2× or 4×** — 2× doubles the width and height; 4× makes the image four times larger in each direction.
3. **Enhance** — The model works through the picture tile by tile. Large photos take longer on phones.
4. **Compare and download** — Drag the slider to compare before and after, then save the enhanced PNG.

## Tech

- Plain HTML, CSS and JavaScript (ES modules), no build step
- Runs entirely in the browser: files and inputs never leave the device
- Third-party libraries:
  - @tensorflow/tfjs 4.22.0 Apache-2.0
  - fflate 0.8.3 MIT

## Run locally

Serve the folder with any static server, for example `python3 -m http.server`, then open http://localhost:8000. (ES modules do not load from `file://`.)

## FAQ

**Can it make blurry text or a logo sharper?**  
Yes. Leave it on “Detect it for me” or choose “Text or logo”. It rebuilds letters and edges in the logo’s own colours, cleans JPEG noise and keeps a transparent background. Use “Photo” for faces and scenes.

**Does the photo enhancer add a watermark?**  
No. It is free with no watermark and no sign-up.

**What is the difference between 2× and 4×?**  
2× doubles the width and height (four times the pixels). 4× makes the image four times wider and taller, which takes much longer.

**Can it fix a very blurry or out-of-focus photo?**  
It sharpens edges and adds detail to small images, but it cannot fully recover a photo that is badly out of focus or shaken.

**Why is it slow on my phone?**  
Upscaling is heavy work done on your own device. Use 2× and a smaller photo on phones, or use a laptop for large images.

**Is there a size limit?**  
To keep your browser responsive, the tool scales very large inputs down first: about 1,500 pixels on the longest side for 2× and 750 for 4×.

## Author

Built by **[Harika Behara](https://github.com/harikabehara247)**.

## Licence

Code: [MIT](LICENSE) © 2026 Harika Behara. Bundled third-party libraries keep their own licences — see `assets/tools/vendor/LICENSES.txt`.
