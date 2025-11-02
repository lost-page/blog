# Lost Page Blog

A tech blog built with Hugo, focused on technology, engineering skills, leadership, and team topics.

## Features

- Hugo-based static site generation
- PaperMod theme for a clean, minimal design
- Markdown-based content authoring
- Full-text search functionality (Fuse.js)
- Syntax highlighting for code blocks (Chroma)
- Tag and category taxonomies
- RSS/Atom feed generation
- Automatic deployment to GitHub Pages

## Prerequisites

- Hugo Extended v0.152.2 or later
- Git

## Local Development

### Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd lost-page-blog
```

2. Install Hugo Extended v0.152.2 or later:

**Linux (Arch):**
```bash
sudo pacman -S hugo
```

**Linux (Debian/Ubuntu):**
```bash
sudo apt install hugo
```

**macOS:**
```bash
brew install hugo
```

**Windows:**
```bash
choco install hugo-extended
```

**Or download directly:**
Download from [Hugo Releases](https://github.com/gohugoio/hugo/releases/v0.152.2)

### Running the Development Server

Start the local Hugo server with draft content enabled:

```bash
hugo server --buildDrafts
```

The site will be available at `http://localhost:1313/`

### Creating New Posts

Create a new blog post:

```bash
hugo new content posts/my-new-post.md
```

This will create a new file at `content/posts/my-new-post.md` with the frontmatter template.

Edit the file and add your content. Make sure to:
- Set `draft: false` when ready to publish
- Add relevant tags and categories
- Add a description and summary for SEO

Example frontmatter:

```yaml
---
title: "My New Post"
date: 2025-11-01T10:00:00-06:00
draft: false
tags: ["hugo", "tutorial"]
categories: ["engineering"]
description: "A brief description of the post"
summary: "A summary that appears in listings"
---
```

### Building the Site

Build the site for production:

```bash
hugo --gc --minify
```

The built site will be in the `public/` directory.

## Deployment

### GitHub Pages

The site is configured to automatically deploy to GitHub Pages using GitHub Actions.

#### Setup GitHub Pages

1. Go to your repository settings
2. Navigate to Pages section
3. Under "Build and deployment":
   - Source: GitHub Actions
4. Push to the `main` branch to trigger deployment

The workflow (`.github/workflows/hugo.yml`) will:
1. Build the Hugo site
2. Deploy to GitHub Pages
3. Make the site available at `https://username.github.io/lost-page-blog/`

#### Custom Domain (Optional)

To use a custom domain:
1. Add a `CNAME` file to the `static/` directory with your domain
2. Configure DNS records with your domain provider
3. Update `baseURL` in `hugo.toml` to your custom domain

## Project Structure

```
lost-page-blog/
├── archetypes/           # Content templates
│   ├── default.md       # Default archetype
│   └── posts.md         # Post archetype with tags/categories
├── content/             # Site content
│   ├── about/          # About page
│   ├── posts/          # Blog posts
│   └── search.md       # Search page
├── layouts/            # Custom layout templates
├── static/             # Static files (images, etc.)
├── themes/             # Hugo themes
│   └── PaperMod/      # PaperMod theme
├── .github/
│   └── workflows/
│       └── hugo.yml    # GitHub Pages deployment
├── hugo.toml           # Hugo configuration
└── README.md           # This file
```

## Configuration

Main configuration is in `hugo.toml`:

- **Site settings**: Title, description, author
- **Theme**: PaperMod
- **Menus**: Navigation structure
- **Taxonomies**: Tags and categories
- **Syntax highlighting**: Chroma with Monokai theme
- **Search**: Fuse.js configuration
- **RSS**: Enabled for home and sections

## Search Functionality

The site includes full-text search powered by Fuse.js:
- Search page: `/search/`
- Searches across post titles, summaries, and content
- Configured in `hugo.toml` under `params.fuseOpts`

## RSS Feed

RSS feeds are available at:
- Main feed: `/index.xml`
- Posts feed: `/posts/index.xml`
- Tag feeds: `/tags/<tag-name>/index.xml`
- Category feeds: `/categories/<category-name>/index.xml`

## Adding Content

### Blog Posts

1. Create a new post: `hugo new content posts/post-name.md`
2. Edit the file in `content/posts/`
3. Add frontmatter (title, date, tags, categories, description)
4. Write your content in Markdown
5. Set `draft: false` when ready to publish
6. Commit and push to deploy

### Pages

To add a new page:

1. Create a new file: `hugo new content page-name/index.md`
2. Edit the content
3. Add a menu entry in `hugo.toml` if needed

### Syntax Highlighting

Code blocks support syntax highlighting for many languages:

\`\`\`python
def hello():
    print("Hello, World!")
\`\`\`

Configured with line numbers and the Monokai color scheme.

## License

This project uses the PaperMod theme which is licensed under the MIT License.

## Support

For Hugo documentation: https://gohugo.io/documentation/
For PaperMod theme: https://github.com/adityatelange/hugo-PaperMod
