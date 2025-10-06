# Sunglasses AR — Self‑Hosted (No CDN)

Your network is likely blocking the CDN. This build serves **everything locally** from `/assets`.

## You must download 3 files and place them in the paths below:

1) **Bundle JS** (exposes `window.vision`):
   - Save as: `assets/vision_bundle.js`
   - Get it from either:
     - https://cdn.jsdelivr.net/npm/@mediapipe/tasks-vision@0.10.10/vision_bundle.js
     - or https://unpkg.com/@mediapipe/tasks-vision@0.10.10/vision_bundle.js

2) **WASM runtime folder** (several .wasm/.js helper files):
   - Save the *entire folder* contents to: `assets/wasm/`
   - Get from:
     - https://cdn.jsdelivr.net/npm/@mediapipe/tasks-vision@0.10.10/wasm/
     (download all files inside and keep the same filenames)

3) **Face Landmarker model file**:
   - Save as: `assets/models/face_landmarker.task`
   - Get from:
     - https://cdn.jsdelivr.net/npm/@mediapipe/tasks-vision@0.10.10/models/face_landmarker.task

**Folder structure (after you place files):**
```
Sunglasses/
  index.html
  camera_test.html
  assets/
    vision_bundle.js
    wasm/
      *.wasm, *.js (several files from the CDN "wasm" directory)
    models/
      face_landmarker.task
```

Then push to GitHub and enable **Pages** (Settings → Pages → Deploy from branch → root).

Open:
- Main AR: `https://<user>.github.io/<repo>/index.html`
- Camera only: `https://<user>.github.io/<repo>/camera_test.html`

If `camera_test.html` works but `index.html` shows "model load error", double-check the **paths and filenames** exactly as above. On iOS, you may need to tap **Start Camera** and allow permissions.

© 2025 • MIT
