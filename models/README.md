# 📦 3D Models Directory

This directory contains custom 3D models for the Krosno AR experience.

## 🎯 How to Add Your Models

### Step 1: Prepare Your Model
1. **Export from Unity:**
   - Select your 3D model in Unity
   - File → Export → FBX
   - Choose appropriate settings (optimize for web)

2. **Convert to GLB Format:**
   - Use online converters like [gltf.report](https://gltf.report)
   - Or use Blender: File → Export → glTF 2.0 (.glb/.gltf)
   - Ensure file size is under 5MB for optimal performance

### Step 2: Add to This Directory
```bash
# Copy your GLB file here
cp your-model.glb models/
```

### Step 3: Update the AR Experience
Edit `advanced-ar.html` and add your model:

```html
<!-- Add to the model selector -->
<div class="model-option" onclick="selectModel('your-model')">🏛️ Your Model Name</div>

<!-- Add to the JavaScript switch statement -->
case 'your-model':
    model = document.createElement('a-entity');
    model.setAttribute('gltf-model', './models/your-model.glb');
    model.setAttribute('scale', '0.5 0.5 0.5'); // Adjust scale as needed
    break;
```

## 📋 Model Requirements

- **Format:** GLB (recommended) or GLTF
- **File Size:** Under 5MB per model
- **Polygons:** Optimize for mobile (under 10,000 polygons)
- **Textures:** Compressed (JPEG/PNG)
- **Materials:** PBR materials work best

## 🔧 Optimization Tips

1. **Reduce Polygon Count:**
   - Use LOD (Level of Detail)
   - Remove unnecessary details
   - Simplify geometry

2. **Optimize Textures:**
   - Use power-of-2 dimensions (512x512, 1024x1024)
   - Compress textures
   - Use appropriate formats

3. **Test Performance:**
   - Load models on mobile devices
   - Check frame rate
   - Monitor memory usage

## 📁 Example Models

- `krosno-arch.glb` - Example architectural model
- `furniture.glb` - Example furniture model
- `decoration.glb` - Example decorative object

## 🚀 Quick Test

To test a model quickly:
1. Add your GLB file to this directory
2. Update the HTML file
3. Open `advanced-ar.html` in a browser
4. Select your model and place it in AR

## 📞 Support

If you have issues with model loading:
1. Check file format and size
2. Verify the file path is correct
3. Check browser console for errors
4. Test with different browsers 