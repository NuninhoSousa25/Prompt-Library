# Prompt Library

A minimalist, single-file web application to organize, store, and quickly access your AI prompts. No dependencies, no build step — open `index.html` and go.

## Features

### Prompt Management
- **Create & Edit:** Full modal editor with name, content, and tags.
- **Smart Variables:** Use `{{variable}}` placeholders in prompts. A modal prompts you to fill them in before copying.
- **Markdown Support:** Headings, bold, italic, inline code, fenced code blocks, lists, and horizontal rules — rendered in cards and the detail panel.
- **Code Block Actions:** Each fenced code block gets its own "Copy Code" button.
- **Download as Markdown:** Download any prompt as a `.md` file.
- **Delete with confirmation.**

### Sidebar & Navigation
- **Collapsible Sidebar:** Collapses to icon-only strip; state persists across sessions.
- **Hierarchical Categories:** Use `/` in tag names to create nested categories (e.g. `Work/Projects/AI`). Filtering a parent includes all children.
- **Tag Filtering:** Click any category in the sidebar to filter prompts.
- **Real-time Search:** Searches both prompt names and content; multi-token, case-insensitive, debounced. Matches are highlighted in titles.

### Prompt Cards & Detail Panel
- **Two-column card grid** (collapses to single column on smaller screens).
- **3-line preview** with stripped markdown.
- **Detail panel:** Click any card to open a right-side panel with full rendered content and all actions (Copy, Edit, Download, Delete).
- **Tags** on cards are clickable to filter by that category.

### Category Management
- **Category Manager Modal:** Bulk rename categories; updates all prompts that use them.
- **Drag & Drop Reordering:** Drag categories to reorder or nest/unnest them in the sidebar tree.

### Editor
- **Three editor modes:** Edit, Split (side-by-side), and Preview — toggled via buttons in the modal.
- **Live preview** updates as you type in Split mode.
- **Tag input** with chip-style preview and clickable suggestions from existing categories.

### Data Management
- **Local Persistence:** All data stored in `localStorage`.
- **Export JSON:** Downloads a timestamped `prompts_backup_YYYY-MM-DD.json`.
- **Import JSON:** Upload a backup file; supports both plain array and versioned `{ prompts: [] }` formats. Skips duplicates (matched by name + content).
- **Sync from URL:** Fetch and merge prompts from a remote JSON endpoint. Configurable via modal; can auto-sync on page load. Skips duplicates and validates content size.
- **Delete All:** Clears all prompts with confirmation.

### UI & UX
- **Dark / Light mode** toggle with persistence. Dark is default.
- **Toast notifications** for copy confirmations, sync status, and action feedback.
- **Empty state** message when no prompts match the active filter.

## How to Use

1. **Open** `index.html` in your browser.
2. **Import (optional):**
   - Click "Import File" to load a local JSON backup.
   - Click "Sync from URL" to pull from a remote endpoint (default: `https://nuno-sousa.com/repository/uploads/prompts_backup.json`).
3. **Create:** Click **+ New Prompt** (top right).
   - Write content in markdown.
   - Add tags — comma-separated or click suggestions.
   - Use `{{variable}}` syntax for fill-in placeholders.
4. **Use:**
   - Click **Copy** to copy a prompt (variables modal appears if needed).
   - Click a card to open the detail panel.
   - Use the sidebar to filter by category or search by keyword.

## Technical Details

- **Architecture:** Vanilla JavaScript, MVC-style separation (Model / View / Controller).
- **Stack:** HTML5, CSS3 (custom properties, Flexbox, Grid), zero-dependency JavaScript.
- **Fonts:** `Instrument Serif` (headings) · `Geist Mono` (body/UI) — loaded from Google Fonts.
- **Performance:** `DocumentFragment` rendering, debounced search, on-demand category cleanup.
- **Storage:** `localStorage` for prompts, category order, theme, sidebar state, and sync settings.
- **IDs:** UUIDs for reliable prompt tracking across sorting and filtering.

## Design

| Token | Dark | Light |
|---|---|---|
| Background | `#0f0e0e` | `#e3dfd8` |
| Sidebar / Card | `#1e1e1e` | `#d9d5ce` |
| Text primary | `#e6dfdf` | `#000000` |
| Accent | `#ffffff` | `#000000` |
| Danger | `#e09191` | `#a63a3a` |

## Origin

Started from a single prompt to an LLM — see `guideline.txt` for the original spec.
