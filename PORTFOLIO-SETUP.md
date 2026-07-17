# Setup — AcademicPages, customized for your EB-1A portfolio

This is the real AcademicPages/Minimal Mistakes theme (same one Urmish's
site uses), with your info filled in and 5 new sections added that the
stock theme doesn't have: Industry Experience, Patents, Media Coverage,
Open Source, and Peer Review & Service.

## What's already done

- `_config.yml` — your name, bio, location, email, GitHub/LinkedIn/Twitter/
  Instagram, Google site verification code, and 5 new collections
  (`patents`, `media`, `opensource`, `academicservice`, `experience`)
- `_pages/about.md` — your real bio, carried over from your old site
- `_pages/cv.md` — your real education + links to your existing project PDFs
- `files/` — your 5 existing project PDFs, copied over from your old repo
- `_data/navigation.yml` — top nav reordered to: Industry Experience,
  Publications, Patents, Talks, Media Coverage, Open Source, Academic
  Service, CV
- Removed: the theme's demo blog posts, Teaching/Portfolio placeholder
  collections, and the "Guide" nav link (that page just explains the theme
  to new users — not useful once your site is live)
- One example entry left in each collection folder so you can see the
  format (delete once you've added real ones)

## Still to do (things I can't know for you)

1. **Fill in the blanks in `_config.yml`**: `googlescholar`, `orcid`,
   `employer` are currently blank — add them once you have the URLs.
2. **Replace the avatar**: swap `images/profile.png` for a real photo of
   yourself.
3. **`_pages/cv.md`**: I left your internship dates/titles as placeholders
   (`[Dates]`, `[Title]`) since I don't have that info — fill those in.
4. **Delete the example entries** once you've added real ones (or just
   overwrite them):
   `_publications/2009-10-01-paper-title-number-1.md`,
   `_talks/2012-03-01-talk-1.md`,
   `_patents/2026-01-01-example-patent.md`,
   `_media/2026-01-01-example-coverage.md`,
   `_opensource/2026-01-01-example-project.md`,
   `_academicservice/2026-01-01-example-review.md`,
   `_experience/2026-01-01-example-role.md`

## How to add a new entry

Copy the example file in the relevant collection folder, rename it, fill in
the front matter. E.g. for a new patent:

```bash
cp _patents/2026-01-01-example-patent.md _patents/2026-08-01-my-real-patent.md
```

```yaml
---
title: "A Method for Doing the Thing — US 11,234,567"
collection: patents
permalink: /patents/2026-08-01-my-real-patent
excerpt: 'One-sentence plain-language description.'
date: 2026-08-01
venue: 'US Patent and Trademark Office'
paperurl: 'https://patents.google.com/patent/US11234567'
citation: 'Upasani, S. (2026). U.S. Patent No. 11,234,567.'
---
Optional longer body text — this becomes the full individual page for this
entry (e.g. /patents/2026-08-01-my-real-patent/), separate from the summary
that shows on the /patents/ list page.
```

Same pattern for `_publications/`, `_talks/`, `_media/`, `_opensource/`,
`_academicservice/`, `_experience/` — just match the fields already used in
that folder's example file.

## Bulk-importing publications (if you export from Google Scholar)

`markdown_generator/publications.py` (or the `.ipynb` notebook, if you use
Jupyter) reads a CSV/TSV and generates one `.md` file per row. Useful once
you have more than a handful of papers. See
`markdown_generator/README.md` for the expected column format.

## Running it locally

```bash
bundle install
bundle exec jekyll serve
```
Visit `http://localhost:4000`. This theme has more gems than your old one
(`github-pages` gem specifically), so `bundle install` will take a bit
longer the first time — that's normal.

## Deploying

Same as before: push to `ShubhangiUpasani.github.io`, GitHub Pages builds it
automatically. Since this fully replaces your old site's theme, this should
be a full push (not a merge) — back up your old repo first if you want to
keep the ability to roll back (e.g. `git tag pre-academicpages-migration`
before you push these changes).
