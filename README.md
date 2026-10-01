# drbarbaratilmann.de

Static website for the Schule der Entfaltung — Dr. med. Barbara Tilmann.
Plain HTML and one stylesheet, no build step, no framework, no database.
Sister site to `tilmann-chiron.com`: same construction, warmer palette.

## How it's put together

| Path | What it is |
|---|---|
| `<lange-slugs>/index.html` | The pages themselves, each at its original WordPress URL |
| `index.html` | The homepage |
| `assets/style.css` | The only stylesheet. Colours are CSS variables at the top |
| `bilder/` | Photos, resized and compressed |
| `studium.html`, `kkt.html`, … | Short-name redirects into the long folders |
| `sitemap.xml`, `robots.txt`, `.nojekyll` | Search engines, and "serve files as-is" |

## URLs — do not rename these folders

Every page lives at the **exact address it had on the old WordPress site**,
trailing slash and all, because those addresses are what Google has indexed.
The long folder names are the URLs, not clutter.

`praesenzstudium-fuer-integrale-wegbegleitung-ausbildung-in-naturcoaching/index.html`
is served at
`/praesenzstudium-fuer-integrale-wegbegleitung-ausbildung-in-naturcoaching/`.

All 18 old addresses were tested and return the page directly, with no redirect,
because WordPress used trailing slashes and so does this site.

Three old addresses that held versions of the same content now redirect to the
page that kept the ranking: `/studium-fuer-integrale-wegbegleitung/`,
`/schule-der-entfaltung/` and
`/schule-der-entfaltung-bewusstseinswerdung-kurse-seminare-coaching/`.
`/blog/` redirects to the homepage.

**Which "Schule der Entfaltung" page is canonical was a judgment call.** Three
old URLs held versions of it. The richest one, and the one `tilmann-chiron.com`
links to, is now the real page; the other two redirect to it. If Search Console
later shows a different one had the traffic, say so and the canonical can be
swapped.

The short names (`studium.html`, `medizinrad.html`, …) are **redirects only**.

## Decisions worth knowing about

**Seminar dates were all expired.** Every course on the old site advertised
dates in 2023 and 2024 — one even said "dieser Termin entfällt". Publishing
those in 2026 would make the school look abandoned. Each course page now shows
a "Termine und Anmeldung" box reading *Auf Anfrage*, and the full original
schedule, venue and prices sit directly underneath as an HTML comment. Nothing
was thrown away: open the file, and the old details are right there to restore
or replace.

**One image was removed.** `Mandala.jpg` on the Medizinrad page was a
**watermarked Adobe Stock image** — the watermark and the stock ID were visible
in it. It appears the previous agency used an unlicensed file. It is not in this
repository. Her own photo of the stone circle is used instead. Worth checking
whether a licence was ever bought.

**The .de domain has no mailbox.** Both `mail@drbarbaratilmann.de` and
`praxis@drbarbaratilmann.de` appeared on the old site; both are replaced
throughout by `drbarbara@tilmann-chiron.com`.

**Address corrected.** The old site still gave "Vorm Holz 1" in several places.
Everything now says Ludwigstraße 48, matching the practice site. The old venue
addresses survive only inside the archived comments.

**No blog.** The old site had a blog page, but it contained only an
introductory sentence — the RSS feed turned out to mirror the main pages rather
than hold posts. `/blog` redirects to the homepage.

**Soft hyphens stripped.** The WordPress theme had injected invisible
`&shy;` characters into every word. They are gone, so the text is now
searchable and copy-pasteable.

## Before this goes live

1. **Contact form — done.** The form posts to Formspark form `Hlu0y0VAH`,
   the same form the practice site uses. Submissions from here carry the
   subject "Anfrage über drbarbaratilmann.de", so the two sites stay
   distinguishable without needing a second form.
2. **Impressum.** The entries marked `<!-- BITTE PRÜFEN -->` are best guesses.
   Note that seminars are not medical treatment, so the VAT position may differ
   from the practice — worth one question to her Steuerberater.
3. **Custom domain.** Settings → Pages → Custom domain → `drbarbaratilmann.de`,
   then tick "Enforce HTTPS", once DNS points at GitHub.

## Privacy, deliberately

No third-party requests: no web fonts, no embedded maps, no video embeds, no
analytics, no cookies. The old site carried a Borlabs cookie banner and
placeholders for YouTube, Vimeo, Facebook, Instagram and reCAPTCHA — all gone,
which is why no consent banner is needed here.

## Making changes

Ask Claude, review the diff in GitHub Desktop, commit and push.
