# Static Site Generator (C++)

A lightweight static site generator built in C++. Drop the executable into your content folder, run it, get a complete HTML site ready for GitHub Pages.

No Node.js. No Python. No dependencies. Just the `.exe` and your Markdown files.

---

## Quickstart

1. Download `site_generator.exe` from this repo
2. Set up your content folder (see structure below)
3. Run `site_generator.exe`
4. Your site is generated in `docs/`

That's it.

---

## Folder Structure

Set up your project like this before running the generator:

```
your-portfolio/
├── site_generator.exe        ← drop it here
├── templates/
│   ├── template.html         ← your HTML shell
│   ├── style.css
│   └── search.js
└── content/
    ├── index.md              ← home page
    ├── about.md              ← about page
    ├── projects.md           ← projects page
    └── blog/                 ← optional, any subfolders become categories
        ├── tech/
        │   └── my-post.md
        └── books/
            └── review.md
```

The generator discovers everything under `content/` automatically. Add a folder, add a post — it appears in navigation without any config.

---

## Your Content Files

Each `.md` file becomes a page. Start with these three and add whatever you need:

**`content/index.md`** — your landing page
```markdown
# Your Name

Short bio. What you do. Where you are.

[About →](/about) | [Projects →](/projects)
```

**`content/about.md`** — longer bio, background, what you're looking for

**`content/projects.md`** — what you've built

Blog posts go under `content/blog/` in any subfolder structure you want. The folder name becomes the category label in navigation.

---

## Running the Generator

```bash
# Windows
site_generator.exe

# Output lands in docs/
```

Run it again any time you update content. The build cache only regenerates files that changed.

---

## Deploying to GitHub Pages

1. Push your project folder to a GitHub repo
2. Go to **Settings → Pages → Source** and set it to the `docs/` folder on `main`
3. Your site is live at `https://yourusername.github.io/your-repo`

To auto-rebuild on every push, add the included GitHub Actions workflow (`.github/workflows/build-site.yml`) to your repo. Push a new post, the site updates automatically.

---

## What Gets Generated

- A page for every `.md` file in `content/`
- Navigation menu built from your folder structure
- Category sidebar for blog posts
- Table of contents on long pages
- Paginated blog listing
- Client-side search
- Jupyter notebook pages if you drop `.ipynb` files in `content/`

---

## Customizing the Design

Edit `templates/template.html` and `templates/style.css` — these control the look of every page. The template uses simple placeholders:

| Placeholder | What it renders |
|---|---|
| `{{TITLE}}` | Page title |
| `{{CONTENT}}` | Your Markdown, converted to HTML |
| `{{NAVIGATION}}` | Auto-generated nav links |
| `{{SIDEBAR}}` | Category sidebar |
| `{{TOC}}` | Table of contents |

Change fonts, colors, layout — the generator just fills in the placeholders.

---

## Supported Markdown

- Headings (`#` through `######`)
- Bold and italic
- Links and images
- Ordered and unordered lists
- Code blocks and inline code
- Blockquotes
- Horizontal rules

---

## Requirements

Windows. That's it. The `.exe` is self-contained.

For other platforms (Mac/Linux), contact me, i will share the c++ 17 project files.

---

## Source

The full C++ source will be updated here in few short days, so that you could use this repo if you want to modify the generator itself, add features, or build it for a different platform.
