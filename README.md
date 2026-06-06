[简体中文](./README_zh.md) | English &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Manual](./USAGE.md)                                                   
# ♦️ RubyCite v1.0 Personal Research Data System.

<p align="left">
  <img src="https://img.shields.io/badge/Version-v1.0%20Stable-green?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/Architecture-Local--First-blueviolet?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/Security-100%25%20Offline%20Privacy-success?style=flat-square" alt="Privacy">
  <img src="https://img.shields.io/badge/Platform-macOS%20 or windows X64%20 -blue?style=flat-square" alt="Platform">
</p>

### 💡 Core Pain Points Solved

1. **No More Scrambled PDF Copy-Pasting**: Traditional PDF copying results in broken lines and messy formatting. RubyCite parses original English SCI PDFs into clean, standard **Markdown text** while **automatically extracting standalone tables and high-resolution figures**.
2. **AI Literature Reviews without Hallucinated Citations**: Standard LLMs easily fabricate references. RubyCite allows you to **select specific local papers** to feed into the model, generating rigorous reviews anchored with precise `{Author, Year}` citations.
3. **Seamless EndNote / Zotero Integration**: Paste the AI-generated review into MS Word, click **Export RIS** in RubyCite, and import it into your reference manager. Use `Update Citations` to turn temporary brackets into formal citations instantly.
4. **Absolute Data Sovereignty**: Fully supports embedded local engines (llama.cpp) and Ollama for **100% air-gapped, offline execution**. Keep your novel research hypotheses and confidential drafts entirely on your own machine.

---

### 🛠️ Core Feature Workflow

* **📄 Convert**: Batch-import English PDFs to extract clean Markdown, images, and standard YAML metadata (with automated Crossref enrichment).
* **📊 Analyze**: Generates a 3-card concise `.digest.md` briefing for any single paper, distilling the core scientific problem, methodologies, and system boundaries in 60 seconds.
* **🕸️ Review**: Select multiple papers (Full text or Digests), input your outline prompt, and let the LLM execute a tailored literature review draft with valid citation anchors.
* **💾 Export**: One-click output to standard `library.ris` files for effortless integration with your existing reference database.

---

### ⚡ Project Orientation
RubyCite is an **offline-first data utility designed to streamline the academic workflow**. It is **NOT** a standard AI copywriting or paraphrasing wrapper, but an engineered toolchain built to eliminate the drag of reading, tracking, and citing massive piles of academic PDFs.

