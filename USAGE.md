[简体中文](./USAGE_zh.md) | English
# 💎 RubyCite v1.0 User Manual

This manual provides a detailed walkthrough for configuring, parsing, evaluating, and synthesizing academic literature inside RubyCite v1.0, culminating in a closed-loop integration with Zotero and EndNote.

---

## 🛠️ Step 1: Base Configuration (Settings)

Before importing literature, establish your foundational language model infrastructure. RubyCite operates on a **local-first** paradigm while allowing flexible cloud scaling.

### 1. Initialize LLM Backend Connection
Navigate to the **Settings** tab on the left sidebar and select an engine based on your computational resources:
* **Option A: RubyCite Built-in Engine**
    * **Action**: Place your pre-downloaded, standard `.gguf` model files directly into the application's local `models/` directory.
    * **Use Case**: Best for 100% air-gapped, offline operations where complete data sovereignty and privacy are mandatory.
* **Option B: Ollama Service Gateway**
    * **Action**: Run `ollama serve` in your system terminal. Enter your local gateway address (default: `http://localhost:11434`) and select your target model (e.g., `qwen2.5-coder:32b` or your cloud pointer `qwen3-coder-next:cloud`).
* **Option C: Cloud API Endpoints**
    * **Action**: Select OpenAI, DeepSeek, or other OpenAI-compatible upstream providers. Supply your custom API Base URL and Secret Key.

### 2. Connectivity Benchmarking & Persistence
* Click **Test Connection** to ensure a successful handshake with the local IPC channel or remote server.
* Select your preferred **UI/Review Language** (English/Chinese).
* (Optional) Toggle the **Crossref Metadata Enrichment** switch. When a valid DOI is detected, the system automatically fetches authenticated bibliographic metadata in the background.
* Click **Save Settings** to persist configurations.

---

## 📄 Step 2: Pipeline PDF Processing (Convert)

Deconstruct noisy, heavily formatted PDF layouts into structured, highly readable Markdown data assets.

### 1. Ingest Raw PDF Literature
* Head to the **Convert** tab and click **Select PDFs…**.
* Choose one or multiple original **English SCI journal PDFs** (Note: Text must be selectable and vector-based; scanned image-only PDFs yield poor results).

### 2. Output Inspection & Asset Validation
Once parsing is complete, click a record in the left sidebar list. The main panel displays the extracted components saved onto your local storage:
* **Overview Pane**: Displays extracted Title, Authors, Journal, Year, and DOI. You can manually edit these or hit "Crossref" to force re-fetch.
* **Main Canvas**: A clean Markdown rendering of the paper text with layout artifacts, line breaks, and multi-column distortions entirely removed.
* **Asset Panel (Right)**: High-resolution images, charts, and vector tables isolated and extracted directly from the physical PDF rendering layers.

> 💾 **Underlying Storage Schema**
> Each successful conversion generates a standardized directory architecture on disk:
> * `markdown/{Paper_Name}.md`: Complete text output wrapped in standard YAML front-matter headers.
> * `markdown_assets/{Paper_Name}/`: Directory containing isolated image files, independent figures, and data tables.
> * `pdfs/`: Local archival duplicates of your imported source files.

---

## 📊 Step 3: Molecular Literature Distillation (Analyze)

Compress extensive research articles into high-density structural element cards before reading.

### 1. Trigger Dimensionality Reduction
* Open the **Analyze** tab and select the target **Full `.md` file** from the left list (Do not select files carrying the `.digest.md` extension at this step).
* Click **Generate cards**.

### 2. Card Review & Annotation Logging
The system processes the text profile using an absolute minimum token overhead, yielding 3 specialized summary dimensions:
* **Card 1: Executive Summary**
* **Card 2: Targeted Scientific Problems & Methodological Tags**
* **Card 3: Material / Boundary Systems**

Use the **My notes** canvas in the bottom right to pin down personal insights or advisor feedback, then click **Save notes**.

> 💾 **Underlying Storage Schema**
> The engine creates a lightweight companion file named `{Paper_Name}.digest.md` under the `/markdown/` directory. This file stores only the core YAML metadata, the 3 AI-generated elements, and your personal annotations. The original long-form text is completely stripped out to optimize token efficiency for synthesis workflows.

---

## 🕸️ Step 4: Zero-Hallucination Review Synthesis (Review)

Synthesize evidence-based literature review drafts strictly bounded by your private repository, complete with valid inline citation strings.

