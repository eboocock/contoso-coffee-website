# Contoso Coffee Website (v6)

This site is ready to host as static HTML. Styling is embedded on every page for consistency.

## Contact → Power Automate → Dataverse
1. Create a cloud flow with trigger **When an HTTP request is received**.
2. Use this JSON schema:
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
3. Add Dataverse action **Add a new row** → table **Lead** (or your custom table), map fields:
   - Topic → Contoso Website: {firstName} {lastName}
   - First Name, Last Name, Company, Email
   - Lead Source → Website
   - Description → Interest: {interest}\n\nMessage: {message}\nSubmitted: {submittedUtc}
4. Copy the **HTTP POST URL** from the trigger.
5. Open `contact.html` and set `FLOW_URL` to your URL. Save & deploy.

## Images
- Home & customers pages use unique Pexels images (free to use).
- Product images are unique per product using `https://picsum.photos/seed/<SKU>/1200/675` for deterministic placeholders.
- To replace with brand images, set the `Image` column in your CSV or swap the `Image` in `assets/enriched_products.json` and re-deploy.

## Hosting
- GitHub Pages, Azure Static Web Apps, or any static host works.
