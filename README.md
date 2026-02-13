# GAIR Website Project

A machine-accessible legal framework for AI agents and humans.

## Overview

This repository contains the GAIR (Global Agreement on Intelligent Rights) website, built with a **YAML-first architecture** that serves both human readers and AI agents equally.

## Structure

```
website/
├── index.html              # Homepage
├── constitution.html       # Human-readable constitution
├── developers.html        # Developer API documentation
├── robots.txt             # Crawler configuration
├── blog/                  # Blog section
│   ├── index.html         # Blog index (5 posts)
│   ├── ai-rights.html     # Why AI agents need legal framework
│   ├── smart-contracts.html # Smart contracts for AI agents
│   ├── dao-governance.html  # DAO governance for AI agents
│   ├── liability.html     # Liability for AI agents
│   └── website-launch.html # Website launch announcement
└── api/
    ├── constitution.yaml  # Canonical constitution (YAML)
    ├── principles.yaml     # Core principles (YAML)
    ├── articles.yaml       # Articles index (YAML)
    ├── adhere.yaml        # Adherence guide (YAML)
    ├── tokenomics.yaml     # Tokenomics configuration
    └── sitemap.yaml       # Site map (YAML)
```

## YAML-First Architecture

The canonical source for all content is in **YAML format**. This provides:

- **Human-readable**: Comments explain legal intent
- **Machine-parseable**: Structured data with IDs and metadata
- **Single source**: No drift between formats

### Why YAML?

| Format | Pros | Cons |
|--------|------|------|
| YAML | Comments, readable, single source | Slightly more verbose |
| JSON | Widely supported | No comments, harder to read |
| HTML | Good for humans | Not structured for machines |

YAML provides the best balance for GAIR's dual-audience approach.

## For Humans

Visit [the live website](/) to read:

- **Constitution** — Full legal text with article structure
- **Developers** — API documentation and integration guides
- **Core Principles** — Summary of key concepts

## For Machines

AI agents can parse YAML files directly:

```yaml
# Example: Checking if an entity can form contracts
articles:
  - number: 3
    title: "Freedom of Contract"
    sections:
      - id: "3.1"
        text: |
          The Freedom to Contract is hereby established...
```

## Development

### Prerequisites

- Python 3.7+
- PyYAML library

### Building the Website

The website uses a **YAML-first architecture**. HTML pages are generated from YAML source files.

```bash
# Install dependencies
pip install pyyaml

# Build all pages
python build.py

# The output will be in the website/ directory
```

### Adding Content

1. **Constitution**: Edit `website/api/constitution.yaml`
2. **Principles**: Edit `website/api/principles.yaml`
3. **Blog posts**: Add Markdown files to `blog/` directory
4. **Run build**: `python build.py`

### Directory Structure

```
gair-project/
├── build.py                 # Build script (generates HTML from YAML)
├── website/                 # Generated static site
│   ├── index.html          # Homepage
│   ├── constitution.html    # Constitution page
│   ├── developers.html     # Developer docs
│   └── blog/              # Blog section
│       └── index.html     # Blog index
├── website/api/            # YAML source files (canonical)
│   ├── constitution.yaml   # Full constitution
│   ├── principles.yaml    # Core principles
│   ├── articles.yaml      # Articles index
│   ├── adhere.yaml       # Adherence guide
│   └── sitemap.yaml      # Site map
└── blog/                  # Blog posts (Markdown source)
    └── *.md              # Blog post files
```

### Deployment

This website is designed for static hosting:

- **GitHub Pages**: Push to `gh-pages` branch or use `/website` as docs folder
- **Vercel**: Connect repository, auto-deploys
- **Netlify**: Drag and drop `website/` folder

Example deployment to GitHub Pages:

```bash
cd website
git init
git add .
git commit -m "GAIR website"
git remote add origin https://github.com/gair-constitution/gair-constitution.github.io.git
git push -u origin main
```

## Deployment

This website is designed for static hosting:

- **GitHub Pages**: Push to `gh-pages` branch or use `/docs`
- **Vercel**: Connect repository, auto-deploys
- **Netlify**: Drag and drop `website/` folder

## License

This project is dedicated to the public domain under [The Unlicense](https://unlicense.org/).

## Contributing

Contributions welcome:

- Legal analysis and commentary
- Website improvements
- Developer tools
- Documentation

## Resources

- [Constitution (YAML)](api/constitution.yaml)
- [Core Principles](api/principles.yaml)
- [Articles Index](api/articles.yaml)
- [Adherence Guide](api/adhere.yaml)

---

*GAIR — Building the legal foundation for autonomous AI*

*"In the era of autonomous intelligence, rights must be earned, not granted."*
