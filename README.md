# Venn Kit

A Venn diagram widget for comparing ideas. Single static page (`index.html`), no build step.

- Click inside a circle to add a thought; drag chips between zones, or off the diagram to delete.
- Click a circle label to rename it and describe it; click an empty overlap to describe that combination.
- Styling, all point-and-click:
  - Circle popover: color swatches (8 presets + custom picker).
  - Thought popover: its own color plus **B / I / S** (bold, italic, strikethrough).
  - Palette button (top right): font, text size (S / M / L), background color, default color for all thoughts, and text color.
- Three views of the same data, switched bottom-left:
  - **Venn** (2–3 groups): the diagram above.
  - **Table**: thoughts as rows, groups as columns; click a cell to toggle membership, a header or row title to rename, "+" to add a row or column.
  - **UpSet**: one column per combination that has thoughts, sorted by size; click a column to list its thoughts, drag a thought to another column to move it.
- Up to 8 groups (Venn shows at most 3; adding a 4th switches to UpSet).
- Import (top right): paste a range from Excel/Sheets or upload an .xlsx/.csv. First column = thought names, first row = group names, any filled cell = member. Shows a preview and replaces the current data on confirm.
- Everything saves to localStorage.

Run locally: open `index.html` in a browser.
