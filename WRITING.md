# Writing a post

## 1. Create the file

Posts are Markdown files in `_posts/`, named `YYYY-MM-DD-short-slug.md`. The slug becomes the URL:

    _posts/2026-10-12-why-laser-ranging.md  →  /writing/why-laser-ranging/

Start the file with this front matter:

```yaml
---
title: Why laser ranging
description: One sentence. Shown on the index, in Google results and in link previews.
tags: [engineering]        # optional
math: true                 # optional: enables $$ ... $$ and \( ... \) equations
image: /images/posts/why-laser-ranging/cover.png   # optional: social preview image (1200×630)
---
```

Then write in normal Markdown. Useful extras:

- Images: put them in `images/posts/<slug>/` and use `![Alt text](/images/posts/<slug>/fig1.png)`. A line of italics directly under an image renders as a caption.
- Footnotes: `a claim[^1]`, then `[^1]: The source.` at the bottom.
- Code: fenced blocks with a language, e.g. ```` ```python ````.
- Tables: GitHub-style pipe tables.

## 2. Work on it privately (optional)

Put unfinished posts in `_drafts/` with no date in the filename (`_drafts/why-laser-ranging.md`). They're never published. To preview them locally:

    bundle exec jekyll serve --drafts

and open http://localhost:4000. When it's ready, move it to `_posts/` with a date prefix.

## 3. Publish

Commit and push to `master`. GitHub Pages rebuilds in about a minute. The post appears on the home page, at `/writing/`, in `feed.xml` and in the sitemap automatically.

To write straight from the browser: on GitHub, go to the `_posts/` folder, click **Add file → Create new file**, name it as above and commit.

## Adding to the gallery

1. Put the image in `images/gallery/`. Aim for about 1600 px on the long edge, saved as JPEG at around 80% quality.
2. Add an entry to `_data/gallery.yml`. The order in the file is the order on the page:

```yaml
- src: /images/gallery/station-dusk.jpg
  caption: First light
  place: Somewhere dark
  year: 2026
  credit: Photo — Jane Smith   # only if you didn't take it
```

Check the image doesn't show anything the list below rules out, such as site details, equipment close-ups or screens.

## Before publishing: checklist

The site is personal, but the subject matter overlaps with dual-use and export-controlled areas. Check every post:

- [ ] Nothing that isn't already public: stay at the level of published papers, public talks or textbook physics.
- [ ] No station coordinates or site details beyond what's publicly listed (e.g. ILRS station names).
- [ ] No link budgets, laser or detector parameters, measured precision specs, or performance figures for real systems.
- [ ] No customer, partner or prospect names, and no unreleased commercial or funding details.
- [ ] No tracking data or results for specific non-cooperative, military or unidentified objects.
- [ ] Not written on behalf of Foundational, and no company branding.
- [ ] If in doubt, run it past export compliance first.
