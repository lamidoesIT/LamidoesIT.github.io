# Lami Langa — Portfolio

Plain HTML + CSS. No build step, no frameworks, no npm. Open `index.html` in a browser and
it works.

## Files

```
site/
├── index.html              one-page portfolio
├── style.css               design tokens — edit :root to reskin the whole site
├── projects/
│   └── finsight.html
└── assets/
    ├── lami-headshot.png
    ├── favicon.svg
    ├── og.png              social share preview (1200x630)
    ├── certs/              certification badges
    ├── logos/              skill logos
    └── projects/           project screenshots
```

## Before you publish

Nothing is left to configure. The FINSIGHT card links to the live demo and the repo, and
the Contact section links straight to LinkedIn and email — there is no form, so there is
nothing that can silently fail.

**One thing to keep an eye on:** FINSIGHT is hosted on Render's free tier, which spins the
service down after 15 minutes of no traffic; the next visitor waits about a minute. The
site warns them, but a keep-alive ping (cron-job.org, every ~14 minutes) or Render's $7/mo
Starter plan removes the wait.

## Content accuracy — read this

The FINSIGHT write-up was drafted from the screenshot and what you described. Check every
claim before this goes in front of a recruiter, particularly how classification actually
works and whether the parser really handles more than one bank's statement format.
Anything you cannot defend in an interview, cut.

## Adding projects later

Copy `projects/finsight.html`, change the content, drop a screenshot into
`assets/projects/`, then duplicate the `.project` block in `index.html`. For a second
project, reverse the order of the text and the `<figure>` so the images alternate sides.

## Publish on GitHub Pages

```bash
cd site
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/LamidoesIT/LamidoesIT.github.io.git
git push -u origin main
```

Naming the repo **`LamidoesIT.github.io`** publishes it at `https://LamidoesIT.github.io`.

Any other repo name works too — push it, then **Settings -> Pages -> Source: Deploy from a
branch -> main / (root)**. It lands at `https://LamidoesIT.github.io/<repo-name>/`.

## Editing notes

- Everything visual comes from the CSS variables at the top of `style.css`. Change
  `--color-accent` and every button, icon circle and arrow follows.
- `--card-width` controls how wide the centre column is.
- Sections fade in on scroll via the script at the bottom of each page. Elements marked
  `data-reveal` start hidden; without JavaScript they show immediately.
- Fonts are Poppins from Google Fonts. To go offline, download it and add an `@font-face`
  block to `style.css`.
