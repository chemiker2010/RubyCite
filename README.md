[简体中文](./README_zh.md) | English
# RubyCite
RubyCite is a desktop literature tool for researchers, focused on born-digital English journal PDFs. It connects reading, note-taking, review writing, and citation management in one local workflow.
**RubyCite** is a desktop literature tool for researchers, focused on **born-digital English journal PDFs**. It connects reading, note-taking, review writing, and citation management in one local workflow.

**In one line:** PDF → Markdown (with figures) → per-paper AI summary cards → multi-paper literature review + RIS export

---

## Key Features

| Feature | Description |
|---------|-------------|
| **Structured PDF conversion** | Turn selectable English journal PDFs into Markdown with body text, tables, and figures |
| **Smart metadata** | Auto-detect DOI, authors, journal, etc.; optional Crossref enrichment (network required) |
| **Single-paper AI analysis** | Generate three summary cards per paper and save a lightweight digest note |
| **Multi-paper reviews** | Select several papers and generate a literature review with `{Author, Year}` citations |
| **Reference management** | Export RIS for EndNote, Zotero, and Word citation updates |
| **Flexible LLM backends** | Built-in llama.cpp, Ollama, LM Studio, OpenAI-compatible cloud APIs, and more |
| **Local-first** | Papers, Markdown, notes, and RIS stay on your machine |

## Who It’s For

- Researchers who read many English journal PDFs and want editable Markdown notes
- Students and scientists writing **literature review** chapters
- Anyone who wants AI-assisted reading with EndNote/Zotero-compatible citations
- Users who prefer offline or self-hosted models (Ollama, bundled GGUF, etc.)

## System Requirements

- **macOS** (Apple Silicon preferred; see your build/installer for details)
- Publisher PDFs with **selectable text** (scanned PDFs are poorly supported)
- An LLM configured for Analyze and Review (local or cloud)
- Network for Crossref enrichment and cloud APIs

---

## UI Overview

| Tab | Purpose |
|-----|---------|
| **Convert** | Import PDFs and convert to Markdown |
| **Analyze** | AI summary cards for one paper |
| **Review** | Multi-paper literature review |
| **Settings** | LLM, language, Crossref options |
| **About** | Version and copyright |

The left sidebar lists papers; the center panel is the main workspace; the right panel shows figures and bibliographic metadata.

---

## Recommended Workflow

```
① Convert — import PDFs
      ↓
② Check metadata & figures (right panel)
      ↓
③ Analyze — generate summary cards
      ↓
④ Review — select papers → Feed to model → prompt → Generate review
      ↓
⑤ Export RIS → import into EndNote/Zotero → Update Citations in Word
```

---

## Step-by-Step Guide

### 1. Configure the LLM (Settings)

1. Open **Settings**
2. Choose an **LLM provider**, for example:
   - **RubyCite built-in (llama.cpp)** — place `.gguf` files in the `models/` folder
   - **Ollama** — run `ollama serve` locally
   - **OpenAI / DeepSeek / …** — set API base URL and key
3. Pick a **model** and click **Test connection**
4. Set **Review language** (English or Chinese for UI and review output)
5. Click **Save settings**

Optional: enable **Crossref metadata enrichment** to fill author, title, and journal from DOI.

### 2. Convert — Import PDFs

1. Go to **Convert** and click **Select PDFs…**
2. Choose one or more English journal PDFs and wait for conversion
3. Select a paper in the sidebar to preview Markdown and extracted figures
4. Use **Overview** on the right to view or edit title, authors, DOI, journal, etc.

**Outputs:**

| Path | Contents |
|------|----------|
| `markdown/{paper}.md` | Full Markdown (body, figures, YAML front matter) |
| `markdown_assets/{paper}/` | Extracted images |
| `pdfs/` | Copied source PDFs |

### 3. Analyze — Single-Paper AI Summary

1. Open **Analyze** and select a **full `.md` file** (not `.digest.md`)
2. Click **Generate cards**
3. Read the three AI cards; add **My notes** and **Save notes**

Output: `{paper}.digest.md` — YAML, three cards, and your notes only (no full body or figures).

### 4. Review — Multi-Paper Literature Review

1. Open **Review** and check papers in the left sidebar (digest or full)
2. Click **Feed to model**
3. Write your **Review prompt**
4. Click **Generate review**, then copy or save the result

The review uses temporary `{Author, Year}` citations (e.g. `{Smith, 2023}`).

### 5. Export RIS — EndNote / Zotero

1. Click **Export RIS…** in the Review sidebar
2. Import the `.ris` file into EndNote or Zotero
3. Paste the review into Word and run **Update Citations**

RIS entries are built from **full `.md` metadata**. If you selected a digest, RubyCite maps it to the corresponding full paper entry.

---

## Data Locations

In development, data usually lives in the project root. Installed builds typically use:

`~/Library/Application Support/RubyCite/`

| Path | Contents |
|------|----------|
| `markdown/` | Converted Markdown |
| `markdown_assets/` | Extracted figures |
| `pdfs/` | Source PDFs |
| `models/` | Local `.gguf` models |
| `library.ris` | Reference library |
| `review.md` | Last generated review |
| `settings.json` | App settings |

Use **Open data folder** in the sidebar to open the data directory quickly.

---

## FAQ

**Conversion fails or text is garbled?**  
Use publisher PDFs with selectable text. “Print to PDF” from HTML or pure scans are not supported well.

**Analyze / Review says LLM offline?**  
Check Settings → provider and model. For local models, ensure Ollama is running or built-in llama has `bin/llama-server` and a `.gguf` in `models/`.

**Wrong DOI or authors?**  
Edit metadata in the right **Overview** panel; refresh from DOI via Crossref when available.

**Digest vs full Markdown?**  
Full `.md` has the complete paper and figures. `.digest.md` has AI cards and your notes — lighter and good for Review input.

**Chinese PDFs?**  
RubyCite v1 targets **English journal PDFs**; Chinese support is limited.
