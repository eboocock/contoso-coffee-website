# Contoso Coffee Website - Visual Theme Guide

## 🎨 Color Palette

### Primary Colors (Coffee Browns)
```
Coffee Dark:   #3E2723  ██████  Main headers, footer
Coffee Medium: #5D4037  ██████  Subheadings, links
Coffee Light:  #8D6E63  ██████  Accents, borders
Coffee Cream:  #D7CCC8  ██████  Light backgrounds
```

### Accent Colors
```
Accent Gold:   #C9A961  ██████  CTAs, highlights
Accent Green:  #7CB342  ██████  Sustainability
Accent Orange: #FF6F00  ██████  Special offers
```

### Neutral Colors
```
White:         #FFFFFF  ██████  Card backgrounds
Off-White:     #FAF8F6  ██████  Page background
Gray Light:    #EEEBE8  ██████  Section backgrounds
Gray Medium:   #9E9E9E  ██████  Secondary text
```

## 📐 Layout Structure

### Header (All Pages)
```
┌─────────────────────────────────────────────┐
│  ☕ Contoso Coffee    Home Products About Contact │
└─────────────────────────────────────────────┘
```
- Sticky navigation
- Coffee brown gradient background
- Logo with coffee cup icon
- Hover effects on links

### Hero Section (All Pages)
```
┌─────────────────────────────────────────────┐
│                                              │
│            [Page Title]                      │
│            Descriptive text                  │
│                                              │
└─────────────────────────────────────────────┘
```
- Rich coffee gradient background
- White text with text-shadow
- Centered content
- Optional CTA buttons

### Content Sections
```
┌─────────────────────────────────────────────┐
│  Section Title                               │
│  Descriptive text                            │
│                                              │
│  ┌─────┐  ┌─────┐  ┌─────┐                 │
│  │Card │  │Card │  │Card │                  │
│  └─────┘  └─────┘  └─────┘                 │
└─────────────────────────────────────────────┘
```
- Alternating white and cream backgrounds
- Cards with shadow and hover effects
- Grid layouts (2, 3, or 4 columns)

### Footer (All Pages)
```
┌─────────────────────────────────────────────┐
│  About         Quick Links    Contact Info  │
│  [Company      [Navigation]   [Phone/Email] │
│   description]                               │
│                                              │
│  © 2025 Contoso Coffee                      │
└─────────────────────────────────────────────┘
```
- Dark coffee brown background
- Three-column grid
- Links in cream color
- Gold accent headings

## 🖼️ Component Examples

### Logo Usage
```html
☕ Contoso Coffee
```
- Coffee cup emoji (☕) as icon
- Georgia font family
- Size: 1.75rem
- Color: White on dark, dark brown on light

### Buttons
```
Primary:   [Send Message]     Gold background, dark text
Secondary: [Learn More]       Transparent with border
Large:     [Get Started]      Increased padding
```

### Cards
```
┌─────────────────┐
│  Card Title     │
│ ─────────────── │
│  Card content   │
│  with details   │
└─────────────────┘
```
- White background
- Rounded corners (12px)
- Subtle shadow
- Hover: lift effect

### Forms
```
Label
┌────────────────────┐
│ Input field        │
└────────────────────┘
```
- Gold border on focus
- 2px border width
- Rounded corners
- Comfortable padding

## 📄 Page-Specific Elements

### Homepage (index.html)
- Hero with 2 CTA buttons
- "Why Choose" 3-column feature grid
- Product categories 4-column grid
- Industry segments cards
- Full-width dark CTA section

### Products (products.html)
- Product cards with "Best Seller" / "New" tags
- Price display in gold
- Gradient product image placeholders
- Equipment section with detailed specs
- Supplies grid with icons

### About (about.html)
- Two-column story section
- Timeline with year markers
- Statistics grid with large numbers
- Leadership team cards with avatars
- Sustainability commitment section

### Contact (contact.html)
- Info box at top (cream background, gold border)
- Two-column form layout (name fields)
- Full-width textarea
- Dropdown for inquiry type
- Large submit button
- NO demo data button

## 🎯 Typography

### Headings
```
H1: Georgia, 2.5rem (40px), Bold
H2: Georgia, 2rem (32px), Semibold
H3: Georgia, 1.5rem (24px), Semibold
H4: Georgia, 1.25rem (20px), Medium
```

### Body Text
```
Paragraph: Segoe UI, 1rem (16px), Regular
Small:     Segoe UI, 0.875rem (14px), Regular
Large:     Segoe UI, 1.125rem (18px), Regular
```

### Special Text
```
Price:     1.5rem (24px), Bold, Gold
Stats:     3rem (48px), Bold, Gold
```

## 💫 Interactive Elements

### Hover Effects
- **Links**: Color change to gold
- **Buttons**: Lift + shadow increase
- **Cards**: Slight lift (-4px)
- **Navigation**: Background highlight

### Focus States
- **Inputs**: Gold border + glow
- **Buttons**: Outline visible
- **Links**: Underline appears

### Transitions
- All: 0.3s ease
- Smooth, professional feel
- Never instant

## 📱 Responsive Behavior

### Desktop (1200px+)
- 3-4 column grids
- Full navigation
- Larger hero sections

### Tablet (768px - 1199px)
- 2 column grids
- Adjusted spacing
- Wrapped navigation

### Mobile (< 768px)
- Single column layout
- Stacked navigation
- Larger touch targets
- Reduced font sizes

## ✨ Special Features

### Gradient Backgrounds
```css
Hero: linear-gradient(135deg, #3E2723 0%, #5D4037 50%, #4A332A 100%)
```

### Shadow Levels
```css
Small:  0 2px 4px rgba(62, 39, 35, 0.1)
Medium: 0 4px 12px rgba(62, 39, 35, 0.15)
Large:  0 8px 24px rgba(62, 39, 35, 0.2)
```

### Border Radius
```css
Small:  4px   (buttons, small elements)
Medium: 8px   (inputs, cards)
Large:  12px  (major cards)
XLarge: 20px  (hero sections)
```

## 🔍 Accessibility Features

- ✅ WCAG AA color contrast
- ✅ Semantic HTML5
- ✅ Keyboard navigation
- ✅ Focus indicators
- ✅ Alt text for images
- ✅ Proper heading hierarchy

## 🚀 Performance

- 📦 Single CSS file (9KB)
- 📄 Optimized HTML
- 🎨 CSS variables for consistency
- ⚡ Minimal external dependencies
- 📱 Mobile-first approach

---

**This theme provides a cohesive, professional appearance across all pages while maintaining the warm, inviting feel of a premium coffee brand.**
