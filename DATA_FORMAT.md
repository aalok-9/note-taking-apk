# AetherWorkspace Open Data Format Specification (v1.0.0)

AetherNotes uses an open, transparent, user-owned format designed for long-term data preservation and portability.

---

## 1. Workspace Archive Package (.zip)

When a workspace is exported, it produces a standard ZIP archive with the following directory layout:

```
workspace_archive.zip/
├── manifest.json            # Workspace metadata and counts
├── folders.json             # Folders hierarchy
├── notebooks.json           # Optional notebooks hierarchy
├── notes/                   # Full JSON definitions of each note
│   ├── note_tax_rates.json
│   └── note_audit_sa.json
├── markdown/                # Human-readable Markdown mirrors
│   ├── Taxation_Corporate_Tax_Rates.md
│   └── Audit_SA200_Framework.md
└── attachments/             # Local images, audio, and documents
```

---

## 2. Manifest Schema (`manifest.json`)

```json
{
  "formatVersion": 1,
  "appName": "AetherNotes",
  "appVersion": "1.0.0",
  "exportedAt": "2026-08-23T01:00:00.000Z",
  "workspace": {
    "id": "ws_ca_studies",
    "name": "CA Studies Workspace",
    "description": "Study workspace",
    "formatVersion": 1,
    "createdAt": "2026-08-20T00:00:00.000Z",
    "updatedAt": "2026-08-23T01:00:00.000Z"
  },
  "counts": {
    "notes": 5,
    "folders": 4,
    "notebooks": 0
  }
}
```

---

## 3. Note Schema (`notes/*.json`)

```json
{
  "id": "note_123",
  "workspaceId": "ws_ca_studies",
  "folderId": "fld_taxation",
  "title": "Corporate Tax Regime",
  "viewMode": "editor",
  "isFavorite": true,
  "isPinned": false,
  "tags": ["Taxation", "DirectTax"],
  "createdAt": "2026-08-23T00:00:00.000Z",
  "updatedAt": "2026-08-23T01:00:00.000Z",
  "version": 2,
  "blocks": [
    {
      "id": "blk_1",
      "type": "heading-1",
      "content": "Corporate Tax Regime"
    },
    {
      "id": "blk_2",
      "type": "table",
      "content": "",
      "data": {
        "columns": [
          { "id": "col_1", "title": "Section", "type": "text", "width": 140 },
          { "id": "col_2", "title": "Rate", "type": "number", "width": 120 }
        ],
        "rows": [
          { "id": "r1", "cells": { "col_1": "115BAA", "col_2": 22 } }
        ]
      }
    }
  ],
  "canvasData": {
    "strokes": [],
    "shapes": [],
    "texts": [],
    "paperConfig": {
      "template": "ruled",
      "tint": "light",
      "lineSpacing": 28,
      "gridSize": 24
    }
  }
}
```
