# Contoso Coffee Website

**Version 6e - Contact Form Updated**

Premium commercial and consumer coffee solutions website with dark theme, product catalog, customer success stories, and contact form.

## 🎯 Latest Update (v6e)

**✅ Contact Form Updated:**
- **Removed "Demo Lead" button** that prefilled form fields with demo data
- Maintained all original design, styling, and functionality
- Preserved Power Automate integration for lead capture
- All other pages remain unchanged

## 📁 File Structure

```
contoso-coffee-website/
├── index.html              # Homepage with hero and feature cards
├── products.html           # Product catalog with accordion categories
├── customers.html          # Customer success stories and testimonials
├── contact.html            # Contact form (UPDATED - no demo button)
├── assets/
│   ├── enriched_products.json  # Product data (60+ products)
│   └── img/
│       ├── logo.svg        # Contoso Coffee logo
│       └── favicon.svg     # Site favicon
└── README.md              # This file
```

## 🎨 Design System

**Dark Theme Color Palette:**
- Background: `#0f0a08` (Deep coffee brown)
- Surface: `#17110e` (Darker surface)
- Card: `#211813` (Card backgrounds)
- Text: `#f5efe9` (Off-white text)
- Muted: `#cbbfba` (Muted secondary text)
- Brand: `#c08a59` (Warm copper/gold accent)
- Line: `rgba(255,255,255,.08)` (Subtle borders)

**Design Features:**
- Dark, sophisticated coffee-inspired theme
- Responsive grid layouts
- Sticky navigation with backdrop blur effect
- Card-based design with elegant shadows
- Accordion product catalog (expand/collapse)
- Hero sections with image overlays
- Embedded styling (no external CSS file needed)
- Form integration with Power Automate

## 🚀 Deployment to GitHub Pages

### Quick Deploy

1. **Navigate to your repository:**
   ```bash
   cd contoso-coffee-website
   ```

2. **Replace the files:**
   ```bash
   # Optional: Backup old version
   git checkout -b backup-v6d
   git checkout main
   
   # Copy all new files
   cp /path/to/updated/files/*.html .
   cp -r /path/to/updated/files/assets ./
   ```

3. **Commit and push:**
   ```bash
   git add .
   git commit -m "Update contact form - remove demo button (v6e)"
   git push origin main
   ```

4. **Verify deployment:**
   - Visit: https://eboocock.github.io/contoso-coffee-website/
   - Check contact page: https://eboocock.github.io/contoso-coffee-website/contact.html
   - Changes appear within 1-2 minutes

### Alternative: Manual Upload via GitHub UI

1. Go to your repository: https://github.com/eboocock/contoso-coffee-website
2. Click "Upload files"
3. Drag all HTML files and assets folder
4. Commit changes
5. Wait 1-2 minutes for GitHub Pages to rebuild

## 📋 Page Details

### Homepage (index.html)
- Hero section with background image
- "Why Contoso" section with 3 feature cards:
  - Commercial & Consumer Portfolio
  - Nationwide Support & Service
  - Responsible by Design (Sustainability)
- Professional footer

### Products (products.html)
- **Accordion-based catalog** organized by category
- **Expand/collapse all** controls for easy navigation
- **Rich product cards** featuring:
  - Product images (unique per SKU)
  - SKU badges
  - Product metadata (category, tags, type)
  - Detailed descriptions
  - Features list
  - Technical specifications table
  - Pricing
  - "Request Quote" CTA buttons
- **60+ products** across categories:
  - Coffee Beans
  - Consumer Machines
  - Commercial Machines
  - Grinders
  - Accessories & Supplies

### Customers (customers.html)
- **Case studies** from major clients
- Quantified business impact (annual revenue)
- "Why Contoso" reasoning
- **Customer testimonials** with names and titles
- Professional card-based layout

### Contact (contact.html) ✨ UPDATED
- **Clean, professional contact form**
- **Form Fields:**
  - First Name (required)
  - Last Name (required)
  - Company (required)
  - Email (required)
  - Area of Interest dropdown (required)
  - Message (optional textarea)
- **Power Automate integration** for lead capture
- **Fallback behavior**: Downloads JSON if Flow not configured
- **Badge indicator**: "Submits to Power Automate → Dataverse Lead"
- **✅ Demo button removed** (was: "Demo Lead" button)

## 🔧 Configuration

### Power Automate Integration

The contact form submits to Power Automate → Dataverse Lead. 

**To configure:**

1. **Open `contact.html`** and locate line 158
2. **Update the `FLOW_URL` constant:**
   ```javascript
   const FLOW_URL = "YOUR_POWER_AUTOMATE_HTTP_TRIGGER_URL";
   ```

