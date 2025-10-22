# 🚀 Contoso Coffee Website - Deployment Package v6e

## 📦 Package Contents

This package contains the updated Contoso Coffee website with the demo button removed from the contact form.

### ✅ Files Included

**Website Pages (4 files):**
1. `index.html` - Homepage with hero and features
2. `products.html` - Product catalog with accordion (60+ products)
3. `customers.html` - Customer success stories and testimonials
4. `contact.html` - Contact form (**UPDATED** - demo button removed)

**Assets (3 files):**
5. `assets/enriched_products.json` - Product data (84 KB)
6. `assets/img/logo.svg` - Contoso Coffee logo
7. `assets/img/favicon.svg` - Site favicon

**Documentation (3 files):**
8. `README.md` - Original brief documentation
9. `README-UPDATED.md` - Comprehensive documentation (recommended)
10. `CHANGES-v6e.md` - Detailed change log

**Total:** 10 files

---

## 🎯 What's New in v6e

**Single Change:** Removed the "Demo Lead" button from `contact.html`

**Impact:**
- ❌ Demo button removed (was prefilling: Abbi Atkins, Dutch Brothers, etc.)
- ❌ `fillDemo()` function removed from JavaScript
- ✅ All other functionality preserved
- ✅ Power Automate integration intact
- ✅ Form validation working
- ✅ Design and styling unchanged

---

## 🚀 Quick Deploy to GitHub Pages

### Prerequisites
- GitHub account
- Repository: `contoso-coffee-website`
- Git installed locally (or use GitHub web interface)

### Method 1: Command Line (Fastest)

```bash
# 1. Navigate to your local repository
cd /path/to/contoso-coffee-website

# 2. (Optional) Create backup branch
git checkout -b backup-v6d
git checkout main

# 3. Copy all files from this package
cp /path/to/package/*.html .
cp -r /path/to/package/assets ./

# 4. Verify changes
git status
git diff contact.html

# 5. Commit
git add .
git commit -m "Update to v6e: Remove demo button from contact form"

# 6. Push
git push origin main

# 7. Verify deployment (wait 1-2 minutes)
# Visit: https://eboocock.github.io/contoso-coffee-website/contact.html
```

### Method 2: GitHub Web Interface (Easiest)

**For contact.html only:**
1. Go to: https://github.com/eboocock/contoso-coffee-website
2. Click on `contact.html`
3. Click the pencil icon (Edit this file)
4. Select all content (Ctrl+A / Cmd+A)
5. Delete
6. Open the new `contact.html` from this package
7. Copy all content
8. Paste into GitHub editor
9. Scroll down, add commit message: "Remove demo button (v6e)"
10. Click "Commit changes"
11. Wait 1-2 minutes
12. Visit: https://eboocock.github.io/contoso-coffee-website/contact.html

**For all files:**
1. Go to: https://github.com/eboocock/contoso-coffee-website
2. Click "Upload files"
3. Drag and drop all HTML files from this package
4. Drag and drop the `assets` folder
5. Commit message: "Update to v6e: Remove demo button"
6. Click "Commit changes"
7. Wait 1-2 minutes for deployment

---

## 🔍 Pre-Deployment Checklist

Before deploying, ensure:

- [ ] You have all 10 files from this package
- [ ] The `assets` folder structure is intact (img subfolder)
- [ ] You've backed up the current v6d version (optional but recommended)
- [ ] You have push access to the GitHub repository
- [ ] GitHub Pages is enabled on the repository

---

## ✅ Post-Deployment Verification

After deploying, verify these items:

### 1. Homepage Check
- [ ] Visit: https://eboocock.github.io/contoso-coffee-website/
- [ ] Hero image loads
- [ ] Three feature cards display
- [ ] Navigation works

### 2. Products Page Check
- [ ] Visit: https://eboocock.github.io/contoso-coffee-website/products.html
- [ ] Accordion categories expand/collapse
- [ ] Product images load
- [ ] "Expand all" / "Collapse all" buttons work

### 3. Customers Page Check
- [ ] Visit: https://eboocock.github.io/contoso-coffee-website/customers.html
- [ ] Case studies display
- [ ] Testimonials show

### 4. Contact Page Check (Most Important)
- [ ] Visit: https://eboocock.github.io/contoso-coffee-website/contact.html
- [ ] **Verify: Only ONE button visible ("Send")**
- [ ] **Verify: NO "Demo Lead" button present**
- [ ] Form fields are empty by default
- [ ] All fields are functional
- [ ] Validation works (try submitting empty form)
- [ ] Form submits (check console for success/error)

