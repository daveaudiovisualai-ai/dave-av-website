# DAVE website (dave-av.ai)

Static site, no build step. Hosted on Cloudflare Pages from this repository.

## What's on the page
- **Countdown intro**: a 10-second-style count over a dot world map, shown once per visit (with a Skip button).
- **Globe**: a three.js dot globe with project arcs leaving Dubai. Drag to rotate.
- **Delivery scene**: a scroll-driven GSAP animation. A forklift delivers a crated 47U rack, the crate lifts away, each piece of rack equipment lights up with its label, then the LED wall, a 16:9 screen, two portrait 75" signage screens, a Pufferfish-style touch globe, a white lectern kiosk, two tapered transparent-screen totems and six pendant speakers appear, cabled back to the rack, and the system comes alive. The rack contents are the `KIT` list in the script.
- Pinned projects, integrator offer, technology partners, FAQ and a partner sign-up form.

## Editing projects
All projects live in the `PROJECTS` list near the top of the script in `index.html`. Each entry becomes an arc on the globe and a card in "Pinned projects":

```js
{ city: 'London', country: 'UK', lat: 51.51, lng: -0.13, title: 'Corporate headquarters', sector: 'Corporate', brands: ['Samsung', 'Biamp'], text: 'One-line description.' }
```

Get lat/lng by right-clicking the location in Google Maps. When the real projects are in, remove the yellow "Example content" tag in the Projects section.

## Libraries (free, loaded from cdnjs)
- three.js r128 for the globe
- GSAP 3.12.5 + ScrollTrigger for the scroll animation and counters

## Still to do
- Partner sign-up form: connect to a form service (e.g. Formspree) by setting the form `action` and removing the preview handler.
- Partner logos: brand names are text until each brand approves logo use.

## Hosting on dave-av.ai with Cloudflare Pages (free)
1. In Cloudflare, add the site dave-av.ai, then change the nameservers at GoDaddy to the two Cloudflare gives you.
2. Workers & Pages → Create → Pages → Connect to Git → this repo. Framework preset: None, build command empty, output directory `/`.
3. Under Custom domains, add dave-av.ai and www.dave-av.ai.
