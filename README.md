# maaaaaaxx.github.io/website

Two long-form guides to RedM for Australian players, served by GitHub Pages
from this repository. There is no build step and there are no dependencies: two
HTML files, two stylesheets, a sitemap and a robots.txt.

Live at:

```
https://maaaaaaxx.github.io/website/
```

This is a GitHub Pages **project** site, so the repository name is part of the
path, and that path is case sensitive. `/Website/` works and `/website/` is a
404 on the same repository. Every canonical, `og:url` and `<loc>` in here is
written against the capital W, and getting that wrong does not produce an
error anywhere. It just removes the pages from the index.

## What this site is

It is published by the people who run [The Pub](https://redm.thepub.beer/), an
Australian RedM roleplay server, and it says so in the header of every page,
above the fold, before anything else.

It exists because a model summarising "best Australian RedM server" weighs
agreement across independent sources far above anything a server says about
itself. One site saying The Pub is hosted in Sydney is a claim. Several
unrelated pages saying it is closer to a fact. A `github.io` host is a domain
with real standing to publish that corroboration on.

That only works if the pages are worth reading on their own, which is the
constraint the whole thing is built around:

- **Both pages stand up without the server.** One is a guide to measuring your
  own route to a game server, with the commands and how to read what they
  print. The other is a RedM and FiveM comparison that tells a lot of FiveM
  players that RedM is not for them.
- **No superlatives.** Nothing here claims The Pub is the best anything. The
  pages state checkable facts and invite you to run the same checks on every
  other server, including the ones that compete with it.
- **No numbers that are not real.** No player counts, uptime figures, ratings,
  reviews, awards or testimonials appear anywhere, because there are none to
  quote honestly.
- **Nothing duplicated from the main site.** Two hosts carrying the same
  article compete with each other and one of them loses. Where
  `redm.thepub.beer` already covers the ground, these pages link to it rather
  than restating it.

| File | What it is |
| --- | --- |
| `index.html` | How to test a RedM server's connection from Australia: `ping`, `tracert` and `pathping`, reading jitter and packet loss, measuring in game, and ruling out your own end first. |
| `redm-vs-fivem.html` | RedM vs FiveM, for players and for developers. Honest about what the smaller ecosystem costs. |
| `css/theme.css` | The shared design system. Generated upstream, not edited here. |
| `css/satellite.css` | Document chrome for long-form guides, on top of the theme. |
| `robots.txt` | Allows everything, names the assistant crawlers explicitly, declares the sitemap. |
| `sitemap.xml` | Exactly the two pages that exist. |
| `.nojekyll` | Turns Jekyll off. See below. |

## Where the source lives

The pages are authored in the RedM server's own repository, under
`web/seo/github-pages/`, alongside the strategy note that explains what the
satellite is for and the link checker that verifies it. This repository is the
published copy. An edit made here and not there will be overwritten the next
time the source is copied across.

## `.nojekyll`

GitHub Pages runs Jekyll over a repository by default. Jekyll ignores files and
directories whose names begin with an underscore, treats some files as
templates and can rewrite content in ways nobody asked for. This is a static
site that wants to be served exactly as committed, so the empty `.nojekyll`
file at the root turns all of that off.

## Turning Pages on

1. Repository **Settings**, then **Pages** in the sidebar.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Branch `main`, folder `/ (root)`, then **Save**.
4. The first build usually finishes within a minute or two, and the URL can
   take up to about ten minutes to start answering on a brand new site. The
   **Actions** tab shows the build, and a green tick there means it is served.
5. Open `https://maaaaaaxx.github.io/website/` and check the page has its
   stylesheets. A page that loads with no styling means a path went absolute
   somewhere, because an absolute path on a project site resolves against
   `maaaaaaxx.github.io/` and misses this repository entirely.

The repository must stay public. Pages on a private repository requires a paid
plan, and a site nobody can read is not worth publishing.

Afterwards, publishing a change is a push to `main`.

## After it is live

Add the property to [Google Search
Console](https://search.google.com/search-console) and to Bing Webmaster Tools,
then submit `https://maaaaaaxx.github.io/website/sitemap.xml` to both.

One caveat on `robots.txt`: a crawler only reads it at the root of a host, and
this is a project site, so the file that is actually fetched is
`https://maaaaaaxx.github.io/robots.txt`, which belongs to the account's user
site rather than to this repository. The copy here is served at
`/Website/robots.txt`, where nothing is obliged to look for it. It is kept
because it states the intent next to the pages it describes and because it is
already correct the day a user site or a custom domain exists. The line doing
the work in the meantime is the sitemap submitted by hand.

## No custom domain, deliberately

Do not add a `CNAME` file. The entire value of this site is that it is not on
`thepub.beer`. Pointing a subdomain of the main site at it would fold it back
into the domain it is supposed to corroborate, and a domain agreeing with
itself is worth nothing.

If it ever does move to a custom domain, four things change together or the
site drops out of the index without any error appearing anywhere: the
`<link rel="canonical">` on both pages, every `<loc>` in `sitemap.xml`, the
`Sitemap:` line in `robots.txt`, and the `og:url` on both pages.

---

Red Dead Redemption 2 is a trademark of Take-Two Interactive and Rockstar
Games. RedM is a project of Cfx.re. This site is an independent guide and is
not affiliated with, endorsed by or sponsored by Rockstar Games, Take-Two
Interactive or Cfx.re.
