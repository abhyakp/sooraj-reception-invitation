# Sooraj & Sivakami — Wedding Reception Invitation

A western, pastel digital invitation (blush, white and sage, with roses and greenery) for the **wedding reception** on **Sunday, 31 January 2027, 6:00 PM – 9:00 PM** at Rajiv Gandhi Town Hall, Chalakudy.
Built with plain **HTML5, CSS3 and vanilla JavaScript**: no frameworks, no build step, no dependencies besides Google Fonts.

```
reception-invitation/
├── index.html            # the invitation (SEO + Open Graph + Event JSON-LD)
├── css/style.css         # mobile-first pastel styles and animations
├── js/script.js          # reception countdown, back-to-top, scroll reveal
├── assets/
│   ├── images/           # couple photo (webp/jpg), og-image.jpg (1200×630 share image)
│   └── icons/            # favicon.svg, favicon-32, apple-touch-icon, 192/512 icons
├── 404.html  robots.txt  sitemap.xml  site.webmanifest  .nojekyll
└── README.md
```

## Page sections

1. Opening — names, "request the pleasure of your company at their wedding reception", date/time, couple photo in a floral arch
2. Save the date — January · Sunday | 31 | 6:00 PM · 2027
3. Reception details — date, time, venue, Get Directions (Google Maps)
4. Closing — message, names, countdown to 6:00 PM IST

## Event details

| | |
|---|---|
| Couple | Sooraj & Sivakami |
| Hosts | Mrs. Rajeswari S. & Mr. Sureshkumar C. K. |
| Date | Sunday, 31 January 2027 (1202 Makaram 17) |
| Reception | 6:00 PM – 9:00 PM, Rajiv Gandhi Town Hall, Chalakudy, Thrissur |

## Run locally

```bash
python -m http.server 8080      # then open http://localhost:8080
# or
npx serve .
```

## Live address (set before sharing)

The site assumes GitHub Pages at **<https://abhyakp.github.io/sooraj-reception-invitation/>**.
If the repo name or domain is different, replace that address in:

- `index.html` (canonical, `og:url`, `og:image`, `twitter:image`, JSON-LD `image`)
- `robots.txt`, `sitemap.xml`
- `404.html` (the `/sooraj-reception-invitation/` paths)

## Deploy on GitHub Pages

```bash
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

Then Settings → Pages → Deploy from branch → `main` / root. Serve over HTTPS.

After deploying, paste the link into a WhatsApp chat with yourself to check the preview. WhatsApp caches previews, so finalise the address before sending widely. You can also use the [Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/).

## Countdown and timezone

`js/script.js` sets the reception in India Standard Time (fixed UTC+05:30), so the visitor's own timezone has no effect.
Before 6:00 PM IST it counts down; from 6 to 9 PM it shows an "underway" message; after 9 PM a thank-you message. Numbers never go negative.

## Privacy / search engines

The page is indexable by default. To keep it out of Google while still sharing by link, add `<meta name="robots" content="noindex">` to the `<head>` of `index.html` and leave `robots.txt` as **Allow** so crawlers can see the tag. WhatsApp and Facebook previews still work.

## Customising

- **Colours and fonts**: CSS variables at the top of `css/style.css` (blush, rose, mauve, sage). Fonts: Pinyon Script, Cormorant Garamond, Montserrat.
- **Flowers**: all florals are inline SVG symbols in the sprite at the top of `index.html` (`f-rose`, `f-rose-peach`, `f-blossom`, `f-bud`, `f-leaf`, `f-euca`, composed into `f-spray` and `f-divider`). No image downloads.
- **Text**: plain HTML in `index.html`; countdown messages in `js/script.js`.
- **Couple photo**: shown in the arch. Replace `assets/images/couple-720.webp` (720×900), `couple-1200.webp` and `couple-1200.jpg` (1200×1500) at the same names, keeping a 4:5 crop.
- **Share image / icons**: `assets/images/og-image.jpg` (1200×630) and `assets/icons/*` use the same photo and rose artwork; replace at the same names.
- After changing CSS/JS, bump the `?v=` number on their links in `index.html` so browsers fetch the new files.

## Launch checklist

- [ ] Confirm the live address (see above)
- [ ] Decide index vs. `noindex`
- [ ] Open on a phone and test Get Directions
- [ ] Check the WhatsApp/Facebook link preview
- [ ] Optional: submit `sitemap.xml` in Google Search Console and Bing Webmaster Tools; add analytics if wanted (no IDs are included)
