# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is a **Mintlify documentation site** - an MDX-based documentation platform. The content is organized as MDX files with YAML frontmatter, and navigation/config is centralized in `docs.json`.

## Development commands

```bash
# Install Mintlify CLI globally (first time setup)
npm i -g mint

# Start local development server (runs on port 3000)
mint dev

# Run on custom port
mint dev --port 3333

# Update CLI to latest version
mint update

# Validate links in documentation
mint broken-links
```

**Note:** Node.js 19 or higher is required.

## Architecture

### Core configuration

- **`docs.json`** - Central configuration containing:
  - Theme settings (theme: "maple", primary color: #16A34A)
  - Navigation structure with tabs and groups
  - Logo/favicon paths
  - API playground configuration
  - Contextual AI assistant options
  - Footer social links

### Content structure

- **Format:** MDX files with YAML frontmatter
- **Navigation:** Manually defined in docs.json (not automatic)
- **Tabs:** Two main tabs - "Guides" and "API reference"
- **Folder mapping:** Pages in folders use folder path in navigation (e.g., `essentials/settings` maps to `essentials/settings.mdx`)

### Frontmatter requirements

Every MDX page must include:
- `title`: Clear, descriptive page title
- `description`: Concise summary for SEO/navigation
- `icon`: (optional) Icon name for the page

### Mintlify component library

Commonly used components:
- **Callouts:** `<Note>`, `<Tip>`, `<Warning>`, `<Info>`, `<Check>`
- **Code:** `<CodeGroup>`, `<RequestExample>`, `<ResponseExample>`
- **Structure:** `<Steps>`, `<Step>`, `<Tabs>`, `<Accordion>`, `<AccordionGroup>`
- **API Docs:** `<ParamField>`, `<ResponseField>`, `<Expandable>`
- **Media:** `<Frame>`, `<Card>`, `<CardGroup>`, `<Columns>`

### Reusable snippets

Files in `/snippets/` directory can be imported as components in other MDX files.

### API documentation

OpenAPI 3.1.0 specification is located at `/api-reference/openapi.json`.

## Content guidelines

- Second-person voice ("you")
- Prerequisites at start of procedural content
- Test all code examples before including them
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links
- Search for existing information before adding new content
- Match style and formatting of existing pages

## Deployment

- Automatic deployment via Mintlify GitHub app
- Changes deploy to production after pushing to default branch
- No build commands needed - Mintlify handles everything
