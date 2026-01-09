# synechism website

Personal digital garden for collecting bookmarks, videos, and papers with a hierarchical tag system.

## Stack
- **Astro** - static site generator
- **Fuse.js** - client-side fuzzy search
- **GitHub Pages** - hosting (deploys automatically on push to main)

## Adding Resources

Edit `src/data/resources.json`:

```json
{
  "meta": {
    "dateRange": "2026-01-01-ongoing",
    "resourceCount": 2,
    "tagCount": 4,
    "lastSync": "2026-01-09 14:30"
  },
  "resources": [
    {
      "id": "1",
      "title": "Resource Title",
      "type": "bookmark",
      "url": "https://example.com",
      "dateAdded": "2026-01-09",
      "summary": "Optional description",
      "tags": ["ai/machine_learning", "cs/theory"]
    }
  ]
}
```

**Fields:**
- `id` - unique string identifier
- `type` - one of: `"bookmark"`, `"video"`, `"paper"`
- `url` - the resource URL
- `dateAdded` - format: `YYYY-MM-DD`
- `summary` - optional, can be empty string `""`
- `tags` - array of tag paths matching the tag tree

**Remember to update `meta.resourceCount` when adding resources.**

## Adding Tags

Edit `src/data/tags.json`:

```json
{
  "tags": [
    {
      "name": "ai",
      "children": [
        { "name": "machine_learning", "children": [] }
      ]
    }
  ]
}
```

Tags are hierarchical. A resource tagged `"ai/machine_learning"` will appear under both `ai` and `ai/machine_learning`.

## Current Tag Tree
- ai (machine_learning, nlp, computer_vision)
- biology (neuroscience, genetics)
- cs (systems, theory, programming_languages)
- mathematics (algebra, analysis, topology)

## Development

```bash
npm run dev      # start dev server
npm run build    # build for production
```

## Deployment

Push to `main` branch. GitHub Actions will automatically build and deploy to https://synechism.github.io/website

## Theme

Using Dracula color scheme. Colors defined in `src/styles/global.css`.
