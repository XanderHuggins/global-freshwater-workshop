# Global Freshwater Systems Science Workshop website

Source for [freshwatersystemsworkshop.org](https://freshwatersystemsworkshop.org/), built with [Hugo](https://gohugo.io/)
and the [Winston theme](https://github.com/zerostaticthemes/hugo-winston-theme).

GitHub Pages publishes the `docs` folder of the `main` branch (Settings > Pages: Deploy from a branch, `main`, `/docs`).
Running `hugo` builds the site into `docs`.

Needs **Hugo extended, version 0.158 or newer** (tested with 0.169.0).

## Download

The theme is a Git submodule, so clone with:

    git clone --recurse-submodules https://github.com/XanderHuggins/global-freshwater-workshop

If `themes/hugo-winston-theme` is empty after cloning, run `git submodule update --init`.

## Where things are

| What you see on the site | File to edit |
|---|---|
| Home page text and images | `content/_index.md` |
| People (name, role, photo, links) | `data/people.json` (photos in `static/images/people/`) |
| Workshops list and report links | `content/workshops/index.md` (reports in `static/pdfs/`) |
| Contact page | `content/contact.md` |
| Menu | `[menu]` in `config.toml` |
| Colours and fonts | `[params]` in `config.toml` |
| Text sizes | `assets/scss/_content.scss` (pages), `assets/scss/_intro.scss` (home page) |
| Image sizes on the home page | `assets/css/extended/home.css` |
| People page look | `assets/css/extended/people.css` |
| Home page layout | `layouts/index.html` |
| People page layout | `layouts/people/single.html` |
| Footer icons | `data/social.json` (layout in `layouts/partials/footer.html`) |
| Custom domain | `static/CNAME` (copied into `docs` on every build) |

Do not edit files inside `themes/hugo-winston-theme`: it is a link to the theme's own repository, so changes there
are never saved here. To change a theme file, copy it to the same path in this repository's own folders
(`layouts/`, `assets/`) and edit the copy. The copy takes priority over the theme's file.

## Preview

    hugo server

Then open http://localhost:1313. Ctrl+C stops it.

## Publish

    Remove-Item -Recurse -Force docs
    hugo
    git add -A
    git commit -m "what changed"
    git push

## History

- 7 November 2026: theme edits that had only existed on an old laptop (smaller text sizes, home page without a title,
  people page styles) were recovered from the published site and stored in this repository's own `assets/` and
  `layouts/` folders. The build output matches the site as published in September 2025. The config now builds
  straight into `docs` with minified output. The unused GitHub Actions workflow was removed.
