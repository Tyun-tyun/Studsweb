# The Slapping Studs — website foundation

The bones only: identity, colour, type, layout, and the page list.
Everything visual is up for redesign; this is the part that should
survive one.

## The club

SIJHV **The Slapping Studs** — student ice hockey association at the
University of Twente, in Enschede. Founded **1982**; the oldest student
ice hockey club in the Netherlands. Roughly 50–60 members across four
squads — **Studs 1, Studs 2, Striking Stallions, Cadets** — and one
coach. English is the working language.

- **Home ice:** IJsbaan Twente, Colosseum 90, 7521 PT Enschede
- **Board:** bestuur@slappingstuds.nl · Postbus 217, 7500 AE Enschede
- **2026:** the Striking Stallions won the 5th Division North — the club's first divisional title.

## Build

Plain HTML, CSS and JavaScript. No framework, no build step, no dependencies. Each page is its own `.html` file; open `index.html`directly or serve the folder. The only external request is Google Fonts.

## Colour

Dark by default, with a light "paper" tone for reading sections.
**Gold is the only warm colour and belongs to the club. Cyan belongs to the editing layer and appears nowhere else.**

| Token | Value | Role |
|---|---|---|
| `--ink` | `#0C0D0E` | page background |
| `--ink2` | `#131518` | raised panel |
| `--ink3` | `#1B1E22` | hover / menu surface |
| `--bone` | `#EDEAE1` | text on dark; background of paper sections |
| `--bone2` | `#DFDBCF` | second paper tone |
| `--gold` | `#F7C325` | club accent (jersey gold) — the only warm colour |
| `--ice` | `#93A9B8` | labels, meta, data text |
| `--edit` | `#62C9DE` | admin / CMS layer only |
| `--danger` | `#E06B5A` | destructive actions |
| `--ok` | `#8FD1B0` | success / coach role |
| `--line-d` | `rgba(237,234,225,.13)` | hairline on dark |
| `--line-l` | `rgba(12,13,14,.16)` | hairline on paper |

## Type

Two families, strict jobs.

- **Archivo** sets everything. Display: condensed (~66% width axis),
  weight 800, uppercase. Text: normal width, 17px / 1.6.
  Labels, dates, scores and meta: Archivo, sentence case, 14–15px.
- **NY Rangers** (`/fonts`) is the club's own face: the home hero
  wordmark and jersey numbers only.
- Never: monospace, tiny uppercase letter-spaced labels, eyebrow
  labels above headings, 01/02/03 numbering, hairline rules or 1px
  outlined boxes (separate with space or a tone step), gradients
  (except a scrim over a photo), shadows on things at rest.
  `--mono`, `--hdr-disp` and `--hdr-ui` remain as token names and
  all resolve to Archivo.

Headline scale: `d1` clamp(52–158px) · `d2` clamp(38–90px) ·
`d3` clamp(26–50px) · `d4` clamp(19–28px).

## Layout

- Content max width `--maxw` = **1340px**, centred.
- Page gutter `--pad` = **clamp(18px, 4vw, 56px)**.
- A fixed header and a shared footer on every page.
- **Photos are never faked.** An image slot with no file shows a
  hatched placeholder captioned with what belongs there.

All of the above lives in `css/tokens.css` — change it there and it
changes everywhere. Start there.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home — hero, latest news, upcoming events, sign-up |
| `about.html` | About the association |
| `history.html` | Club history, 1982 → today |
| `players.html` | Rosters and coaching staff |
| `training.html` | Training times and how a practice works |
| `games.html` | This season's fixtures and competitions |
| `past-games.html` | Results archive by season |
| `news.html` | Latest posts |
| `archive.html` | News archive by season |
| `hockey.html` | The game explained — rules, gear |
| `pictures.html` | Photo albums (members) |
| `contact.html` | Board, contact form, how to find the rink |
| `join.html` | Sign-up for an introduction practice |
| `sign-in.html` | Accounts and the permission model |
| `admin.html` | Content admin console (gated) |
| `account.html` | Member area, one view per `?v=`: overview, training, games & lifts (names, club van, travel signup), one game per `?v=game&id=`, profile (signed in only; `js/account.js`, `css/account.css`) |
| `404.html` | Not found |

## What is in the repo right now

Trimmed to `index.html` and only what it needs to run:

```
index.html
css/   tokens.css  base.css  layout.css  components.css  admin.css
js/    data.js  auth.js  routes.js  core.js  views.js  admin.js  app.js
assets/photos/hero-squad-2026.jpg
```

`js/data.js` holds all site content; `js/core.js` + `js/views.js` +
`js/app.js` are the engine. The earlier full 16-page prototype is in
git history at commit `2fef618` if any of it is worth pulling back.