3. **Create a Power Automate flow:**
   - Trigger: **When an HTTP request is received**
   - Use this JSON schema:
     ```json
     {
       "type": "object",
       "properties": {
         "firstName": {"type":"string"},
         "lastName": {"type":"string"},
         "company": {"type":"string"},
         "email": {"type":"string"},
         "interest": {"type":"string"},
         "message": {"type":"string"},
         "source": {"type":"string"},
         "submittedUtc": {"type":"string"}
       }
     }
     ```
   - Action: **Add a new row** → Dataverse → **Leads** table
   - Map fields:
     - Topic: `Contoso Website: {firstName} {lastName}`
     - First Name: `{firstName}`
     - Last Name: `{lastName}`
     - Company Name: `{company}`
     - Email: `{email}`
     - Lead Source: `Website`
     - Description: `Interest: {interest}\n\nMessage: {message}\nSubmitted: {submittedUtc}`

4. **Copy the HTTP POST URL** from the trigger
5. **Paste into `contact.html`** and save/deploy

**Current behavior:**
- ✅ If Flow URL configured: Submits to Dataverse as Lead
- ⚠️ If Flow URL missing/invalid: Downloads submission as JSON file (fallback)

### Form Data Structure

Data sent to Power Automate:
```json
{
  "firstName": "string",
  "lastName": "string",
  "company": "string",
  "email": "string",
  "interest": "Commercial Machines | Consumer Machines | Beans & Subscriptions | Training & Service | Other",
  "message": "string (optional)",
  "source": "Contoso Coffee Website",
  "submittedUtc": "2025-10-22T19:15:00.000Z"
}
```

## 🖼️ Images

**Homepage & Customer Pages:**
- Use high-quality Pexels images (free commercial use)
- Professional coffee/barista photography

**Product Images:**
- Generated using `https://picsum.photos/seed/<SKU>/1200/675`
- Deterministic placeholders (same SKU = same image)
- **To replace:** Edit `assets/enriched_products.json` and update `Image` property

**Logo & Favicon:**
- Custom SVG files in `assets/img/`
- Dark theme with copper accent

## 🌐 Live Website

**Production URL:** https://eboocock.github.io/contoso-coffee-website/

**Pages:**
- Home: `/` or `/index.html`
- Products: `/products.html`
- Customer Success: `/customers.html`
- Contact: `/contact.html`

## 📱 Responsive Design

**Desktop (>860px):**
- Multi-column grid layouts
- Sticky navigation
- Full hero images
- Two-column product details

**Tablet (720px - 860px):**
- Adjusted columns
- Maintained all features
- Responsive forms

**Mobile (<720px):**
- Single column layouts
- Optimized touch targets
- Adjusted hero height (44vh)
- Stacked form fields

## ✅ What Changed in v6e

### Modified Files
- **`contact.html`**:
  - Removed `<button type="button" class="cta" onclick="fillDemo()">Demo Lead</button>`
  - Removed `fillDemo()` JavaScript function (lines 192-207)
  - Maintained all styling, layout, and Power Automate integration

### Unchanged Files
- `index.html`: No changes
- `products.html`: No changes
- `customers.html`: No changes
- `assets/enriched_products.json`: No changes
- `assets/img/logo.svg`: No changes
- `assets/img/favicon.svg`: No changes

### Preserved Functionality
- ✅ Power Automate integration
- ✅ Form validation
- ✅ Fallback to JSON download
- ✅ All styling and layout
- ✅ Responsive design
- ✅ Navigation and footer
- ✅ Dark theme design system

## 🔄 Version History

- **v6e** (October 22, 2025): Removed demo button from contact form
- **v6d**: Previous version with demo data button
- **v6**: Initial production build with dark theme
- Earlier: Development versions

## 🛠️ Technical Details

**Technologies:**
- Pure HTML5 (no frameworks)
- Embedded CSS (no external stylesheets)
- Vanilla JavaScript (no dependencies)
- SVG graphics
- JSON product data

**Browser Support:**
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS, Android)

**Performance:**
- Lightweight pages (<150KB each)
- Fast load times
- No external dependencies
- Optimized images

## 📞 Support & Troubleshooting

### Common Issues

**Problem:** Form doesn't submit
- **Solution:** Check if `FLOW_URL` is configured in `contact.html`
- **Fallback:** Form will download JSON file locally

**Problem:** Products don't expand
- **Solution:** Ensure JavaScript is enabled
- **Check:** Browser console for errors

**Problem:** Images don't load
- **Solution:** Verify `assets/` folder is deployed
- **Check:** Network tab in developer tools

### Testing Locally

```bash
# Simple Python server
python -m http.server 8000

# Visit: http://localhost:8000
```

## 📝 Customization Guide

### Update Products
1. Edit `assets/enriched_products.json`
2. Follow existing product structure
3. Redeploy to GitHub Pages

### Change Colors
- Edit CSS variables in `<style>` section
- Update `:root` color definitions
- Colors are consistent across all pages

### Modify Form Fields
1. Open `contact.html`
2. Find the `<form>` section
3. Add/remove fields as needed
4. Update Power Automate schema to match

## 🎯 Next Steps

1. **Deploy updated files** to GitHub Pages
2. **Test contact form** submission
3. **Verify Power Automate** flow is receiving data
4. **Check Dataverse Leads** table for new entries
5. **Monitor for any issues**

---

**© 2025 Contoso Coffee. All rights reserved.**  
*Ethically sourced • Carbon-neutral roasting • Global service network*

**Questions?** Check the GitHub repository or contact your administrator.
