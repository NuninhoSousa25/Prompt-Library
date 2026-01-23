# Prompt Library

A minimalist, elegant, and professional web application to organize, store, and quickly access your AI prompts. Designed for senior developers and power users who need a clean interface for prompt management.

## 🚀 Features

### Core Management
- **Hierarchical Categories:** Create subfolders using `/` (e.g., `Work/Projects/AI`). Filters automatically include sub-items.
- **Drag & Drop Organization:**
    - **Reorder:** Drag categories to change their order.
    - **Nest:** Drag a category *onto* another to make it a subfolder.
    - **Un-nest:** Drag to the top level to remove from hierarchy.
- **Category Manager:** Bulk rename and reorganize categories via a dedicated modal.
- **Smart Variables:** Use `{{variable}}` placeholders in your prompts. A custom modal appears to fill them in before copying.
- **Expandable Cards:** Long prompts are truncated with a unified "Expand" button.

### 🎨 Visuals & UX
- **Theme Support:** Dark Mode (default) and Light Mode toggle with persistence.
- **Markdown Rendering:** Native support for **Bold**, *Italic*, and `Code Blocks` inside prompt cards for better readability.
- **Code Block Actions:** Dedicated "Copy Code" buttons inside markdown code blocks for instant snippet extraction.
- **Improved Tag Input:** Visual chip-based preview and clickable tag suggestions in the editor modal.
- **Enhanced Editor:** High-productivity modal layout (800px wide) with a tall (400px) text area for complex prompt editing.

### 🛠️ Prompt Builder
A dedicated "Staging Area" to construct complex prompts.
- **Compose:** Click the **✚ Add** button on any prompt card to send its text to the Builder.
- **Edit & Combine:** Mix and match multiple prompts in the right sidebar, add custom instructions, and edit the final result.
- **Copy All:** One-click copy for your constructed mega-prompt.
- **Mobile Access:** Dedicated toggle to access the builder on smaller screens.

### Data Management
- **Automatic Backups:** Creates timestamped copies of your files in a `backups/` folder.
- **Local Persistence:** Uses `localStorage` to save data directly in your browser.
- **JSON Import/Export:** Full backup and restore functionality with structure validation and content limits.
- **Export Versioning:** JSON exports include versioning and timestamps for future-proof compatibility.
- **Robustness:** Uses UUIDs for reliable prompt tracking across sorting and filtering.

## 🛠️ Technical Details

- **Architecture:** Vanilla JavaScript using **MVC (Model-View-Controller)** pattern for clean separation of concerns.
- **Performance:** 
    - Optimized rendering using `DocumentFragment`.
    - Single-pass variable replacement algorithm.
    - On-demand category cleanup to minimize overhead.
- **Stack:** HTML5, CSS3 (Variables, Flexbox/Grid), Zero-dependency JavaScript.

## 📋 How to Use

1. **Open:** Launch `index.html` in your browser.
2. **Import (Optional):** Click "Import JSON" in the sidebar and select a backup for a starter set.
3. **Create:** Click **+ New Prompt** top-right.
    - **Tags:** Enter tags separated by commas or click the suggestions.
    - **Variables:** Add placeholders like `{{Topic}}` in the body.
4. **Use:**
    - Click **Copy** to copy text (and fill variables via the modal).
    - Click **✚ Add** to add to the Builder.
    - Click tags in the sidebar to filter.
    - Use the **Toggle Theme** button in the sidebar to switch modes.

## 🎨 Design

- **Themes:** Dark (#121212) / Light (#f5f5f5)
- **Accent:** Soft Blue (#4a9eff / #007bff)
- **Typography:** Inter / System UI Sans-Serif