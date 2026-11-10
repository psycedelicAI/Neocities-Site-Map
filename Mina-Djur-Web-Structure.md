# Mina Djur — Website Structure

**Website:** [mina-djur.neocities.org](https://mina-djur.neocities.org/)  
**Repository:** [psycedelicAI/Neocities-Site-Map](https://github.com/psycedelicAI/Neocities-Site-Map/)  
**Document purpose:** Map the Mina Djur website’s folders, files, and responsibilities.

> This is a documentation map of the Mina Djur Neocities website. It is not the website source code itself. Paths marked **VERIFY** need to be checked against the current Neocities file manager before they are treated as a complete live inventory.

---

## 1. Website overview

Mina Djur is a static website built with HTML, CSS, JavaScript, and text-based data and settings files.

The website is organized around these main areas:

- **Root pages** — the homepage, site-wide loader, and root-level resources.
- **`pages/`** — numbered pages, including product categories and information pages.
- **`content/`** — editable page copy, seasonal text, and blog posts.
- **`settings/`** — public configuration files for identity, visibility, colors, campaigns, and other settings.
- **`store/`** — product data and product-image folders.
- **`core/`** — shared JavaScript, blog code, and default color palettes.
- **`design/`** — shared and page-specific stylesheets.

The basic content flow is:

```text
Settings and text files
          ↓
JavaScript reads and applies their values
          ↓
HTML provides the page structure
          ↓
CSS controls the visual presentation
```

Text and configuration files are public when hosted on Neocities. They must not contain passwords, private data, or secret API keys.

---

## 2. Website folder tree

The tree below records the structure and paths known from the current project work. Files and directories marked **VERIFY** must be checked against the live site before this document is considered a definitive file-by-file inventory.

```text
Mina-Djur-Neocities-Site/
│
├── index.html
├── not_found.html                         [VERIFY live file]
├── favicon.ico                            [Root favicon URL has been used]
│
├── pages/
│   ├── 01.html                            # Walks
│   ├── 02.html                            # Rest & Beds
│   ├── 03.html                            # Food & Water
│   ├── 04.html                            # Play & Enrichment
│   ├── 05.html                            # Dog Care
│   ├── 06.html                            # Travel & Accessories
│   ├── 07.html                            # Holiday/theme page
│   ├── 08.html                            # Seasons page
│   ├── 09.html                            # Tips and affiliate content
│   ├── 10.html                            # About page
│   └── information.html                   # Customer and business information
│
├── content/
│   ├── content.txt                        # Page text fields, including homepage fields
│   ├── index-blogg.txt                    # Numbered homepage blog posts
│   ├── yearly.txt                         # Holiday and seasonal text
│   ├── products-about.txt                 [VERIFY exact filename]
│   └── content-about.txt                  [VERIFY; this name has also been used]
│
├── settings/
│   ├── # README-SETTINGS.txt              # Settings-folder guide
│   ├── campaign.txt                       # Campaign rules
│   ├── discount.txt                       # Discount rules
│   ├── identity.txt                       # Brand name, tagline, page and navigation labels
│   ├── information-settings.txt           # Public business and contact information
│   ├── page-colors-custom.txt             # Custom colors for regular pages
│   ├── page-settings.txt                  # Page visibility in navigation
│   ├── product-pages.txt                  # Product-slot visibility by page/theme
│   ├── site-colors-custom.txt             # Custom site/component colors
│   ├── theme.txt                          # Selects the site color theme
│   └── Yearly-Settings.txt                # Seasonal and holiday behavior/settings
│
├── store/
│   ├── Store010.txt                       # Product data for page 01
│   ├── Store020.txt                       # Product data for page 02
│   ├── Store030.txt                       [VERIFY exact file]
│   ├── Store040.txt                       [VERIFY exact file]
│   ├── Store050.txt                       [VERIFY exact file]
│   ├── Store060.txt                       [VERIFY exact file]
│   │
│   ├── 01/                                # Product images for page 01
│   ├── 02/                                # Product images for page 02
│   ├── 03/                                # Product images for page 03
│   ├── 04/                                # Product images for page 04
│   └── 05/                                # Product images for page 05
│        [Other image folders: VERIFY]
│
├── core/
│   ├── site-loader.js                     # Page-aware shared script loader
│   │
│   ├── blog/
│   │   └── index-blogg.js                 # Loads and renders homepage blog posts
│   │
│   ├── palettes/
│   │   ├── page-colors-default.txt        # Default regular-page palette
│   │   └── site-colors-default.txt        # Default site/component palette
│   │
│   └── java/
│       └── store/
│           ├── affiliate-loader.js
│           ├── annual.js
│           ├── cart.js
│           ├── content.js
│           ├── gallery.js
│           ├── identity.js
│           ├── lightbox.js
│           ├── order-email.js
│           ├── palette-master.js
│           ├── product-loader.js
│           ├── product-settings.js
│           ├── product-sku.js
│           ├── seasons.js
│           └── variant-price.js
│
└── design/
    ├── default.css                        # Shared site-wide styles
    └── pages/
        ├── index-products.css             # Homepage styles
        └── 02.css                         # Page 02 styles
             [Other page-specific CSS files: VERIFY]
```

---

## 3. Page map

| Page | Main purpose | Known route |
|---|---|---|
| Homepage | Blog and site introduction | `/index.html` |
| Page 01 | Walks | `/pages/01.html` |
| Page 02 | Rest & Beds | `/pages/02.html` |
| Page 03 | Food & Water | `/pages/03.html` |
| Page 04 | Play & Enrichment | `/pages/04.html` |
| Page 05 | Dog Care | `/pages/05.html` |
| Page 06 | Travel & Accessories | `/pages/06.html` |
| Page 07 | Holiday or current theme | `/pages/07.html` |
| Page 08 | Seasonal content | `/pages/08.html` |
| Page 09 | Tips and affiliate content | `/pages/09.html` |
| Page 10 | About | `/pages/10.html` |
| Information | Business, ordering, delivery, returns, privacy, and contact | `/pages/information.html` |
| Not-found page | Custom page for missing routes | `/not_found.html` — verify live file |

The page’s actual HTML filename, CSS path, and script selection should always be checked against the live version before editing.

---

## 4. Content files

### `content/content.txt`

Contains editable page copy arranged using page and field numbers. The homepage uses page key `00`.

Example structure:

```text
00|0|~Small heading
00|1|~Heading
00|2|~Introduction text
```

The HTML page must identify its content page and mark fields with `data-content-field` for the content script to place the text.

### Homepage blog file

```text
/content/index-blogg.txt
```

Contains numbered blog-post blocks. The homepage blog script reads this file and displays posts with the highest post number first.

The known post structure is:

```text
[1]
title=Post title
datetime=2026-11-10 12:00
body=First paragraph

Second paragraph
```

### Seasonal content

```text
/content/yearly.txt
```

Contains text for page 07’s holiday themes and page 08’s seasons. The page number, active theme/season key, field number, delimiters, and `~` marker are structural and should be preserved.

### Product-information content filename — resolve before relying on it

Two filenames have appeared in project work:

```text
/content/products-about.txt
/content/content-about.txt
```

The active content script and the file actually uploaded must use the same path. Check the current `content.js` and the live files, choose one canonical filename, and remove obsolete requests only after the new path has been tested.

---

## 5. Settings files

| File | Responsibility |
|---|---|
| `settings/identity.txt` | Brand name, tagline, page names, and navigation labels |
| `settings/page-settings.txt` | Whether pages are treated as active in navigation |
| `settings/product-pages.txt` | Which product slots are approved to display on each page or theme |
| `settings/information-settings.txt` | Public business, contact, and information-page settings |
| `settings/theme.txt` | Selects custom/default theme behavior |
| `settings/site-colors-custom.txt` | Custom colors for shared site components |
| `settings/page-colors-custom.txt` | Custom colors for regular pages |
| `settings/campaign.txt` | Supported campaign configuration |
| `settings/discount.txt` | Supported discount configuration |
| `settings/Yearly-Settings.txt` | Seasonal/holiday selection and related settings |
| `settings/# README-SETTINGS.txt` | Human-readable guide to the settings folder |

Exact capitalization, punctuation, and filenames matter because URLs and paths may be case-sensitive.

**Planned, not confirmed as created:** product color/size code files and a central store-interface/currency settings file. Do not list them as existing files until they have been created and uploaded.

---

## 6. Product data and images

Product pages load product information from Store files. Known examples include:

```text
/store/Store010.txt
/store/Store020.txt
```

A product row can include:

- product slot;
- product ID;
- product name;
- description;
- size, weight, and price variants;
- color options;
- image prefix.

Page 02, for example, uses product image prefixes like:

```text
../store/02/01-
```

Product images are grouped in numbered directories under `/store/`. The image filename pattern and prefix must match the product row and gallery’s expected naming convention.

Before moving, renaming, or deleting a product or image file:

1. Check which product/page uses it.
2. Keep a backup.
3. Update all matching product data or code references if the path changes.
4. Test the product card and gallery afterward.

Hiding a product slot in `product-pages.txt` does not itself delete its product data or images.

---

## 7. JavaScript responsibilities

| Script | Known responsibility |
|---|---|
| `core/site-loader.js` | Loads page-appropriate scripts in the intended order |
| `core/blog/index-blogg.js` | Reads and renders homepage blog posts |
| `affiliate-loader.js` | Supports affiliate content |
| `annual.js` | Seasonal/yearly behavior |
| `cart.js` | Shopping-cart behavior and totals |
| `content.js` | Reads page text and product-information text |
| `gallery.js` | Product-image gallery behavior |
| `identity.js` | Reads/applies brand and page identity settings |
| `lightbox.js` | Enlarged product-image view |
| `order-email.js` | Builds the customer’s email-order handoff |
| `palette-master.js` | Loads and applies the selected palette |
| `product-loader.js` | Reads product data and renders product cards |
| `product-settings.js` | Applies product-slot visibility settings |
| `product-sku.js` | Generates product SKU values |
| `seasons.js` | Holiday-theme behavior |
| `variant-price.js` | Variant price behavior |

The script list records known project paths; it does not mean every script is loaded on every page. `site-loader.js` should load only the scripts a page needs and preserve the correct execution order.

---

## 8. Color palettes

Known default palette files:

```text
/core/palettes/page-colors-default.txt
/core/palettes/site-colors-default.txt
```

Custom palette settings are stored under:

```text
/settings/page-colors-custom.txt
/settings/site-colors-custom.txt
```

`palette-master.js` connects the theme setting to the relevant palette files. Verify its current requested paths against the files that actually exist. Do not leave requests to removed or obsolete seasonal/holiday color files.

---

## 9. Planned settings work — not yet part of the live tree

The following are planned changes, not confirmed files:

```text
/settings/product-color-codes.txt
/settings/product-size-codes.txt
/settings/store-settings.txt
```

Possible responsibilities:

- `product-color-codes.txt` — product color names and SKU color codes.
- `product-size-codes.txt` — product size names and SKU size codes.
- `store-settings.txt` — customer-facing product UI labels and selected currency/format.

If created, update the settings guide and this structure document after the files are uploaded.

### Currency behavior

The intended simple model is:

- A product price is entered as a number in the store’s selected currency.
- One setting selects the currency to display, such as `SEK`, `USD`, or `EUR`.
- The website does **not** calculate exchange rates or convert prices.
- When the store changes its selected currency, its owner sets/reviews the product prices in that currency.
- The payment provider handles payment and any conversion it performs.

---

## 10. GitHub repository structure

The website structure document belongs in:

```text
https://github.com/psycedelicAI/Neocities-Site-Map/
```

Recommended repository layout:

```text
Neocities-Site-Map/
├── README.md
└── WEBSITE-STRUCTURE.md
```

The repository contains the site map documentation. It is separate from the files published to the Neocities website unless the owner deliberately copies website files into the repository.

### README link

Add this section or link to the repository’s `README.md`:

```markdown
## Website documentation

- [Mina Djur — Website Structure](WEBSITE-STRUCTURE.md)
```

A relative Markdown link works within GitHub and does not need a hard-coded `main` branch URL.

---

## 11. Add the document through the GitHub website

1. Open [psycedelicAI/Neocities-Site-Map](https://github.com/psycedelicAI/Neocities-Site-Map/).
2. Select **Add file** → **Create new file**.
3. Enter this filename:
   ```text
   WEBSITE-STRUCTURE.md
   ```
4. Paste this document into the editor.
5. Review the preview and confirm the folder tree is readable.
6. Add a commit message, for example:
   ```text
   Add Mina Djur website structure map
   ```
7. Select **Commit changes**.
8. Open `README.md` in the repository and choose **Edit**.
9. Add the README link shown above.
10. Commit the README change, for example:
    ```text
    Link website structure from README
    ```
11. Return to the repository front page and click the new link to verify it opens the document.

---

## 12. Final live-site audit

Before calling this a complete map:

- [ ] Compare every root file against the current Neocities file manager.
- [ ] Open each folder and record every current filename.
- [ ] Verify all numbered pages and the information page.
- [ ] Verify the real names and locations of all content and settings files.
- [ ] Resolve the `products-about.txt` versus `content-about.txt` filename discrepancy.
- [ ] Record all current CSS files and product-image folders.
- [ ] Confirm which Store files actually exist; do not infer missing Store files from numbering.
- [ ] Confirm whether `not_found.html` exists in the root.
- [ ] Remove **VERIFY** notes only after checking the live file.
- [ ] Update this document whenever a folder or file is added, moved, renamed, or removed.

**Last principle:** this map documents the actual Mina Djur site. It should distinguish verified live files from planned files and historical paths.
