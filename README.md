# SIE Model Viewer — BIM Intelligence Platform

## Files
- `index.html` — Main 3D viewer with demo model
- `upload.html` — Upload page for IFC, GLB, OBJ, STL, FBX, DAE, PLY files
- `Logo.png` — Company logo

## GitHub Pages Deployment
1. Create a new repo on GitHub
2. Upload all files to the root of the repo
3. Go to Settings → Pages → Source: Deploy from branch (main) → Save
4. Your viewer will be live at `https://USERNAME.github.io/REPO-NAME/`

## IFC Support (Important!)
The IFC viewer uses the **web-ifc** WebAssembly engine. For the most reliable IFC loading:

### Option A: Local WASM file (recommended)
Download the WASM file and place it in the same folder as your HTML files:

1. Download from: https://unpkg.com/web-ifc@0.0.44/web-ifc.wasm
2. Save as `web-ifc.wasm` in the same folder as `upload.html`
3. Commit and push to GitHub Pages

This is the most reliable method as it avoids CDN cross-origin issues.

### Option B: CDN (automatic)
The upload page will automatically try multiple CDN sources:
- unpkg.com (web-ifc 0.0.44)
- jsDelivr (web-ifc 0.0.44)
- unpkg.com (web-ifc 0.0.46)

### If IFC still fails
Export your model to **.glb** format instead:
- **From Revit**: File → Export → glTF (Revit 2023+) or use the free glTF Exporter plugin
- **From Revit via IFC**: File → Export → IFC, then convert IFC→GLB using BlenderBIM or FreeCAD
- **Online converters**: https://ifcjs.github.io/web-ifc-viewer/example/index

## Supported Formats
| Format | Extension | Status |
|--------|-----------|--------|
| IFC | .ifc | ✅ Native (web-ifc WASM) |
| glTF Binary | .glb | ✅ Native (recommended) |
| glTF | .gltf | ✅ Native |
| Wavefront | .obj | ✅ Native |
| FBX | .fbx | ✅ Native |
| STL | .stl | ✅ Native |
| Collada | .dae | ✅ Native |
| PLY | .ply | ✅ Native |
| Revit | .rvt | ⚠️ Needs export to IFC or GLB first |
