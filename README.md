[简体中文](./README_zh.md) | English &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                  
# ♦️ RubyCite Personal Research Hub.

<p align="left">
  <img src="https://img.shields.io/badge/Version-v2.0%20Stable-green?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/Architecture-Local--First-blueviolet?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/Security-100%25%20Offline%20Privacy-success?style=flat-square" alt="Privacy">
  <img src="https://img.shields.io/badge/Platform-macOS%20 or windows X64%20 -blue?style=flat-square" alt="Platform">
</p>

**RubyCite** is a desktop app for macOS and Windows that turns your computer into a **personal research hub**: import papers, read and search them locally, ask questions across your library, draft with citations, and finish in Word — without handing your PDF collection to a cloud service by default.

Everything lives on your machine: converted texts, library records, vector index, notes, and project manuscripts.

---

## Who it is for

RubyCite fits researchers and graduate students who:

- collect **English journal PDFs** (and bibliographic files) for literature reviews and thesis writing;
- want **semantic search and Q&A** over their own papers, not the open web;
- need **sentence-level citation suggestions** while drafting;
- write long manuscripts in **Markdown** and export to **Word** with EndNote-style or CSL-formatted references;
- prefer **local LLMs** (built-in or Ollama) or their own API keys.

---

## Three ways to work

### 1. Library workflow — import, index, cite

Build a searchable collection, then use it while you write elsewhere.

```text
Import PDFs or RIS / BibTeX / EndNote .enw / Markdown
   → Organize in groups; edit metadata; preview converted text
   → Build index on selected papers
   → Ask questions in the AI panel (optional)
   → Paste a draft into Citation assist → get {Author, Year} markers
   → Export RIS → Word / Zotero / EndNote
```

### 2. Analysis workflow — summarize, then review

```text
Import papers
   → AI Summary: five structured cards per paper + your reading notes
   → Review assist: feed multiple papers → generate a literature review
   → Export RIS or copy the review for Word
```

### 3. Writing workflow — draft inside RubyCite

Open a project folder and treat RubyCite like a lightweight writing IDE:

```text
New project from template (paper / review / grant / final report / empty)
   → Edit .md manuscripts with CodeMirror (syntax highlight, @ citation insert)
   → Check Outline, Preview, Bibliography, Dashboard, Problems
   → Export Word (EndNote markers, static CSL text, or RubyCite Word controls)
   → Optional: Word add-in to refresh citations in Word
```

All three workflows share the **same library** and the same **project bibliography**.

---

## What RubyCite actually does today

### Import and PDF conversion

- Converts **born-digital PDFs** with selectable text (publisher articles from Elsevier, Springer, IEEE, etc.).
- Extracts **body text, tables, figures**, and layout-aware reading order (including two-column articles).
- Rejects scanned or image-only PDFs when text cannot be extracted reliably.
- Also imports **RIS, BibTeX, EndNote `.enw`**, and existing **Markdown** files.
- You can **create references manually** without a PDF.

### Library and metadata

- A central **paper table** with full-text search (SQLite + FTS).
- **Manual groups** and **smart groups** (e.g. has PDF, has AI summary, year ≥ 2020).
- Rich **metadata editing**: title, authors, year, journal, DOI, cite key; **refresh from Crossref**; **CSTR verification**.
- **Find and merge duplicate** entries.
- **Paper preview** of converted Markdown (headings, tables, figures, reference list line by line).
- Separate tabs for **AI summary cards**, **your reading notes**, **figure list**, and **metadata / CSL preview**.
- **Right-click** a row for quick access to metadata, preview, index actions, or delete.
- **Copy formatted bibliographies** (GB/T 7714, APA 7, IEEE, author–year) and **import custom CSL styles**.

### Index and library Q&A

- Builds a **local vector index** with the built-in **multilingual-e5-small** embedding model.
- You choose which papers to index; chunk size is configurable in Settings (rebuild after changes).
- **Ask natural-language questions** over indexed papers; answers follow the **language of your question**.
- See index status, indexed file list, and remove individual papers from the index.

### Citation assist

- Paste a full draft; RubyCite splits it into sentences and searches the index for each.
- Up to **three source passages per sentence**; same paper is merged into one `{Author, Year}` marker.
- View which sources matched each sentence; **copy the annotated draft** for Word.
- Requires a built index first.

### AI Summary (single paper)

- Generates **five AI cards**: Scientific question, Innovation, Key findings, Limitations & outlook, Future research directions.
- Saves a lightweight **`.digest.md`** linked to the full paper; you can add **personal reading notes** on a dedicated tab.
- **Export digest** (e.g. for Obsidian).
- Output language is selectable.

