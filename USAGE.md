[简体中文](./USAGE_zh.md) | English
# 💎 RubyCite Pro v1.2 User Manual

This document provides a complete guide for **RubyCite Pro** users in English, covering everything from installation and configuration to daily usage.

---

## Table of Contents
- [RubyCite Pro User Guide (English)](#rubycite-pro-user-guide-english)
  - [Table of Contents](#table-of-contents)
  - [System Requirements](#system-requirements)
  - [Installation \& Launch](#installation--launch)
  - [Interface Overview](#interface-overview)
  - [Core Workflows](#core-workflows)
    - [Main Line: Index → Q\&A → Citation](#main-line-index--qa--citation)
    - [Side Line: Analyze → Review](#side-line-analyze--review)
  - [Feature Details](#feature-details)
    - [Convert](#convert)
    - [Index / Q\&A](#index--qa)
    - [Analyze](#analyze)
    - [Review Assist](#review-assist)
    - [Citation Assist](#citation-assist)
    - [Settings](#settings)
  - [FAQ](#faq)
  - [Data Storage Locations](#data-storage-locations)
  - [Support \& Feedback](#support--feedback)

---

## System Requirements
| Platform | Requirement |
|----------|-------------|
| macOS    | Apple Silicon preferred, Intel also supported (requires appropriate Rust toolchain) |
| Windows  | Windows 10/11 (use the official installer) |

* Requires **selectable‑text PDFs** (scanned PDFs may have limited recognition).
* If you use AI features, make sure an LLM is configured (local model or cloud API).
* Indexing and vectorisation use the built‑in `multilingual‑e5‑small` model; network access is only needed for Crossref lookup or cloud LLMs.

---

## Installation & Launch
1. **Download**: Get the appropriate installer or source code from the GitHub Releases page.
2. **Install**: Double‑click the `.dmg` on macOS or the `.exe` on Windows.
3. **Launch**: Double‑click the desktop icon.
4. **First Run**: The app creates a data directory at `~/Library/Application Support/RubyCite/` (macOS) or `%APPDATA%\RubyCite\` (Windows).

---

## Interface Overview
![](ui/app-icon.png) *(top‑left icon)*

| Area | Function |
|------|----------|
| **Top Bar** | Language switch button, global actions |
| **Left Activity Bar** | Seven tabs: Convert, Index / Q&A, Analyze, Review Assist, Citation Assist, Settings, About |
| **Main Workspace** | Shows paper list, Markdown editor, or AI results depending on the selected tab |
| **Right Panel** | Shows figures & metadata in Convert/Review; shows index statistics in Index / Q&A |

The UI uses the **Codicons** icon set, supports a dark theme, and can be switched between Chinese and English in Settings.

---

## Core Workflows
RubyCite Pro offers two primary workflows that can be used independently or together.

### Main Line: Index → Q&A → Citation
```text
① Convert – import PDF or Markdown
   ↓
② Index / Q&A – select papers → Build index (vector index creation)
   ↓
③ Ask questions to the library (optional)
   ↓
④ Citation Assist – paste draft → automatically add `{Author, Year}` citations
   ↓
⑤ Export RIS → import into EndNote / Zotero → update citations in Word
```

### Side Line: Analyze → Review
```text
① Convert – import papers
   ↓
② Analyze – generate a single‑paper AI summary card (`.digest.md`)
   ↓
③ Review Assist – select multiple papers → generate a review draft
   ↓
④ Export RIS → update citations in Word
```

---

## Feature Details

### Convert
* **Select PDFs…** or **Import Markdown…** to add papers.
* Supports PDF → Markdown conversion, automatically extracting text, tables, and images.
* Converted files are stored in the `markdown/` folder and can be previewed in the left list.

### Index / Q&A
1. Tick the `.md` files you want to index (exclude `.digest.md`).
2. Click **Build index** – the app uses `multilingual‑e5‑small` to create a vector index.
3. Enter a question on the right and click **Ask** – the AI retrieves relevant passages and answers in the language of the query.

### Analyze
* Select a Markdown file and click **Generate cards** to obtain an AI‑generated summary card containing **Scientific question, Innovation, Core findings** (`.digest.md`).
* You can add personal notes to the card and click **Save notes**.

### Review Assist
1. Tick multiple papers → **Feed to model**.
2. Write a **Review prompt** (you can specify the output language).
3. Click **Generate review** – the app produces a review draft which can be exported as RIS.

### Citation Assist
1. Paste or type the full draft on the left.
2. Click **Add citation** – the system searches the library sentence by sentence and shows the draft with `{Author, Year}` tags on the right.
3. Copy the tagged draft into Word, use **Export RIS** to import into EndNote/Zotero, then update citations in Word.

### Settings
* **LLM Provider** – built‑in llama.cpp, Ollama, LM Studio, or any OpenAI‑compatible API.
* **Model** – select a model and **Test connection**.
* **UI Language**, **Chunk size** (for indexing) – changes require a new **Build index**.
* Additional options: network proxy, log level, etc.

---

## FAQ
1. **Why does Citation Assist return no matches?**
   - Ensure you have built the index in **Index / Q&A** first, and that the draft sentences are related to the topics in your library.
2. **Why doesn’t the answer language follow the UI language?**
   - The answer language follows the language of the question, independent of the UI setting.
3. **What should I do after changing the chunk size?**
   - After adjusting the size in Settings, you must rebuild the index.
4. **PDF conversion fails – what now?**
   - Verify the PDF is a publisher‑provided file with selectable text; scanned PDFs have poor results.
5. **What’s the difference between `full .md` and `.digest.md`?**
   - `full .md` contains the complete paper text; `.digest.md` is an AI‑generated summary card used for Review and is **not** indexed.

---

## Data Storage Locations
| Path / File | Content |
|-------------|---------|
| `markdown/` | Converted Markdown files |
| `markdown_assets/` | Extracted images |
| `pdfs/` | Original PDFs |
| `models/` | Local `.gguf` models |
| `embedmodels/` | Embedding models used for indexing |
| `cite_index.db` | Vector citation index database |
| `library.json` / `library.ris` | Paper library and RIS export |
| `review.md` | Most recent generated review |
| `settings.json` | Application settings |

You can quickly open this directory via **Settings → Open data folder** in the UI.

---

## Support & Feedback
* **Report issues**: Email <chemiker2010@gmail.com>.
* **Source code**: <https://github.com/chemiker2010/RubyCite> (feel free to submit Issues or PRs).

---

We hope you enjoy using RubyCite Pro! If you have any questions, please don’t hesitate to contact us.
