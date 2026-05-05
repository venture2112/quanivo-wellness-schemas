# WordPress Schema Implementation Guide

## Option 1: Schema Plugin (Recommended)

### Install "Schema Pro" or "Rank Math SEO"
1. Go to WordPress Admin → Plugins → Add New
2. Search for "Schema Pro" (paid) or "Rank Math SEO" (free)
3. Install and activate
4. Import the JSON-LD from the schema files

### Schema Pro Setup:
- Go to Schema Pro → Add New
- Select schema type (FAQ, Product, Organization, etc.)
- Copy JSON content from our files
- Paste into custom schema field
- Assign to specific pages

### Rank Math SEO Setup:
- Edit page/post
- Click Rank Math icon → Schema
- Select schema type
- Import JSON or fill fields manually

---

## Option 2: Manual JSON-LD (No Plugin)

### Add to Header/Footer:
1. Go to Appearance → Theme Editor
2. Edit `header.php` or use "Insert Headers and Footers" plugin
3. Paste the `<script type="application/ld+json">` code
4. Wrap in conditional tags for specific pages:

```php
<?php if (is_page('faq')) { ?>
<!-- Paste qeb-faq-schema.json content here -->
<?php } ?>
```

---

## Option 3: Functions.php Method

Add to `functions.php`:

```php
// Add FAQ Schema to FAQ page
function add_qeb_faq_schema() {
    if (is_page('faq')) {
        ?>
        <script type="application/ld+json">
        {
          "@context": "https://schema.org",
          "@type": "FAQPage",
          ... (paste from qeb-faq-schema.json)
        }
        </script>
        <?php
    }
}
add_action('wp_head', 'add_qeb_faq_schema');
```

---

## Option 4: Custom Plugin

Create file `wp-content/plugins/qeb-schema/qeb-schema.php`:

```php
<?php
/**
 * Plugin Name: Quantum Energy Beds Schema
 * Description: AEO Schema markup for QEB
 */

function qeb_schema_markup() {
    // Product schema on product page
    if (is_page('quantum-bed-info')) {
        echo '<script type="application/ld+json">';
        // Paste qeb-product-bed-schema.json content
        echo '</script>';
    }
    
    // FAQ schema on FAQ page  
    if (is_page('faq')) {
        echo '<script type="application/ld+json">';
        // Paste qeb-faq-schema.json content
        echo '</script>';
    }
    
    // Organization schema on all pages
    echo '<script type="application/ld+json">';
    // Paste qeb-organization-schema.json content
    echo '</script>';
}
add_action('wp_head', 'qeb_schema_markup');
```

---

## Recommended Plugins for WordPress AEO

| Plugin | Purpose | Cost |
|--------|---------|------|
| **Schema Pro** | Full schema control | $79/year |
| **Rank Math SEO** | SEO + Schema | Free/Paid |
| **Yoast SEO** | SEO + Basic Schema | Free/Paid |
| **All in One SEO** | SEO + Schema | Free/Paid |
| **Insert Headers and Footers** | Add code easily | Free |

---

## Testing Your Schema

1. **Google Rich Results Test:**
   https://search.google.com/test/rich-results

2. **Schema.org Validator:**
   https://validator.schema.org/

3. **Google Search Console:**
   Check "Enhancements" section after implementation

---

## Quick Implementation Checklist

- [ ] Install schema plugin OR add code to functions.php
- [ ] Add Organization schema (all pages)
- [ ] Add Product schema (product pages)
- [ ] Add FAQ schema (FAQ page)
- [ ] Add Article schema (blog posts)
- [ ] Add Breadcrumb schema (all pages)
- [ ] Test with Google Rich Results tool
- [ ] Submit sitemap to Google Search Console

---

## WordPress-Specific Tips

1. **Page Slugs:** Match schema to correct page slug (e.g., `faq`, `quantum-bed-info`)

2. **Featured Images:** Ensure products have featured images for Product schema

3. **Categories:** Use Article schema with proper categories for blog posts

4. **Author:** Set up author profiles for Article schema

5. **Yoast Conflict:** If using Yoast, disable its default schema to avoid conflicts

---

## Need Help?

All schema files available at:
https://workspace-quanivo.vercel.app
