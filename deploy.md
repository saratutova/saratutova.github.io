# 🚀 Deployment Guide - Krosno AR Experience

## Quick Deployment Steps

### Step 1: Choose Your Hosting Platform

#### Option A: Netlify (Recommended - Easiest)
1. Go to [netlify.com](https://netlify.com) and sign up
2. Click "New site from Git" or drag your folder to the deploy area
3. Upload your project files
4. Get your HTTPS URL instantly
5. Use this URL in your QR code generator

#### Option B: GitHub Pages (Free)
1. Create a new GitHub repository
2. Upload all your files to the repository
3. Go to Settings → Pages
4. Select "Deploy from a branch" → "main" branch
5. Your site will be available at `https://username.github.io/repository-name/`

#### Option C: Vercel (Free)
1. Go to [vercel.com](https://vercel.com) and sign up
2. Click "New Project"
3. Import your GitHub repository or upload files
4. Deploy automatically
5. Get your HTTPS URL

### Step 2: Generate QR Code

1. Open `qr-generator.html` in your browser
2. Enter your deployed URL (e.g., `https://your-site.netlify.app`)
3. Click "Generate QR Code"
4. Download the QR code image
5. Print or display the QR code

### Step 3: Test Your AR Experience

1. Scan the QR code with your phone
2. Allow camera access when prompted
3. Test placing 3D models
4. Verify all features work correctly

## 📋 Pre-Deployment Checklist

- [ ] All files are in the correct directory structure
- [ ] `index.html` and `advanced-ar.html` are working locally
- [ ] Custom 3D models (if any) are optimized (< 5MB each)
- [ ] HTTPS is enabled on your hosting platform
- [ ] QR code points to the correct URL

## 🔧 Custom Model Integration

### Converting Unity Models to Web Format

1. **Export from Unity:**
   - Select your 3D model in Unity
   - File → Export → FBX
   - Choose appropriate settings

2. **Convert to GLB:**
   - Use online converters like [gltf.report](https://gltf.report)
   - Or use Blender to convert FBX to GLB
   - Ensure file size is under 5MB

3. **Add to Project:**
   ```bash
   # Create models directory
   mkdir models
   # Copy your GLB files here
   cp your-model.glb models/
   ```

4. **Update HTML:**
   ```html
   <!-- Add to model selector -->
   <div class="model-option" onclick="selectModel('your-model')">🏛️ Your Model</div>
   
   <!-- Add to JavaScript -->
   case 'your-model':
       model = document.createElement('a-entity');
       model.setAttribute('gltf-model', './models/your-model.glb');
       model.setAttribute('scale', '0.5 0.5 0.5');
       break;
   ```

## 🌐 Domain Setup (Optional)

### Custom Domain
1. Purchase a domain (e.g., from Namecheap, GoDaddy)
2. Configure DNS settings to point to your hosting platform
3. Update your QR codes with the new domain

### Subdomain
- Most hosting platforms allow custom subdomains
- Example: `ar.yourcompany.com`

## 📱 Testing Checklist

### Device Testing
- [ ] iPhone (Safari)
- [ ] Android (Chrome)
- [ ] Android (Firefox)
- [ ] Desktop browsers (for testing)

### Feature Testing
- [ ] Camera access works
- [ ] QR code scanning works
- [ ] Model placement works
- [ ] Model interactions work
- [ ] UI is responsive
- [ ] Loading times are acceptable

## 🔍 Troubleshooting Deployment

### Common Issues

**QR Code Not Working:**
- Verify URL is accessible
- Check for typos in URL
- Ensure HTTPS is enabled
- Test with different QR scanners

**AR Not Working:**
- Check browser console for errors
- Verify camera permissions
- Ensure HTTPS is enabled
- Test on supported devices

**Slow Loading:**
- Optimize 3D model file sizes
- Compress textures
- Use CDN for external libraries
- Enable gzip compression

### Performance Optimization

1. **Model Optimization:**
   - Reduce polygon count
   - Compress textures
   - Use LOD (Level of Detail)
   - Optimize file formats

2. **Code Optimization:**
   - Minify JavaScript and CSS
   - Enable browser caching
   - Use CDN for libraries
   - Optimize images

## 📊 Analytics Setup (Optional)

### Google Analytics
```html
<!-- Add to your HTML files -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Custom Tracking
```javascript
// Track model placements
function trackModelPlacement(modelType) {
    gtag('event', 'model_placed', {
        'model_type': modelType,
        'timestamp': Date.now()
    });
}
```

## 🔒 Security Considerations

1. **HTTPS Required:**
   - AR features require secure connection
   - Most hosting platforms provide HTTPS by default

2. **Content Security Policy:**
   ```html
   <meta http-equiv="Content-Security-Policy" content="default-src 'self' 'unsafe-inline' 'unsafe-eval' data: blob: https:; img-src 'self' data: https:; media-src 'self' https:;">
   ```

3. **Privacy:**
   - Camera access is required
   - No personal data is collected
   - Consider adding privacy policy

## 📞 Support Resources

- **AR.js Documentation:** https://ar-js-org.github.io/AR.js/
- **A-Frame Documentation:** https://aframe.io/docs/
- **WebXR API:** https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API
- **Three.js Documentation:** https://threejs.org/docs/

---

**Need help?** Check the troubleshooting section in the main README or contact support. 