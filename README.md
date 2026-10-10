# Dave website

A single-page static site. Open `index.html` in a browser, or upload the folder to any static host (Netlify, Vercel, GitHub Pages, cPanel).

## Swap in your own hero video
The hero currently plays your YouTube Short. To change it, edit `var YT_ID = '...'` in the script near the bottom of index.html (the part after `/shorts/` or `?v=` in the YouTube link). Set it to `''` to use a local file instead:

1. Export a short loop (10–30 s, no sound needed, 1920×1080, under ~8 MB).
2. Save it as `assets/hero.mp4` (optional extra: `assets/hero.webm`).
3. Save a still frame as `assets/hero-poster.jpg`.
The animated LED-wall background only appears when no video file loads, so nothing else needs changing.

## Things to edit in index.html
- Logo: the `DAVE` wordmark in the header (replace with an `<img>` of your logo).
- Email and studio address in the Contact section (`hello@dave-av.ai` is a guess at the address; change it if needed).
- Projects: the three cards marked "Example project" are placeholders. Replace text, figures and swap each `<canvas>` for an `<img src="assets/your-photo.jpg">`.
- Figures marked "example" in the intro and the "Time saved per stage" meters are illustrative.
- Enquiry form: connect to a form service (e.g. Formspree) by setting the form's `action` and removing the preview handler in the script.

## Hosting on dave-av.ai with Cloudflare Pages (free)
1. In Cloudflare, add the site dave-av.ai, then change the nameservers at GoDaddy to the two Cloudflare gives you. The domain stays registered with GoDaddy.
2. Go to Workers & Pages, then Create, then Pages, then "Upload assets". Drag in this folder (index.html and assets/).
3. Under the project's Custom domains, add dave-av.ai and www.dave-av.ai.
Keep the hero video under 25 MB, which is Cloudflare Pages' limit for a single file. A 20-second 1080p loop at a sensible bitrate is usually 5 to 10 MB.
