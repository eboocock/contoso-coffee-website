# Contoso Coffee — Wiring Contact Form to Power Automate / Dataverse

## What changed
- Replaced placeholder SVGs with real, license-friendly images (Pexels/Pixabay) referenced by URL.
- The Contact form now **POSTs JSON** to a Power Automate **HTTP Request** trigger (set `FLOW_URL` in `contact.html`).

## Set up (Power Automate → Dataverse)
1) Create a **Power Automate cloud flow** with trigger **"When an HTTP request is received"**.
2) Use this sample JSON schema for the trigger:
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
3) Add a **"Add a new row"** Dataverse action targeting a custom table (e.g., `ccf_leads`) or the standard **Lead** table. Map fields:
   - `Topic` → `Contoso Website: {"{firstName} {lastName}"}`
   - `First Name` → `{firstName}`
   - `Last Name` → `{lastName}`
   - `Company` → `{company}`
   - `Email` → `{email}`
   - `Lead Source` → `Website`
   - `Description` → `Interest: {interest}\n\nMessage: {message}\nSubmitted: {submittedUtc}`

4) Save the flow and copy the **HTTP POST URL** from the trigger.
5) Open `contact.html` and replace the value of `FLOW_URL` with your Flow URL.
6) Publish the site.

## Image credits & licenses
- Pexels photos are **free to use** (no attribution required). Pixabay images are **royalty-free** (no attribution required). Check their license pages.
- Hero/espresso machine: https://images.pexels.com/photos/324028/pexels-photo-324028.jpeg?cs=srgb&fm=jpg&w=2000
- Coffee shop counter: https://images.pexels.com/photos/28272182/pexels-photo-28272182.jpeg?cs=srgb&fm=jpg&w=1600
- Coffee beans close-up: https://cdn.pixabay.com/photo/2021/09/07/10/11/coffee-beans-6603499_1280.jpg
- Office meeting with coffee: https://images.pexels.com/photos/6931054/pexels-photo-6931054.jpeg?cs=srgb&fm=jpg&w=1400

## Notes
- If your Flow requires authentication or IP restrictions, host the site on a domain you trust and enable CORS on the trigger as needed.
- To store to Dataverse without Power Automate, you can front the Dataverse Web API with an authenticated API (Azure Functions) and call that from the form.
