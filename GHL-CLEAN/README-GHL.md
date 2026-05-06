# GHL Schema Implementation Guide

## Where to Paste Schema in GHL

### Step 1: Go to Your Page
1. Open your GHL dashboard
2. Go to **Sites → Pages**
3. Click the page you want to add schema to (e.g., FAQ page)
4. Click **Edit**

### Step 2: Access Custom Code
1. In the page editor, click **Settings** (gear icon)
2. Click **Custom Code**
3. You'll see 3 sections:
   - **Header Code** ← Paste schema here
   - **Footer Code**
   - **Custom CSS**

### Step 3: Paste the Schema
1. Copy the FULL code from the schema files (including `<script>` tags)
2. Paste into **Header Code** section
3. Click **Save**
4. Click **Update** on the page

---

## Which Schema Goes Where

| Page | Schema File | Paste Location |
|------|-------------|----------------|
| FAQ Page | quanivo-faq-schema.json | Header Code |
| Homepage | quanivo-organization-schema.json | Header Code |
| Product Pages | quanivo-product-*.json | Header Code |
| All Pages | quanivo-breadcrumb-schema.json | Header Code |
| Contact Page | quanivo-localbusiness-schema.json | Header Code |

---

## Important Notes

### ✅ DO:
- Paste the **FULL** code including `<script type="application/ld+json">` wrapper
- Save and Update after pasting
- Test with Google's Rich Results Test after publishing

### ❌ DON'T:
- Paste just the JSON (needs HTML wrapper)
- Put schema in Footer Code (Header is better for SEO)
- Forget to click Update after saving

---

## Testing Your Schema

1. Publish your page
2. Go to: https://search.google.com/test/rich-results
3. Enter your live page URL
4. Click **Test URL**
5. Check for errors

---

## Files in This Folder

All schema files are in the `GHL-CLEAN/` folder:
- Clean JSON format
- Ready to copy-paste
- Includes both Quanivo and QEB schemas

**Download from:** https://workspace-quanivo.vercel.app
