# AetherNotes — Local-First Knowledge & Digital Paper Studio

> **One application. One local workspace. User-owned data. Offline-first. Cross-platform. Portable. Extensible.**

AetherNotes is a modern, unified, cross-platform knowledge management and digital paper studio combining:
- **Notion**'s modular block-based structured editor and multi-type database tables
- **Obsidian**'s bidirectional wikilinks (`[[Note]]`), backlinks inspector, and interactive 2D knowledge graph
- **GoodNotes & OneNote**'s fluid vector handwriting canvas with stylus pressure sensitivity, stroke smoothing, and digital paper templates (Ruled, Grid, Dotted, Cornell, Graph)
- **Apple Notes & Evernote**'s fast organization, folder hierarchies, tags, pinning, favorites, and instant search
- **Persistent PDF Annotation** with vector highlights, freehand drawing, and sticky note comments

---

## 🌟 Key Capabilities

### 1. 100% Local-First & Private
- All data resides on your device by default in an open, structured format.
- Zero mandatory cloud connectivity. Zero telemetry. Zero user registration.
- Fully operational without an internet connection.

### 2. Notion-Style Block Editor
- 20+ block types: Paragraph, Heading 1/2/3, Bulleted List, Numbered List, Checklist (with bidirectional task aggregation), Toggle Accordion, Blockquote, Callout (Info, Warning, Tip, Success), Code block (with language syntax & copy), Notion Database Table (Text, Number, Checkbox, Date, URL, Summary Calculations), LaTeX Math Equation ($$...$$), Audio recording block, and Dividers.
- Markdown inline shortcuts (`# `, `## `, `- [ ] `, ````, `> `, `---`).
- Slash command menu triggered with `/`.
- Floating rich text formatting toolbar on selection.

### 3. GoodNotes-Style Digital Paper & Handwriting
- High performance Canvas 2D vector engine with Catmull-Rom spline stroke smoothing.
- Pressure-sensitive stylus and touch support with palm rejection.
- Tools: Ballpoint Pen, Graphite Pencil, Highlighter (semi-transparent multiply blend), Stroke Eraser, Lasso Selection, Geometric Shapes (Rectangle, Ellipse, Triangle, Arrow, Line), and Text Box placement.
- Paper Templates: Ruled Lines, Narrow Ruled, College Ruled, Grid, Dotted, Graph, Cornell Notes, Checklist Planner, and Daily Journal with selectable paper tints (Light, Warm Ivory, Vintage Sepia, Dark Slate, Navy Blue).

### 4. Obsidian-Style Knowledge Graph & Bidirectional Links
- Internal wikilinks: `[[Note Title]]` with instant autocomplete popup.
- Backlinks Inspector: Real-time discovery of incoming links and unlinked text mentions with context snippets.
- Interactive 2D Force-Directed Graph visualization with physics simulation, node clustering, and click-to-open note navigation.

### 5. Open Data Portability & Backup
- Complete Workspace Backup & Restore mechanism (`.zip` packaging with `manifest.json`, `notes/`, `drawings/`, and `markdown/` mirrors).
- Single-Note Export: Markdown (`.md` with YAML frontmatter), Standalone Styled HTML (`.html`), Plain Text (`.txt`), Raw JSON (`.json`), and Print / Save to PDF.
- Universal Markdown importer.

### 6. Productivity & Organization
- Aggregated Tasks Planner pulling all checkboxes across all notes with bidirectional status syncing.
- Version History: Automatic local snapshot creation on edits with time-travel diff preview and one-click restore.
- Trash system with soft delete, restore, and permanent purge.
- Global Command Palette (`Ctrl+P` / `Ctrl+Shift+P` / `Cmd+K`) and Quick Capture modal (`Ctrl+Shift+N`).
- Global Fuzzy Search indexing titles, blocks, tags, and folder names.

---

## 🚀 Quick Start & Development

### Prerequisites
- **Node.js**: v18+ (tested on Node.js v26.x)
- **npm** or **yarn** / **pnpm**

### Install Dependencies
```bash
npm install
```

### Start Development Server
```bash
npm run dev
```
Open `http://localhost:5173` in your browser.

### Run Automated Test Suite
```bash
npm test
```

### Production Build
```bash
npm run build
```

---

## 📱 Cross-Platform Distribution

### 1. Windows & macOS Desktop (Electron)
```bash
npm run build
npm run electron:build
```

### 2. Android Mobile (Capacitor)
```bash
npm run build
npx cap add android
npx cap copy
npx cap open android
```

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + N` / `Cmd + N` | Create a new note |
| `Ctrl + P` / `Cmd + P` / `Cmd + K` | Open Command Palette |
| `Ctrl + Shift + F` | Global Fuzzy Search |
| `Ctrl + Shift + N` | Instant Quick Capture |
| `[[` | Autocomplete note wikilink |
| `/` | Open block command menu |
| `Ctrl + B` / `Ctrl + I` / `Ctrl + U` | Bold / Italic / Underline |
| `Ctrl + Z` / `Ctrl + Y` | Undo / Redo |

---

## 📄 License
MIT License. Built for private, local-first knowledge management.
