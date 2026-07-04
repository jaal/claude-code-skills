---
name: write-post
description: Create a new blog post for Olek's personal blog (olek.works / olekwrites.com, an Astro site with notes in src/notes/). Trigger when the user says "write a post", "new blogpost", "draft a note", pastes text to turn into a post, or asks to publish/schedule writing. Produces a correctly-formatted Markdown file with frontmatter, matching the existing conversational voice, plus a pixel-art cover-image prompt.
---

# write-post

Turn a raw idea or pasted draft into a finished, publish-ready blog post that
matches Olek's existing blog: an Astro site (`olek.works`, served at
`olekwrites.com`) whose posts live in `src/notes/` as dated Markdown files.

## Step 0 — Learn the current conventions

Before writing, read 2–3 recent files in `src/notes/` (sort by filename date,
newest last) to match the **current** voice and frontmatter. The blog evolves;
trust the latest posts over this document if they disagree. Also gather the
existing tag vocabulary:

```sh
grep -rhoE '^tags: \[.*\]' src/notes/ | sort | uniq -c | sort -rn
```

If you can't find `src/notes/`, ask the user for the blog repo path.

## Step 1 — Propose options, then write

Offer the user **2–3 options each** for slug, title, and excerpt, mark a
recommended one, then write the file. Also:

- Check grammar and syntax; suggest improvements, but keep the author's voice.
- Keep the **conversational, first-person** style: short paragraphs, plain
  words, the occasional one-line paragraph for emphasis.
- Structure with `##` section headers (and `###` where useful).
- Include **practical takeaways** — bullet lists of "what to do" / "how to".
- End with a short closing line or sign-off (e.g. "Happy writing!").
- Pick **1–4 tags** from the existing vocabulary (common ones: `technology`,
  `ai`, `reflection`, `writing`, `life-lessons`, `environment`, `books`,
  `projects`, `media`). Only invent a tag if nothing fits.

### File location and name

`src/notes/YYYY-MM-DD-<slug>.md` — the date in the filename is the publish
(`added`) date.

### Frontmatter format

```markdown
---
title: 'Title in Title Case'
slug: url-slug
added: YYYY-MM-DD HH:MM
updated: YYYY-MM-DD HH:MM
tags: [tag1, tag2, tag3]
excerpt: One sentence under 160 characters, written for SEO and the preview.
note: publish
---

![Alt text describing the cover](/images/<slug>.png)

# Title in Title Case

[body...]
```

### Scheduling rule

Unless the user gives a date, set both `added` and `updated` to **the next day
at 06:00** (this schedules the post: it stays hidden until that time, and the
daily automated build reveals it). Convert "tomorrow 06:00" to the concrete
`YYYY-MM-DD 06:00` — never leave a relative date.

## Step 2 — Cover-image prompt

After writing, output a ready-to-paste prompt for a pixel-art cover image. Pick
a visual metaphor tied to the post's topic:

```
Pixel art style 8-bit retro illustration of [VISUAL METAPHOR], simple clean
design, similar to retro video game graphics
```

Tell the user to save the result as `public/images/<slug>.png` (so the
frontmatter `/images/<slug>.png` reference resolves).

## Step 3 — SEO check

Confirm before finishing:
- `excerpt` ≤ 160 characters and contains the main keyword.
- `title` is specific and search-friendly.
- `slug` is short, lowercase, hyphenated, keyword-bearing.

## Publishing

The post is scheduled by its `added` date. To publish: commit and push now; the
post stays hidden until the date arrives, when a daily automated build makes it
visible. Don't push secrets; this repo is public.
