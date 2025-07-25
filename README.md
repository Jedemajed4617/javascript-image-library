# JavaScript Image Library Documentation

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Installation](#installation)
4. [Quick Start](#quick-start)
5. [Configuration](#configuration)
6. [API Reference](#api-reference)
7. [Examples](#examples)
8. [Troubleshooting](#troubleshooting)
9. [Browser Support](#browser-support)
10. [License](#license)

---

## Overview

The **JavaScript Image Library** is a modern, lightweight solution for creating beautiful image galleries with fullscreen viewing capabilities. Designed as a replacement for expensive commercial libraries like FancyBox, it provides all essential features while remaining free and open-source.

**Version:** 0.0.3  
**Dependencies:** jQuery 3.7.1+  
**License:** [Propietary](#license)

---

## Features

### 🖼️ **Fullscreen Viewing**
- Immersive fullscreen image experience
- Smooth transitions and animations
- Dark overlay background
- Click outside to close

### 🎠 **Carousel Navigation**
- Seamless gallery browsing
- Thumbnail navigation
- Previous/Next arrows
- Image counter display

### 👆 **Touch & Swipe**
- Native touch gestures
- Swipe navigation on mobile
- Pinch to zoom support
- Drag to pan when zoomed

### 🔍 **Zoom & Pan**
- High-quality zoom functionality
- Smooth panning controls
- Mouse wheel zoom
- Double-tap to zoom on mobile

### ⏯️ **Autoplay Mode**
- Automatic slideshow
- Customizable timing (3 seconds default)
- Play/pause controls
- Progress indicator

### ⌨️ **Keyboard Support**
- Arrow keys for navigation
- ESC to close viewer
- Space bar for autoplay toggle
- Enter to toggle fullscreen

---

## Installation

### Method 1: CDN (Recommended)

Include the required dependencies in your HTML:

```html
<!-- jQuery (Required) -->
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
// Or the latest version :)

<!-- JavaScript Image Library (From github) -->
<script src="https://cdn.jsdelivr.net/gh/jedemajed4617/javascript-image-library/javascript-img-lib.js"></script>
<script src="https://cdn.jsdelivr.net/gh/jedemajed4617/javascript-image-library/javascript-img-lib.css"></script>
```

### Method 2: Download

1. Download the complete zip from the website
2. Extract the files to your project directory
3. Include the CSS and JS files in your HTML

---

## Quick Start guide

### Step 1: HTML Structure

Create a container with the required attributes and add images with the `gallery_image` class:

```html
<!-- Gallery Mode -->
<div data-velisoft-img-lib="gallery" data-velisoft-img-libcontrols="true">
    <img src="image1.jpg" alt="Image 1" class="gallery_image">
    <img src="image2.jpg" alt="Image 2" class="gallery_image">
    <img src="image3.jpg" alt="Image 3" class="gallery_image">
</div>

<!-- Single Image Mode -->
<div data-velisoft-img-lib="single" data-velisoft-img-libcontrols="true">
    <img src="hero-image.jpg" alt="Hero Image" class="gallery_image">
</div>
```

### Step 2: Initialize

The library automatically initializes when the DOM is ready. No additional JavaScript code is required!

---

## Configuration

### Container Attributes

#### `data-velisoft-img-lib`
**Required** - Defines the viewing mode
- `"gallery"` - Multiple images with navigation
- `"single"` - Single image viewer

#### `data-velisoft-img-libcontrols`
**Optional** - Controls UI visibility
- `"true"` - Show all controls (default)
- `"false"` - Hide zoom, pan, autoplay controls

### Image Requirements

#### `class="gallery_image"`
**Required** - All images must have this class to be included in the library

#### Image Attributes
- `src` - Image URL (required)
- `alt` - Alternative text (recommended)
- `title` - Image title (optional, displayed in viewer)

---

## API Reference

### Global Variables

```javascript
// Current image index in gallery
let currentImageIndex = 0;

// Array of current gallery images
let currentImages = [];

// Autoplay state
let isAutoplayActive = false;

// Zoom state
let isZoomed = false;
let currentZoomLevel = 1;
```

### Functions explained

#### `initializeImageLibrary()`
Initializes the library for all containers on the page.

#### `openFullscreen(imageElement, images)`
Opens the fullscreen viewer for a specific image.
- `imageElement` - The clicked image element
- `images` - Array of gallery images

#### `closeFullscreen()`
Closes the fullscreen viewer and returns to normal view.

#### `nextImage()`
Navigates to the next image in the gallery.

#### `previousImage()`
Navigates to the previous image in the gallery.

#### `toggleAutoplay()`
Starts or stops the autoplay slideshow.

#### `zoomIn()` / `zoomOut()`
Controls zoom functionality in fullscreen mode.

---

## Some code exmaples

### Basic Gallery

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="velisoft-img-lib.css">
</head>
<body>
    <div data-velisoft-img-lib="gallery">
        <img src="photo1.jpg" alt="Photo 1" class="gallery_image">
        <img src="photo2.jpg" alt="Photo 2" class="gallery_image">
        <img src="photo3.jpg" alt="Photo 3" class="gallery_image">
    </div>
    
    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
    <script src="velisoft-img-lib.js"></script>
</body>
</html>
```

### Portfolio Gallery with Custom Styling

```html
<div class="portfolio-grid" data-velisoft-img-lib="gallery" data-velisoft-img-libcontrols="true">
    <div class="portfolio-item">
        <img src="project1.jpg" alt="Project 1" class="gallery_image portfolio-image">
        <div class="portfolio-overlay">
            <h3>Project Title</h3>
            <p>Project description</p>
        </div>
    </div>
    <div class="portfolio-item">
        <img src="project2.jpg" alt="Project 2" class="gallery_image portfolio-image">
        <div class="portfolio-overlay">
            <h3>Another Project</h3>
            <p>Project description</p>
        </div>
    </div>
</div>
```

### Product Images

```html
<div class="product-gallery" data-velisoft-img-lib="gallery">
    <div class="main-image">
        <img src="product-main.jpg" alt="Product Main View" class="gallery_image">
    </div>
    <div class="thumbnail-grid">
        <img src="product-side.jpg" alt="Product Side View" class="gallery_image thumbnail">
        <img src="product-back.jpg" alt="Product Back View" class="gallery_image thumbnail">
        <img src="product-detail.jpg" alt="Product Detail" class="gallery_image thumbnail">
    </div>
</div>
```

### Single Hero Image

```html
<section class="hero">
    <div data-velisoft-img-lib="single" data-velisoft-img-libcontrols="false">
        <img src="hero-bg.jpg" alt="Hero Background" class="gallery_image hero-image">
    </div>
    <div class="hero-content">
        <h1>Welcome to Our Site</h1>
        <p>Click the image to view in fullscreen</p>
    </div>
</section>
```

---

## Troubleshooting

### Common Issues

#### Images Not Clickable?
**Problem:** Images don't open in fullscreen when clicked.
**Solution:** 
- Ensure images have `class="gallery_image"`
- Check that jQuery is loaded before the library
- Verify container has `data-velisoft-img-lib` attribute

#### Smooth Scroll Conflicts?
**Problem:** Page scrolls to top when closing fullscreen.
**Solution:** 
```css
/* Remove this CSS rule */
html {
    scroll-behavior: smooth; /* ❌ Remove this */
}
```

#### Mobile Touch Issues?
**Problem:** Touch gestures not working on mobile.
**Solution:**
- Ensure images are properly sized
- Check for CSS that might interfere with touch events
- Test on actual device rather than browser dev tools

#### Zoom Not Working?
**Problem:** Zoom functionality doesn't respond.
**Solution:**
- Check that `data-velisoft-img-libcontrols="true"`
- Ensure images are high enough resolution
- Verify no CSS transforms are interfering

### Performance Tips

1. **Optimize Images**: Use appropriate image sizes and formats (WebP when possible)
2. **Lazy Loading**: Consider implementing lazy loading for large galleries
3. **Preload**: Preload adjacent images in galleries for smoother navigation
4. **CSS**: Minimize CSS conflicts by using specific selectors

---

## Browser Support

### Fully Supported
- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+

### Partially Supported
- ⚠️ Internet Explorer 11 (limited touch support)
- ⚠️ Older mobile browsers (basic functionality only)

### Required Features
- CSS Grid support
- Flexbox support
- Touch events (for mobile)
- CSS transforms
- jQuery 3.7.1+

---

## CSS Customization

### Custom Styling

You can override default styles by adding your own CSS after the library CSS:

```css
/* Custom overlay background */
#fullscreen_container {
    background-color: rgba(255, 255, 255, 0.95) !important;
}

/* Custom control buttons */
.fullscreen-controls button {
    background: #your-color !important;
    color: white !important;
}

/* Custom thumbnail styling */
.carousel-thumbnails img {
    border: 2px solid #your-accent-color !important;
}
```

### Dark/Light Theme

```css
/* Dark theme (default) */
:root {
    --overlay-bg: rgba(0, 0, 0, 0.9);
    --control-bg: rgba(255, 255, 255, 0.1);
    --text-color: white;
}

/* Light theme */
.light-theme {
    --overlay-bg: rgba(255, 255, 255, 0.95);
    --control-bg: rgba(0, 0, 0, 0.1);
    --text-color: black;
}
```

---

## Advanced Configuration

### Custom Event Handlers

```javascript
// Listen for library events
$(document).on('fullscreen:opened', function(event, imageData) {
    console.log('Fullscreen opened:', imageData);
});

$(document).on('fullscreen:closed', function() {
    console.log('Fullscreen closed');
});

$(document).on('image:changed', function(event, newIndex) {
    console.log('Image changed to index:', newIndex);
});
```

### Programmatic Control

```javascript
// Open specific image programmatically
const images = $('.gallery_image');
const targetImage = images[2]; // Third image
openFullscreen(targetImage, images);

// Control autoplay
toggleAutoplay();

// Navigate programmatically
nextImage();
previousImage();
```

---

## Updates & Changelog

### Version 0.0.4 (Future)
- CSS reworked 
- Better animations
- Better feel (like an app)
  
### Version 0.0.3 (Current)
- ✅ Added infinite scroll
- ✅ Enhanced carousel functionality
- ✅ Improved zoom/pan behavior
- ✅ Reworked CSS for better performance
- ✅ Added keyboard navigation
- ✅ Mobile touch improvements

### Version 0.0.2
- ✅ Basic gallery functionality
- ✅ Fullscreen viewing
- ✅ Touch support
- ✅ Zoom capabilities

### Version 0.0.1
- ✅ Initial release
- ✅ Basic image viewing
- ✅ Simple navigation

---

## Support

### Getting Help
- 📧 **Email**: tygo@velisoft.nl
- 🌐 **Website**: https://tgsoftware.services
- 📱 **GitHub**: https://github.com/Jedemajed4617

### Reporting Issues
When reporting issues, please include:
1. Browser and version
2. Device type (desktop/mobile)
3. Steps to reproduce
4. Expected vs actual behavior
5. Console errors (if any)

---

## License

### Commercial Standard License
Preamble/intro This software license may be freely used in unmodified form (with exceptions). A work may only be copyrighted under this license in its unmodified form, or with some subsections removed or swapped out. Details todo.
Overview These are the changes made to this specific license: Copyright Owner: Tygo Jedema Product Name: Javascript-img-lib License Modifications Source code is NOT provided. Warranty is NOT given. You are allowed to have this software installed on 4 machine(s) at once. Commercial use is NOT allowed.
Definitions "Product", or "software" refers to the work that is copyrighted under this license.
"We", or "us" refer to the copyright owner of this product. That owner is Tygo Jedema
"You" refers to the licensee of this product.
License, not purchase By purchasing this license, you are allowed to use this product, but we retain the copyright to the software.
Redistribution You may not redistribute or resell the software.
Warranty This product does NOT come with any warranty, express or implied, notwithstanding legislation to the contrary.
Source Code This software does NOT provide the source code, and it is NOT legal to attempt to aquire it, whether by reverse engineering or otherwise.

Note: If the owner wishes to provide the source code, remove the NOTs in the paragraph above. In either case, remove this notice.

---

## Final Notes

This library is actively maintained. For the latest version and updates, visit our website or GitHub repository.

**Happy coding! 🚀**
