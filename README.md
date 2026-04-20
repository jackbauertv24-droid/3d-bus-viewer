# 3D Bus Viewer

A static HTML5 single-page 3D model viewer built with Three.js.
View bundled bus models or load your own 3D models locally.

## Features

- **Bundled Models**: 3 open-source bus models included
- **User Upload**: Load your own GLB, GLTF, or OBJ files
- **Serverless**: Files stay on your device - no server upload
- **Studio Lighting**: Multiple lighting presets (Studio, Outdoor, Night)
- **Wireframe Mode**: Toggle wireframe overlay
- **Color Customization**: Pick custom colors for models
- **Screenshot**: Download current view as PNG
- **Responsive**: Works on desktop and mobile
- **Keyboard Controls**: R (reset), F (fullscreen)

## Supported Formats

| Format | Bundled | User Upload |
|--------|---------|-------------|
| OBJ    | ✅      | ✅          |
| GLB    | ❌      | ✅          |
| GLTF   | ❌      | ✅          |

## Usage

### View Bundled Models
1. Select a model from the dropdown menu
2. Use mouse/trackpad to rotate, pan, and zoom

### Load Your Own Models
1. Click "Load Local File"
2. Select a .obj, .glb, or .gltf file from your computer
3. The file is loaded locally - **no upload to any server**

### Controls
- **Left click + drag**: Rotate model
- **Right click + drag**: Pan view
- **Scroll wheel**: Zoom in/out
- **R key**: Reset view
- **F key**: Toggle fullscreen

## Running Locally

### Option 1: Direct File Opening
Open `index.html` directly in a browser. Note: bundled models may not load due to CORS restrictions.

### Option 2: Local Server (Recommended)
```bash
# Python 3
python -m http.server 8000

# Python 2
python -SimpleHTTPServer 8000

# Node.js (npx)
npx serve .
```

Then open: http://localhost:8000

### Option 3: GitHub Pages
Deploy to GitHub Pages for free hosting:
1. Push to a GitHub repository
2. Enable GitHub Pages in repository settings
3. Access via: https://yourusername.github.io/3d-viewer/

## Project Structure

```
3d-viewer/
├── index.html          # Main viewer (single file)
├── models/             # Bundled sample models
│   ├── 3dbus/          # Generic bus
│   ├── publictransport/ # LowPoly bus
│   ├── schoolbus/      # School bus
│   └── ATTRIBUTION.md  # Model credits
└── README.md           # This file
```

## Adding Your Own Bundled Models

1. Place OBJ/GLB files in the `models/` folder
2. Add entries to `BUNDLED_MODELS` in index.html:
```javascript
const BUNDLED_MODELS = {
    'models/your-model.obj': { mtl: 'models/your-model.mtl', name: 'Your Model' }
};
```
3. Add option to the model select dropdown:
```html
<option value="models/your-model.obj">Your Model Name</option>
```

## Credits

- **3D Engine**: [Three.js](https://threejs.org/)
- **Bus Models**: [OpenGameArt](https://opengameart.org) (CC0)
  - Generic Bus by ajanhallinta
  - LowPoly Bus by quaternius
  - School Bus by quaternius

## License

- **Code**: MIT License (free to use, modify, distribute)
- **Bundled Models**: CC0 (Public Domain)