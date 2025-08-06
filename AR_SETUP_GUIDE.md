# AR Setup Guide

## Issues Fixed

1. **Camera Access**: Updated AR.js configuration for proper camera initialization
2. **HTTPS Requirement**: Added HTTPS detection and warnings
3. **Favicon 404**: Added inline favicon to prevent 404 errors
4. **Model Support**: Added support for the Nortec 600D GLB model
5. **Error Handling**: Added comprehensive error handling and status indicators

## Requirements

### 1. HTTPS or Localhost
AR.js requires HTTPS to access the camera. You can run this in two ways:

**Option A: Local Development Server (Recommended)**
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (if you have it installed)
npx http-server -p 8000

# Using PHP
php -S localhost:8000
```

Then visit: `http://localhost:8000`

**Option B: HTTPS Server**
- Deploy to GitHub Pages, Netlify, or any HTTPS hosting service
- Or use a local HTTPS server with self-signed certificates

### 2. Camera Permissions
- Allow camera access when prompted by the browser
- Make sure no other applications are using the camera

### 3. Modern Browser
- Chrome (recommended)
- Firefox
- Safari (iOS)
- Edge

## How to Test

1. **Start a local server** (see options above)
2. **Open the page** in your browser
3. **Allow camera access** when prompted
4. **Wait for "Camera: Ready"** status to appear
5. **Point camera at a flat surface**
6. **Tap "Place Model"** to place 3D objects

## Troubleshooting

### Camera Not Working
- Check if you're on HTTPS or localhost
- Ensure camera permissions are granted
- Try refreshing the page
- Check browser console for errors

### Models Not Appearing
- Make sure you're pointing at a well-lit, textured surface
- Try different surfaces (table, floor, wall)
- Check if the camera status shows "Ready"

### Performance Issues
- Close other camera-using applications
- Ensure good lighting conditions
- Try on a different device if available

## Features

- **Multiple Models**: Cube, Sphere, Cylinder, and Nortec 600D
- **Touch Controls**: Tap to place, swipe up gesture
- **Visual Feedback**: Placement effects and animations
- **Status Indicators**: Real-time camera and AR status
- **Error Handling**: Clear error messages and guidance

## File Structure

```
saratutova-github-io/
├── index.html          # Main AR application
├── models/
│   └── Nortec600D.glb  # 3D model file
└── AR_SETUP_GUIDE.md   # This guide
```

## Next Steps

1. Test the application locally
2. Deploy to a hosting service for public access
3. Customize models and interactions as needed
4. Add more AR features like object tracking or image recognition 