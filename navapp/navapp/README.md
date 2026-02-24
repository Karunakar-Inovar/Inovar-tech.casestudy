# NavApp Marketing Website

A pixel-perfect, single-page marketing website built with HTML and Tailwind CSS (via CDN). No build tools required.

## Project Structure

```
navapp/
├── index.html          # Main HTML file
├── styles/
│   └── global.css      # Custom CSS with design tokens
├── scripts/
│   └── main.js         # Mobile menu & smooth scroll
├── assets/
│   ├── images/         # Place images here
│   └── icons/          # Place icons here
├── DEPLOYMENT.md       # Deployment guide
└── README.md           # This file
```

## Quick Start

1. **Open locally**: Simply open `index.html` in your browser
2. **Or use a local server**:
   ```bash
   # Python
   python -m http.server 8000
   
   # Node.js
   npx serve
   
   # PHP
   php -S localhost:8000
   ```

## Design Tokens

Colors are defined in:
- Tailwind config (in `<script>` tag in HTML)
- CSS variables in `styles/global.css`

**Current Colors:**
- Primary: `#7A75E6` (muted purple)
- Text Dark: `#1A1A1A`
- Text Muted: `#6B7280`
- Background Dark: `#101010`
- Background Light: `#F8F8F8`

**Font:** Inter (from Google Fonts)

## Features

- ✅ Responsive design (mobile-first approach)
- ✅ Mobile menu toggle
- ✅ Smooth scroll navigation
- ✅ Active section highlighting
- ✅ Pixel-perfect spacing and typography
- ✅ Semantic HTML
- ✅ Accessibility considerations

## Adding Images

1. Place images in `/assets/images/`
2. Reference them in HTML:
   ```html
   <img src="assets/images/hero-image.jpg" alt="Description" loading="lazy">
   ```

## Customization

### Change Colors
Edit the Tailwind config in `index.html`:
```javascript
colors: {
    primary: '#YOUR_COLOR',
    // ...
}
```

### Change Fonts
1. Update Google Fonts link in `<head>`
2. Update `fontFamily` in Tailwind config

## Deployment

See `DEPLOYMENT.md` for detailed Vercel deployment instructions.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

© 2026 NavApp. All rights reserved.
