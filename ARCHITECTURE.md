# AetherNotes Architecture Specification

AetherNotes follows a modular, decoupled Clean Architecture designed for high performance, local-first reliability, offline longevity, and cross-platform extensibility.

---

## 1. Architectural Layers

```
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  - React 19 Components (BlockEditor, DigitalPaper, Graph)   │
│  - Tailwind CSS + CSS Variables (Theming & Density)         │
│  - Adaptive Layout (Sidebar, NoteList, Navbar, Inspector)   │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                    Application Layer                        │
│  - useWorkspace State & Debounced Autosave Engine           │
│  - SearchEngine (Fuzzy Matcher & Multi-field Indexer)       │
│  - PortabilityService (ZIP Package, MD, HTML Export)        │
│  - AudioRecorderService (Web Audio API & Analyzer)          │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                      Domain Layer                           │
│  - Note, Block, CanvasData, TableData, Workspace Models     │
│  - Wikilink & Backlink Bidirectional Parser                 │
│  - 2D Force Graph Physics Generator (D3-force)              │
│  - Markdown-to-Blocks & Blocks-to-Markdown Converters       │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                      Data Layer                             │
│  - Dexie.js (IndexedDB Local Database)                      │
│  - Atomic Transactions & Version Snapshot History           │
│  - Crash-Resilient Write Pipeline                           │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                    Platform Layer                           │
│  - Electron Desktop Bridge (Windows / macOS)                │
│  - Capacitor Native Bridge (Android / iOS)                  │
│  - File System Access API & Pointer Events (Stylus Pressure)│
└─────────────────────────────────────────────────────────────┘
```

---

## 2. Key Subsystem Designs

### 2.1 Block Editor Architecture
- **State Model**: Notes contain an ordered array of `Block` objects with unique IDs and type tags.
- **Rendering**: Each block type (`paragraph`, `heading`, `table`, `code`, `equation`, `callout`, etc.) renders a dedicated component capable of inline editing and keyboard navigation without re-rendering the whole tree.
- **Wikilink Extraction**: Outgoing links `[[Note Title]]` are parsed in real time to update bidirectional backlinks and graph nodes.

### 2.2 Vector Digital Paper Engine
- **Canvas Rendering**: Uses high-DPI Canvas 2D with Catmull-Rom spline curve interpolation for natural, smooth handwriting.
- **Stylus Pressure**: Pointer events capture `e.pressure` to dynamically modulate line thickness.
- **Layer Separation**: Highlighters render on lower layers with `multiply` blend modes, while geometric shapes and pen strokes render on upper layers.
- **Paper Templates**: Procedural SVG backgrounds generate Ruled, Grid, Dotted, Cornell, and Graph lines behind the drawing canvas.

### 2.3 Knowledge Graph Engine
- **Physics Simulation**: Uses `d3-force` with link force, charge repulsion (`-200`), and collision radii.
- **Degree Sizing**: Node radius dynamically scales with incoming and outgoing connection degrees.
- **Interactive Navigation**: Clicking any node navigates the workspace directly to the corresponding note.

### 2.4 Local Persistence & Crash Safety
- **Debounced Writes**: Edits are persisted with a 350ms debounce into IndexedDB with atomic transactions.
- **Revision Snapshots**: Major edit sessions capture snapshot revisions with time-travel restore capabilities.
- **Soft Deletion**: Notes in trash remain in the database until permanently emptied.
