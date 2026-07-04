# ГОЛОС Landing

Static landing page for the `ГОЛОС` speaking course.

## Launch Handoff

### Payment Links

The page works without a payment provider: buy buttons fall back to `mailto:` requests.

To enable direct payment buttons:

1. Create real payment links in WayForPay or LiqPay for Basic, Pro, and VIP.
2. Copy `payment-links.example.json` to `payment-links.json`.
3. Replace each placeholder with a real `https://` checkout URL:

```json
{
  "basic": "https://...",
  "pro": "https://...",
  "vip": "https://..."
}
```

Only valid `https://` links are applied. If the file is missing or malformed, the manual email flow stays active.

### Author Photo

To replace the theater-mask fallback, add this file next to `index.html`:

```text
author-photo.jpg
```

Recommended image: vertical portrait, 3:4 ratio, at least 900x1200 px, compressed JPG.

## Files

- `index.html` - landing page.
- `payment-links.example.json` - safe payment-link template.
- `CONTENT_SCRIPTS.md` - TikTok/content ideas for course promotion.

## Safe Checks

```bash
python3 -m json.tool payment-links.example.json >/dev/null
```
