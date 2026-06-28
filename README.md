# Blog website

A text-first personal notes blog built for native GitHub Pages with Jekyll.

## Local development

1. Install Ruby and Bundler.
2. Install dependencies:

```bash
bundle install
```

3. Run the site:

```bash
bundle exec jekyll serve
```

4. Open the local URL printed by Jekyll.

## Publishing

Push the repository to GitHub and enable GitHub Pages for the default branch.

## Writing a new post

Create a new file in `_posts/` named:

```text
YYYY-MM-DD-your-slug.md
```

Use front matter like this:

```md
---
title: Your title
date: 2026-06-24
tags: [notes, learning]
description: One-line summary for listings and feeds.
---
```

`description` is recommended. If it is missing, the site falls back to the post excerpt.
