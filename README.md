# README — Sales page for *El Recetario de la Puerta de Atrás*

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The sales page. All design and code are inside this one file. |
| `images/` | Every photo, taken from the book and converted to WebP. |
| `terminos.html`, `privacidad.html`, `reembolsos.html` | Terms, Privacy and Refunds pages, in Spanish. **Review them before you publish** — they are a template, not written by a lawyer. |

## 1. Edit the settings (CONFIG)

Open `index.html` in a text editor (Notepad, VS Code). Search for `const CONFIG` near the bottom. Change only the values in quotes:

| Setting | What to put |
|---|---|
| `checkoutUrl` | Your checkout link, e.g. `"https://yourname.gumroad.com/l/recetario"`. **While it's empty, the buy buttons just scroll down to the buy section.** |
| `price` | Today's price: `"$27"` |
| `regularPrice` | The full price: `"$55"` |
| `launchEndDate` | The last day of the launch price, written like `"2026-11-30"`. Once set, the red top bar appears with the date. **After that date the page switches itself to $55**, so raise the price in Gumroad on the same day. |
| `refundDays` | Guarantee length (30). |
| `supportEmail` | Your support email. |
| `youtubeUrl` | Your channel link. |
| `exitPopup` | `true` shows the "Antes de irte" (before you go) popup: on computers when the mouse leaves through the top, on phones after 45 seconds or 60% of the page. Never in the first 10 seconds, never after a buy click, once every 7 days per visitor. Set `false` to turn it off. |
| `metaPixelId`, `ga4Id` | Leave empty if you don't track. Put an ID in and that tracker loads, with a cookie notice. |
| `reviews` | The 3 review cards. Change `text`, `name`, `place`, and set `placeholder: false`. **While it says `true`, the card shows a red “Ejemplo · reemplazar” (example, replace) tag.** Use real reviews only, copied exactly as the person wrote them. No reviews yet? Delete the whole `id="resenas"` section. |

Save the file and upload it again.

Buy links keep any `utm_` tags from the page address (e.g. `?utm_source=youtube`), so Gumroad shows where each sale came from.

## 2. Popups

There is one popup, "Antes de irte", with the price and a buy button (see `exitPopup` above). It has no countdown timer on purpose: the offer is real, so it doesn't need one.

The "read the first chapter free" email popup is still **off**. When you have an email service (MailerLite or Kit, both free to start), ask me and I'll add it.

## Unit prices and the dish picker

- The "12¢ por entrada · 11¢ por página · $1.69 por receta" numbers are worked out from `price`, so they update by themselves when the price changes.
- The "Elige lo tuyo" picker reads its list from `const PICKER` right under CONFIG. Each line is `[entry number, title, page]`; a 4th value `1` marks a full recipe with photo.

## 3. Publish for free

**Netlify (easiest):**
1. Go to <https://app.netlify.com/drop>.
2. Drag **the whole folder** (with `index.html` and `images` inside) onto the page.
3. In about a minute you get an address like `random-name.netlify.app`. It's live.
4. To update, edit the file and drag the folder again under *Deploys*.

**Vercel:** new project → upload the folder.

**GitHub Pages:** push the files to a repository → *Settings → Pages* → choose the `main` branch.

## 4. Use your own domain

1. Buy the domain (Namecheap, Porkbun, Cloudflare, etc.).
2. In Netlify: *Domain management → Add a domain*, type your domain.
3. Netlify shows DNS records (an `A` or `CNAME`). Copy them into the DNS settings where you bought the domain.
4. Wait a few hours. Netlify adds HTTPS (the padlock) by itself.

## 5. Before you go live

- [ ] `checkoutUrl` set, and you tested one purchase.
- [ ] `launchEndDate` set (showing $55 crossed out needs a real date when the price goes up).
- [ ] Real reviews in place of the examples, or the section deleted.
- [ ] Legal pages reviewed.
- [ ] In Gumroad: the product delivers the book **and** the Tarjetas de Cocina PDF, and the refund policy says 30 days.
