# NOTES

## 1. What I changed
**Bugs**
- Prices now come from `PRODUCTS`, not the page text. Before, ₹1,299 became ₹1 in the cart.
- Max 5 per tea and never more than stock. Sold-out teas can't be added and always sort last.
- Coupon WELCOME10 follows the rules: 10%, max ₹150, minimum ₹399, no gift boxes, any letter case, applying it twice changes nothing.
- Shipping is ₹49, free when the amount after discount reaches ₹599. Only the final total is rounded. Amounts use ₹ and Indian commas.
- Search, filter and sort now work together. Slow old search answers are ignored.
- Delivery check shows days, "not serviceable" or an error, and never sticks on "Checking…".
- Also fixed: crash on first visit, wrong cart count, "remove" deleting more than one item, broken plus/minus, Green filter, quick view opening the wrong tea, checkout not submitting the real form.

**Design and UX**
- Followed BRAND.md: colours, fonts, spacing, button states, section order.
- Add-to-cart button is always visible, a small message appears when you add, cart has a free-shipping bar.
- Removed the popup, marquee, countdown, and the "Shark Tank" and "10,000+" claims.

**Technical**
- Removed jQuery, animate.css and Font Awesome. Added title, description, Open Graph, and JSON-LD (store, products, FAQ).
- Added alt text, a skip link and keyboard support.

## 2. What the AI got wrong
- My first version stretched the product images because of `width`/`height` attributes on the `<img>` tags. I noticed it on my screen and the AI fixed it with `height:auto`.
- Gemini gave me very large images and I used them straight on Vercel. The page downloaded about 30 MB and took 2.4 minutes on Slow 4G. I found it in the Chrome Network tab.

## 3. Images
- Made with Gemini: 8 product images and the hero.
- Logo is a simple SVG (leaf and the word Mistvale).
- Before: total about 30 MB. Hero was 6.5 MB, product images were 0.6 MB to 6.3 MB each.
- Fix: resized product images then saved as WebP with Squoosh.

## 4. How I tested it
- Chrome, phone width 360px, keyboard only.
- Checked image size and load time in the Chrome Network tab on Slow 4G, before and after compressing.

## 5. Time spent
- Generation of image took some time and almost 3 hours to understand and implement. 

## 6. Extra features
- Wishlist (saved in the browser), quick view, skip link.

## 7. With more time I would...
- Add a phone menu (links are hidden on small screens), size options, shareable filter links, and recently viewed.