### Review assist (multiple papers)

- Check papers → **Feed to model** → choose template: **journal article**, **thesis**, or **survey report**.
- Write a custom prompt; generate a long-form review in the AI panel.
- **Save or copy** the review; export **RIS** for reference managers.

### Writing workspace

- **Explorer** for your project folder; create files and folders; open multiple manuscript tabs.
- **CodeMirror 6 editor** with Markdown highlighting.
- **Project bibliography** in the sidebar — link library papers to the current project.
- **Two citation syntaxes** in one document: `[@cite_key]` (structured) and `{Author, Year}` (Word/EndNote).
- Type **`@`** to search the library and insert cite keys.

**Workbench tools for the open manuscript:**

| Tool | Purpose |
|------|---------|
| **Outline** | Jump through headings |
| **Preview** | Render manuscript with formatted citations, **KaTeX** math, **Mermaid** diagrams |
| **Bibliography** | List unresolved or project references |
| **Overview / Dashboard** | Word counts, bibliography size, index status |
| **Problems** | Unresolved citations, orphan bib entries, missing images — click to jump |
| **Citation network** | Which library papers appear in which manuscripts |
| **Gap analysis** | LLM report on themes and gaps in the project bibliography |
| **AI pre-review** | Scores (innovation, evidence, coverage, writing) plus weakness list |

**Editor assist** (needs LLM in Settings; evidence and suggestions need index):

- Hover `[@cite_key]` for details; **F12** jumps to the library entry.
- **Suggested citations** for the current paragraph (after index is built).
- **Cmd+K** custom rewrite; **Cmd+L** ask about selection.
- Right-click: Rewrite, Academic tone, Expand, Shorten, Add citation, Find evidence.
- **Find evidence** groups indexed papers as supporting, contradicting, or neutral for a selected claim.
- **Tab** at paragraph end for ghost-text continuation (accept with Tab).

**Export to Word (.docx):**

- **EndNote mode** — `{Author, Year}` markers for “Update citations” in Word.
- **Static CSL** — in-text and reference list text in your chosen CSL style.
- **RubyCite mode** — Word content controls refreshable via the add-in.
- Optional **`reference.docx`** template for fonts and heading styles (bundled Pandoc).

Export can be blocked when the project scan reports unresolved citation errors (you may override with confirmation).

### Project templates

Start faster with scaffolds:

- **Empty** — metadata only  
- **Paper** — manuscript + figures folder  
- **Review** — survey + themes notes  
- **Grant** — NSFC-style proposal sections (background, gap, question, methods, innovation, plan, budget) + experiment folder  
- **Final report** — closure report structure  

Create a **new folder from template** or **apply a template** to an open workspace.

### Word add-in

- Local **HTTPS** connection to RubyCite on your computer (desktop app must be running).
- Task pane: **search library**, **insert citations**, **format bibliography**.
- One-time **certificate trust** and manifest install from the Tools menu.

### Settings and interface

- **LLM providers**: built-in llama.cpp (local `.gguf`), Ollama, LM Studio, vLLM, OpenAI-compatible APIs (OpenAI, DeepSeek, Groq, OpenRouter, Moonshot, Silicon Flow, Azure, and more).
- **Six interface languages**: English, 中文, 日本語, Français, Español, Deutsch.
- **Color themes**: default, blue light, warm light, blue dark.
- **Crossref** email for DOI metadata enrichment (optional, needs network).

---

## Local-first by design

- Converted Markdown, `library.db`, vector index, RIS export, reviews, and workspace files stay under your **RubyCite data folder** or **workspace folder**.
- AI runs **locally** or through **APIs you configure** — RubyCite does not require a vendor cloud account.
- The Word add-in talks to **localhost only**; it does not upload your library to RubyCite servers.

---

## Before you start

| Requirement | Detail |
|-------------|--------|
| PDFs | Text must be selectable (not scan-only) |
| Index / Citation assist | Build index on selected papers first |
| AI features | Configure an LLM in **Settings → Test connection** |
| Word add-in | Trust certificate; install manifest; keep RubyCite running |
| Network | Only for Crossref, cloud LLMs, or optional model downloads |

For step-by-step use, open **Help → User guide** inside the app.

---

## Learn more

| Resource | |
|----------|--|
| In-app **User guide** | Full manual |
| **About** | Version and legal notices |
| [EULA.md](EULA.md) | License terms |
| [COPYRIGHT.md](COPYRIGHT.md) | Copyright |

**Contact:** [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com)

---

*RubyCite 2.0 — Copyright © 2026 Hongtao Lu. All rights reserved.*
