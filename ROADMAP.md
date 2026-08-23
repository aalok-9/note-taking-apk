# AetherNotes Product Roadmap

---

## Completed Phases (v1.0.0)

- [x] **Phase 1: Foundation & Clean Architecture**
  - Modular layered architecture (Presentation, Application, Domain, Data, Platform)
  - Cross-platform shell support for Windows, macOS, Android, and Web
  - Local-first IndexedDB database with Dexie, atomic transactions, and debounced autosave

- [x] **Phase 2: Modern Block-Based Editor**
  - 20+ block types (Headings, Paragraphs, Lists, Checklists, Toggles, Code, Tables, Equations, Quotes, Callouts, Audio notes)
  - Inline markdown shortcuts, slash command menu (`/`), floating rich text toolbar
  - Notion-style database tables with column types, sorting, filtering, and summary calculations

- [x] **Phase 3: Knowledge Management & Graph Intelligence**
  - Bidirectional internal wikilinks `[[Note Title]]` with autocomplete
  - Real-time backlinks inspector showing linked and unlinked mentions with snippets
  - Interactive 2D Force-Directed Knowledge Graph with D3 physics and cluster coloring
  - Tag management and hierarchical folder organization

- [x] **Phase 4: Digital Paper & Canvas Handwriting**
  - High performance Canvas 2D stroke smoothing engine with stylus pressure sensitivity
  - Pen, Pencil, Highlighter (multiply blend), Stroke Eraser, Lasso Selection, and Geometric Shapes
  - Paper templates (Ruled, Narrow Ruled, College Ruled, Grid, Dotted, Cornell, Graph) and paper tints

- [x] **Phase 5: Persistent PDF Annotation**
  - PDF document viewer with zoom, page navigation, and vector highlight/comment layers

- [x] **Phase 6: Open Portability, Import & Export**
  - Full workspace `.zip` backup package creation and restore engine
  - Single/Multi-note export to Markdown, standalone styled HTML, Plain Text, JSON, and PDF
  - Universal Markdown importer

- [x] **Phase 7: Productivity, Recovery & Polish**
  - Aggregated Task Planner with bidirectional checklist sync
  - Local version snapshot history with time-travel diff preview and one-click restore
  - Soft-delete Trash bin with restoration and permanent purge
  - Global Command Palette (`Ctrl+P` / `Cmd+K`) and Quick Capture (`Ctrl+Shift+N`)
  - Light, Dark, OLED, Sepia themes and customizable accent colors
  - Pre-populated realistic CA Studies sample workspace

---

## Future Extensibility (v2.0+)

- [ ] **Optional Self-Hosted Sync Engine**
  - Conflict-free Replicated Data Types (CRDTs) for multi-device sync
  - End-to-end encryption (E2EE) with zero-knowledge private keys
  - Self-hosted Docker container with WebSockets / SQLite backend

- [ ] **Local AI / LLM Extension Layer (Optional & Privacy-First)**
  - Local ONNX / WebLLM semantic search and note summarization
  - Automatic flashcard generation and question extraction