### 1. Bound Your Grounded Context (Select Ingestion Strategy)
Navigate to the **Review** tab. Depending on the scale and scope of your document, tick the corresponding nodes in the left file tree:
* **Strategy A: Full-Text Ingestion (Full .md)**
    * **Operational Guardrail**: Select the raw, un-suffixed Markdown files. To prevent context drift or model attention fatigue, **it is highly recommended to limit full-text ingestion to under 20 papers**.
    * **Best For**: Section-specific progress updates, mini-reviews, or granular technical method comparisons.
* **Strategy B: Element-Card Ingestion (.digest.md)**
    * **Operational Guardrail**: Select the condensed `.digest.md` files processed through the Step 3 pipeline.
    * **Best For**: **Writing doctoral dissertations, master's theses, or comprehensive grant proposals requiring 100+ references**. Feeding structural cards avoids exceeding LLM context window limits while allowing the model to perform highly accurate cross-sectional synthesis across massive archives.

After selection, click **Feed to model** to secure these items as the exclusive knowledge context for your query.

### 2. Engineer the Synthesis Prompt
* Type your precise structural requirements into the **Review prompt** area.
    * *Example Prompt: Trace the technological evolution of Volatile Organic Compound (VOC) abatement methods from the provided context. Focus specifically on comparing Catalytic Oxidation vs. Regenerative Thermal Oxidizers (RTO) regarding space velocity constraints and thermal energy efficiency.*

### 3. Generate Drafts with Anchored Citations
* Click **Generate review**.
* **Anti-Hallucination Lock**: The system confines the LLM's logical boundary to your checked items. The model is physically blocked from parsing external web data or fabricating non-existent references.
* The output incorporates temporary inline citation strings structured as **`{Author, Year}`** (e.g., `...however, thermal catalyst deactivation occurs under elevated space velocities {Smith, 2023}.`). Click to copy or export.

---

## 💾 Step 5: Legacy Ecosystem Integration (Export RIS)

Translate raw review text into formally formatted, journal-ready citations inside Microsoft Word or WPS.

### 1. Export Standard Bibliographic Database
* Under the **Review** interface, click **Export RIS…**.
* The application iterates through the metadata records of all selected items from your session and compiles them into a single `library.ris` bibliography file (The system automatically cross-references a `.digest.md` file back to its full metadata profile).

### 2. Reference Manager Synchronization & Word Document Refresh
1. Open your desktop reference manager (**Zotero** or **EndNote**) and drag-and-drop the generated `.ris` file into your collection.
2. Paste the generated review text from RubyCite into your **Microsoft Word** or **WPS** draft.
3. Ensure the Zotero/EndNote word processor integration plugin is active. Click **Update Citations** or **Bibliography Refresh** on your word processor toolbar.
4. Your reference manager will scan the text, intercept the `{Author, Year}` temporary brackets (e.g., `{Smith, 2023}`), verify them against the imported RIS database, convert them into your target journal style (e.g., superscript `[1]`), and instantly format your bibliography index at the end of the file.

---

## 📂 Local Storage Infrastructure (Data Path)

To simplify incremental backups, versioning, and local synchronization using tools like Syncthing or Git, RubyCite maintains a clean, transparent storage presence on your file system.

On macOS production setups, click **Open data folder** to trigger Finder, or navigate directly to:
`~/Library/Application Support/RubyCite/`

### Directory Layout & Maintenance Index:
* `/markdown/`: Contains full converted text papers and paired `.digest.md` element cards.
* `/markdown_assets/`: Stores raw extracted vector images, data diagrams, and chart outputs.
* `/pdfs/`: Local mirror repository storing original PDF documents.
* `/models/`: Target directory for storing offline `.gguf` models used by the native llama.cpp instance.
* `library.ris`: Globally maintained local bibliography tracking index.
* `settings.json`: Configuration file storing encrypted provider strings, gateway paths, and user localizations.

---

## ❓ Troubleshooting (FAQ)

* **Q: PDF text parsing failed or outputted unreadable text blocks?**
    * **A**: Ensure the source document is a native digital PDF straight from the publisher, where text layers can be selected via mouse cursor. Flattened scans, print-to-PDF items, or documents heavily embedded with opaque, intrusive text watermarks drastically degrade parsing pipeline fidelity.
* **Q: The engine claims the LLM is offline during Analyze or Review steps?**
    * **A**: Double-check your active configuration under Settings. If utilizing Ollama, make sure the system terminal process `ollama serve` is actively listening and not blocked by regional firewall policies. If running the built-in option, confirm that your weights in `/models/` feature a verified `.gguf` file extension.
* **Q: Can the pipeline parse Chinese academic literature PDFs?**
    * **A**: The current v1.0 pipeline, metadata regex parser, and automated Crossref parsing rules are explicitly optimized for **English SCI Journal PDFs**. Processing Chinese language journals under this version is officially unsupported and will result in metadata failure.
