# Link preview card

Source for `img/og.jpg`, the 1200x630 image WhatsApp, Facebook, Telegram and
iMessage show when the site is shared. Logo, photos and the brand fonts
(Cormorant Garamond, Jost) were extracted from the site export, so the card
matches the site exactly.

## Regenerate after editing card.html

```bash
python3 -m http.server 8779 &
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --hide-scrollbars --force-device-scale-factor=2 \
  --window-size=1200,630 --screenshot=card@2x.png http://localhost:8779/card.html
python3 -c "from PIL import Image; Image.open('card@2x.png').convert('RGB').resize((1200,630), Image.LANCZOS).save('../img/og.jpg', quality=92, optimize=True, subsampling=1)"
```

It renders at 2x and downsamples so the text stays crisp. Keep the result under
300 KB or WhatsApp falls back to a small thumbnail instead of the large preview.

WhatsApp caches previews per URL. To force a refresh after changing the image,
publish it under a new filename and update the `og:image` tags in `index.html`
and `v2/index.html`.
