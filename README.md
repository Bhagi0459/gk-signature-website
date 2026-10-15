# GK Signature – Website

Static one-page website for **GK Signature**, an event décor & styling business in Hyderabad.

- Live: https://gksignature.vercel.app
- Instagram: https://www.instagram.com/gksignatureevents/

## Stack
Plain HTML + CSS + vanilla JS, no build step. Hosted on Vercel; every push to `main` deploys automatically.

## Structure
```
index.html          # the whole site (styles + scripts inline)
images/             # photos, logo, favicons, og-image
robots.txt          # allows indexing, points to sitemap
sitemap.xml         # for Google Search Console
site.webmanifest    # app icons / theme colour
vercel.json         # clean URLs + image caching
```

## Updating
Edit `index.html` (or replace images), commit, and push to `main`. Update `<lastmod>` in `sitemap.xml` for big content changes.

## Image credits / placeholders
Service-card images for Birthdays, Cradle & Naming, Corporate, Private Events and Flower Décor are free-licence placeholders from [Unsplash](https://unsplash.com/license). Replace them with GK Signature's own event photos (same filenames) when available:

| File | Unsplash photo |
|---|---|
| images/birthday-decor.jpg | photo-1741969494307-55394e3e4071 |
| images/cradle-naming-decor.jpg | photo-1644785421448-e1b038f2381e |
| images/corporate-event-decor.jpg | photo-1768508947591-b650dacc70a4 |
| images/pooja-private-decor.jpg | photo-1756395959307-d546b7947e3d |
| images/marigold-garlands.jpg | photo-1789971649652-ae5dfeeaa7b4 |

All other photos are GK Signature's own work.

## Customer reviews
- Customers review via the Google Form at **https://gksignature.vercel.app/review** (redirect in `vercel.json`). Customers cannot see other responses.
- Responses land in the **private** Google Sheet "Review GK Signature (Responses)" (only people it is shared with can open it).
- To publish a review: tick its **Approved** checkbox in the sheet. It appears on the website automatically (no code change, no deploy).
- The website reads a Google Apps Script web app ("GK Signature Review Approvals") that returns **only** rows that are ticked Approved **and** where the customer chose "Yes, you can publish it": first name, event, area, rating and text. Phone numbers are never returned.
- Untick Approved to remove a review from the site. Never add made-up reviews.
