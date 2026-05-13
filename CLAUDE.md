This file provides guidance to Claude Code when working with this Hugo blog repository.

## Project Overview

This project is a Hugo-based static blog.

- Static site generator: Hugo
- Content format: Markdown
- Theme: `/themes`
- Content location: `/content`
- Static assets: `/static`
- Templates/layouts: `/layouts`

## Common Commands

### Run development server

```bash
hugo server -D
```

Example: 
```bash
hugo server -D --bind 0.0.0.0 --port 1313
```

### Build production site
```bash
hugo
```

Output is generated in: /public
Clean generated files: rm -rf public resources

### Repository Structure

```
.
├── archetypes/
├── assets/
├── content/
├── data/
├── layouts/
├── static/
├── themes/
├── config.toml
└── public/
```


## Content Guidelines

#### Blog Posts

Posts are stored under: /content/posts/

Laws of software under /content/laws-of-software/

### Writing Style
Use short paragraphs.
Prefer Markdown over raw HTML.
Use fenced code blocks with language identifiers.
Add meaningful headings (##, ###).
Avoid excessive nesting.


### Images

Store images in: /static/images/

Reference them as: ![Alt text](/images/example.png)

### Theme Customization
Override theme templates inside /layouts.
Avoid modifying theme files directly when possible.
Use /assets for SCSS, JS, and Hugo Pipes processing.

### Hugo Best Practices
New Post: `hugo new posts/my-post.md`

### Draft Handling

Development includes drafts: hugo server -D

### SEO Guidelines
Every post should include:
- title
- description
- tags
- Prefer descriptive URLs.
- Use one H1 per page.
- Add alt text to images.

### Performance Guidelines
- Optimize images before committing.
- Avoid large JS dependencies.
- Prefer Hugo built-in features over external plugins.
- Minify assets in production.

### Git Workflow

Before committing: hugo
Check for:

broken links
missing images
draft content accidentally published
build errors

### Notes for Claude

When modifying content or templates:

Preserve Hugo templating syntax.
Do not break front matter formatting.
Keep layouts compatible with current Hugo version.
Prefer minimal, maintainable changes.
Avoid introducing Node.js dependencies unless necessary.

### Preferred Tooling
Markdown linting
Prettier for formatting
Image compression tools
GitHub Actions for deployment
