# 🎯 Krosno AR Experience

A WebAR solution that allows users to place 3D models in real space using their phone's camera without downloading any additional apps.

## 📱 Features

- **No App Download Required** - Works directly in any modern web browser
- **QR Code Entry** - Users scan a QR code to launch the AR experience
- **Multiple 3D Models** - Choose from cubes, spheres, cylinders, torus, and custom shapes
- **Interactive Models** - Tap models to interact with them
- **Surface Detection** - Visual indicator for optimal model placement
- **Touch Gestures** - Swipe up to place models quickly
- **Responsive Design** - Works on all mobile devices

## 🚀 Quick Start

### Option 1: Local Testing
1. Clone or download this repository
2. Open `index.html` in a web browser
3. Allow camera access when prompted
4. Start placing 3D models!

### Option 2: Deploy to Web
1. Upload all files to a web hosting service (see deployment section)
2. Generate a QR code pointing to your hosted URL
3. Share the QR code with users

## 📁 File Structure

```
KrosnoAR/
├── index.html              # Basic AR experience
├── advanced-ar.html        # Advanced AR with more features
├── qr-generator.html       # QR code generator tool
├── README.md              # This file
└── models/                # Custom 3D models (optional)
    ├── krosno-arch.glb
    └── other-models.glb
```

## 🌐 Deployment Options

### 1. GitHub Pages (Free)
```bash
# Create a new repository on GitHub
# Upload all files
# Enable GitHub Pages in repository settings
# Your AR experience will be available at: https://username.github.io/repository-name/
```

### 2. Netlify (Free)
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop your project folder
3. Get instant HTTPS URL
4. Use the URL in your QR code generator

### 3. Vercel (Free)
1. Go to [vercel.com](https://vercel.com)
2. Connect your GitHub repository
3. Deploy automatically
4. Get HTTPS URL for QR codes

### 4. Firebase Hosting (Free)
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

## 🔧 Customization

### Adding Custom 3D Models

1. **Convert your Unity models to GLB format:**
   ```bash
   # Use Unity's FBX Exporter or online converters
   # Ensure models are optimized for web (under 5MB)
   ```

2. **Add models to the AR experience:**
   ```html
   <!-- In advanced-ar.html, add to the model selector -->
   <div class="model-option" onclick="selectModel('krosno-arch')">🏛️ Krosno Arch</div>
   
   <!-- Add the model loading logic -->
   case 'krosno-arch':
       model = document.createElement('a-entity');
       model.setAttribute('gltf-model', './models/krosno-arch.glb');
       model.setAttribute('scale', '0.5 0.5 0.5');
       break;
   ```

### Customizing the UI

Edit the CSS in the HTML files to match your brand:
```css
.ui-button {
    background: linear-gradient(135deg, #YOUR_COLOR1, #YOUR_COLOR2);
    /* Add your custom styles */
}
```

## 📱 Browser Compatibility

| Browser | iOS | Android | Desktop |
|---------|-----|---------|---------|
| Safari | ✅ | ❌ | ✅ |
| Chrome | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Edge | ✅ | ✅ | ✅ |

**Note:** AR features require HTTPS and camera permissions.

## 🎮 Controls

### Mobile
- **Tap "Place Model"** - Place selected 3D model
- **Swipe Up** - Quick model placement
- **Tap Models** - Interact with placed models
- **Model Selector** - Choose different 3D shapes

### Desktop (Testing)
- **Spacebar** - Place model
- **C** - Clear all models
- **1-5** - Select different models
- **Mouse** - Look around and interact

## 🔍 Troubleshooting

### Camera Not Working
- Ensure you're using HTTPS
- Check browser permissions
- Try refreshing the page
- Use a supported browser

### Models Not Appearing
- Check console for errors
- Ensure models are properly loaded
- Try different model types
- Check device compatibility

### QR Code Not Working
- Verify the URL is correct
- Ensure the website is accessible
- Test with different QR code scanners
- Check if the URL requires authentication

## 🛠️ Technical Details

### Technologies Used
- **AR.js** - Web-based AR framework
- **A-Frame** - 3D web framework
- **WebXR API** - Browser AR capabilities
- **Three.js** - 3D graphics library

### Performance Optimization
- Models are optimized for mobile devices
- Textures are compressed
- Lazy loading for custom models
- Efficient rendering pipeline

## 📞 Support

For issues or questions:
1. Check the troubleshooting section
2. Test with different devices/browsers
3. Verify HTTPS and camera permissions
4. Check browser console for errors

## 🔄 Updates

### Version 1.0
- Basic AR functionality
- Multiple 3D model types
- QR code integration
- Mobile-optimized UI

### Planned Features
- [ ] Custom model upload
- [ ] Multi-user AR sessions
- [ ] Model persistence
- [ ] Advanced interactions
- [ ] Analytics tracking

## 📄 License

This project is open source. Feel free to modify and distribute.

---

**Made with ❤️ for Krosno AR Experience** 