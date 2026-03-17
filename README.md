# KDP Quarto – Multi-Format Book Template

A professional Quarto-based workflow to create books ready for **Amazon KDP** (PDF), **EPUB** distribution, and a **website** — all from a single source.

## ✅ What this template does for you

| Feature | Detail |
|---|---|
| 📄 **KDP-ready PDF** | 6"×9" trim, KOMA-script, correct margins |
| 📱 **Valid EPUB** | Validated automatically with `epubcheck` |
| 🌐 **Website** | Dark/light theme, hosted on GitHub Pages |
| 🤖 **CI/CD** | GitHub Actions: renders + publishes on every push |
| 📚 **Bibliography** | BibTeX support via `references.bib` |
| 🖼️ **Images** | Cross-format image handling via `knitr::include_graphics()` |
| 🔀 **Conditional content** | Show/hide blocks per format (PDF / EPUB / HTML) |

## 🗂 Repository Structure

```
kdp_quarto/
├── _quarto.yml              # Book configuration (formats, metadata, chapters)
├── index.qmd                # Title page / welcome chapter
├── preface.qmd              # Preface
├── intro.qmd                # Introduction
├── chapter_1.qmd            # Chapter template
├── book_conclusion.qmd      # Conclusion
├── references.qmd           # Auto-generated references
├── references.bib           # BibTeX bibliography
├── epub.css                 # Custom CSS for EPUB and HTML
├── images/                  # Book images
├── .github/workflows/       # GitHub Actions CI/CD
├── editorial_workflow.md    # 4-phase editorial process guide
├── commercial_strategy.md   # KDP commercialization planning
├── ai_prompts.md            # AI-assisted writing prompts
└── progress_tracker.md      # Chapter status tracking
```

## 🚀 Quick Start

### 1. Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.3
- [R](https://cran.r-project.org/) ≥ 4.3 + `renv`
- TinyTeX (installed automatically by Quarto)

### 2. Render all formats locally

```bash
quarto render
```

Output goes into `_book/`:
- `_book/*.pdf` → upload to Amazon KDP
- `_book/*.epub` → upload to KDP / distribute
- `_book/index.html` → preview the website

### 3. Validate the EPUB

```bash
epubcheck _book/*.epub
```

### 4. Publish to GitHub Pages

Push to `main` — GitHub Actions handles the rest automatically.  
You can also trigger a manual build from the **Actions** tab → **Render and Publish** → **Run workflow**.

## 📐 KDP PDF Specifications

The `_quarto.yml` is pre-configured for the most common KDP interior size:

- **Trim:** 6"×9" (`paper=6in:9in`)
- **Font size:** 12 pt
- **Document class:** `scrbook` (KOMA-script)
- **Text area:** 4.5"×8" with 0.50" gutter
- **Code:** auto line-breaking via `fvextra`

For other KDP trim sizes, adjust `classoption` and `\areaset` in `_quarto.yml`.

## 📖 Editorial Workflow

See [`editorial_workflow.md`](./editorial_workflow.md) for the recommended 4-phase process:

1. AI-assisted first draft
2. Human revision
3. Technical / author validation
4. Final editing and formatting

## 💰 Commercial Strategy

See [`commercial_strategy.md`](./commercial_strategy.md) for a template on planning pricing, marketing, and multi-product ecosystems around your book.

## 🤖 AI Writing Prompts

See [`ai_prompts.md`](./ai_prompts.md) for ready-to-use prompts that help you generate chapter drafts, blurbs, and marketing copy.

## 📊 Chapter Progress

Track your writing status in [`progress_tracker.md`](./progress_tracker.md).

## 🔑 Key Strengths to Reuse in Other Repos

If you are porting this workflow to another book project, these are the most valuable pieces:

- **`_quarto.yml`** — Copy and adapt for any non-fiction book
- **GitHub Actions workflow** — Zero-config publish to GitHub Pages + epub validation
- **Conditional content blocks** — `{.content-hidden when-format="pdf"}` saves significant formatting work
- **`epub.css`** — Ensures images never overflow on small screens
- **`renv.lock`** — Reproducible R environment for years-long projects

