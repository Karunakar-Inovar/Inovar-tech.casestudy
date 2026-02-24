# NavApp Website - Deployment Guide

## If you get 404 on Vercel

1. **Root Directory** (most common): In Vercel → Project → **Settings** → **General** → **Root Directory**. Leave it **empty** (or `.`) so the repo root—where `index.html` lives—is used. If your repo has the site in a subfolder, set Root Directory to that folder (e.g. `navapp`).
2. **Framework**: In **Settings** → **General** → **Framework Preset**, set to **Other**.
3. **Build & Output**: **Build Command** and **Output Directory** can be left empty; `vercel.json` handles the static deployment.
4. Redeploy after changing settings (**Deployments** → ⋮ on latest → **Redeploy**).

## Vercel Deployment Steps

### Option 1: Deploy via Vercel CLI (Recommended)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Navigate to project directory**:
   ```bash
   cd /Users/karunakarkadari/Desktop/navapp
   ```

4. **Deploy**:
   ```bash
   vercel
   ```
   - Follow the prompts
   - Choose "Y" for production deployment
   - Your site will be live at a `vercel.app` URL

5. **For production domain** (optional):
   ```bash
   vercel --prod
   ```

### Option 2: Deploy via Vercel Dashboard

1. **Go to [vercel.com](https://vercel.com)** and sign in

2. **Click "Add New Project"**

3. **Import your Git repository** (if using Git):
   - Connect your GitHub/GitLab/Bitbucket account
   - Select the repository
   - Vercel will auto-detect it's a static site

4. **Or drag & drop** the `navapp` folder directly:
   - Drag the entire folder to Vercel dashboard
   - It will automatically deploy

5. **Configure build settings** (if needed):
   - **Framework Preset**: Other
   - **Build Command**: (leave empty - static site)
   - **Output Directory**: (leave empty - root is output)
   - **Install Command**: (leave empty - no dependencies)

6. **Deploy**

### Option 3: Deploy via GitHub Integration

1. **Initialize Git** (if not already):
   ```bash
   cd /Users/karunakarkadari/Desktop/navapp
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Create a GitHub repository** and push:
   ```bash
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

3. **Connect to Vercel**:
   - Go to Vercel dashboard
   - Click "Add New Project"
   - Import your GitHub repository
   - Vercel will auto-deploy on every push

## Post-Deployment Checklist

- [ ] Verify site loads correctly at deployed URL
- [ ] Test mobile menu functionality
- [ ] Test smooth scroll navigation
- [ ] Verify all images load (if you add any)
- [ ] Check responsive design on mobile/tablet/desktop
- [ ] Test all links and buttons
- [ ] Verify fonts load correctly (Inter from Google Fonts)

## Custom Domain Setup (Optional)

1. In Vercel dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Follow DNS configuration instructions

---

## Figma Comparison Checklist

Use this checklist to compare your deployed site with the Figma design:

### Layout & Structure
- [ ] All sections appear in correct order
- [ ] Section spacing matches Figma (vertical padding)
- [ ] Container max-widths match design
- [ ] Grid layouts (cards, features) match Figma layout

### Typography
- [ ] Font family matches (Inter)
- [ ] H1 size matches hero heading (5xl-7xl)
- [ ] H2 size matches section headings (4xl-5xl)
- [ ] Body text size matches (lg-xl)
- [ ] Line heights match design
- [ ] Font weights match (bold for headings, regular for body)

### Colors
- [ ] Primary purple color matches (#7A75E6)
- [ ] Dark text color matches (#1A1A1A)
- [ ] Muted text color matches (#6B7280)
- [ ] Dark background matches (#101010)
- [ ] Light background matches (#F8F8F8 or white)
- [ ] Button colors match (primary bg, white text)

### Spacing
- [ ] Padding inside cards matches
- [ ] Gap between cards matches
- [ ] Section padding (py-20) matches vertical spacing
- [ ] Container padding (px-6 lg:px-8) matches horizontal spacing

### Components
- [ ] Navigation bar matches (logo left, links right, CTA button)
- [ ] Hero section layout matches
- [ ] Statistics cards match (4 cards, rounded corners, shadow)
- [ ] Problem cards match (3 cards, dark bg, numbered icons)
- [ ] Feature cards match (numbered backgrounds, rounded corners)
- [ ] Intelligence grid matches (2x2 layout, purple bg)
- [ ] Testimonial quote styling matches
- [ ] Footer matches (copyright left, links right)

### Interactive Elements
- [ ] Button hover states match (opacity change, shadow)
- [ ] Card hover effects match (shadow increase)
- [ ] Link hover colors match (primary color)
- [ ] Mobile menu opens/closes correctly

### Responsive Design
- [ ] Desktop layout matches Figma (desktop-first)
- [ ] Tablet breakpoint works (md:)
- [ ] Mobile layout stacks correctly (single column)
- [ ] Mobile menu appears on small screens
- [ ] Text sizes scale appropriately

### Visual Details
- [ ] Border radius matches (rounded-xl = 12px)
- [ ] Shadow intensity matches (shadow-sm, shadow-md)
- [ ] Border colors match (gray-200, gray-800)
- [ ] Icon sizes match (if you add icons)

### Content Accuracy
- [ ] All headings match Figma text exactly
- [ ] All body text matches
- [ ] Statistics numbers match
- [ ] Button labels match ("Contact Us")
- [ ] Footer text matches

---

## Notes

- **Design Tokens**: Colors are defined in both Tailwind config and CSS variables for flexibility
- **Fonts**: Using Inter from Google Fonts (matches modern sans-serif design)
- **Images**: Place any images in `/assets/images/` and reference them with relative paths
- **Icons**: Place SVG icons in `/assets/icons/` or use inline SVG (as done for mobile menu)

## Troubleshooting

### If fonts don't load:
- Check Google Fonts CDN is accessible
- Verify font-family is applied correctly

### If styles don't apply:
- Check Tailwind CDN is loading
- Verify CSS file path is correct (relative path)
- Check browser console for errors

### If JavaScript doesn't work:
- Check JS file path is correct (relative path)
- Verify DOMContentLoaded event fires
- Check browser console for errors

### If mobile menu doesn't work:
- Check JavaScript file is loaded
- Verify element IDs match (mobile-menu-btn, mobile-menu)
- Check browser console for errors