### 5. Visual Check
- [ ] Logo displays in header
- [ ] Favicon shows in browser tab
- [ ] Dark theme colors correct
- [ ] Navigation highlights active page
- [ ] Footer displays

### 6. Mobile Check
- [ ] Open site on mobile device or use browser dev tools
- [ ] Layout adjusts properly
- [ ] Form is usable on small screens
- [ ] Navigation accessible

---

## ⚙️ Power Automate Configuration

**Current Status:** The contact form has a Power Automate URL configured.

**To verify/update:**
1. Open `contact.html` in a text editor
2. Find line 158: `const FLOW_URL = "..."`
3. Verify the URL is correct
4. If needed, update with your Power Automate HTTP trigger URL

**Testing the integration:**
1. Fill out the contact form on the live site
2. Submit
3. Check your Power Automate flow run history
4. Verify data appears in Dataverse Leads table

**If Flow URL is not configured:**
- Form will download submission as JSON file (fallback behavior)
- This is expected and allows testing without Power Automate

---

## 🔧 Troubleshooting

### Issue: Contact page still shows demo button

**Solution:**
- Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
- Wait a few more minutes for GitHub Pages to rebuild
- Check that the correct file was uploaded
- Verify Git push succeeded: `git log -1`

### Issue: 404 error on assets

**Solution:**
- Verify `assets` folder structure is correct
- Ensure `assets/img/` subfolder exists
- Re-upload the entire assets folder
- Check file paths in HTML (should be `assets/img/logo.svg`)

### Issue: Products not loading

**Solution:**
- Ensure `assets/enriched_products.json` was uploaded
- Check browser console for errors
- Verify file is in the correct location: `assets/enriched_products.json`

### Issue: Form doesn't submit

**Solution:**
- Check browser console for JavaScript errors
- Verify `FLOW_URL` is set correctly in `contact.html`
- Test with browser's developer tools Network tab
- If Power Automate fails, form should download JSON (fallback)

---

## 📋 File Integrity Verification

**File sizes (approximate):**
```
index.html:                  7.5 KB
products.html:             146.0 KB
customers.html:             12.0 KB
contact.html:                9.5 KB
assets/enriched_products.json: 84.0 KB
assets/img/logo.svg:         540 bytes
assets/img/favicon.svg:      540 bytes
```

**Line counts:**
```
contact.html:  194 lines (was 210 in v6d)
index.html:    113 lines
products.html: 1993 lines
customers.html: 226 lines
```

---

## 🔄 Rollback Plan

If you need to revert to v6d:

### Quick Rollback
```bash
git log --oneline  # Find the commit hash before v6e
git revert <commit-hash>
git push origin main
```

### Full Rollback
```bash
git checkout backup-v6d  # If you created backup branch
git checkout contact.html
git commit -m "Rollback to v6d"
git push origin main
```

---

## 📞 Support Resources

**Documentation:**
- `README-UPDATED.md` - Full documentation
- `CHANGES-v6e.md` - Detailed change log
- Original `README.md` - Quick reference

**Online Resources:**
- GitHub Repository: https://github.com/eboocock/contoso-coffee-website
- Live Site: https://eboocock.github.io/contoso-coffee-website/
- GitHub Pages Docs: https://docs.github.com/en/pages

**Testing:**
- Test locally: `python -m http.server 8000`
- Browser Dev Tools: F12 or Cmd+Option+I
- Check console for JavaScript errors
- Use Network tab to debug loading issues

---

## ✨ Summary

**What you're deploying:**
- Updated Contoso Coffee website (v6e)
- Demo button removed from contact form
- All functionality preserved
- Professional, clean interface

**Deployment time:**
- Upload: 2-5 minutes
- GitHub Pages rebuild: 1-2 minutes
- **Total: ~5 minutes**

**Risk level:** Low
- Single file changed (contact.html)
- Non-breaking change
- Easy rollback if needed

---

## 🎉 Ready to Deploy!

You have everything you need. Choose your deployment method above and follow the steps.

**Recommended order:**
1. Read `CHANGES-v6e.md` to understand what changed
2. Review `README-UPDATED.md` for full documentation
3. Choose deployment method (command line or web interface)
4. Deploy
5. Verify using post-deployment checklist
6. Test contact form submission

**Good luck with your deployment!** 🚀

---

**Package Version:** v6e  
**Date:** October 22, 2025  
**Status:** Ready for production  
**Change:** Demo button removed from contact form
