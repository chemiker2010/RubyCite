简体中文 | [English](./README.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[使用说明](./USAGE_zh.md)  
# ♦️ RubyCite  — 个人科研数据系统
<p align="left">
  <img src="https://img.shields.io/badge/版本-v1.2.1%20Stable-green?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/架构-本地优先%20%7C%20Local--First-blueviolet?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/安全-100%25%20离线隐私保护-success?style=flat-square" alt="Privacy">
  <img src="https://img.shields.io/badge/平台-macOS%20 或者windows 64位系统%20-blue?style=flat-square" alt="Platform">
</p>

### 💡 解决的核心问题

1. **告别 PDF 乱码与排版折磨**：直接复制 PDF 经常带有恶心的断行和乱码。RubyCite 将英文 SCI 原版 PDF 完美转换为干净的 **Markdown 正文**，并**自动剥离提取出论文中的核心表格与插图**。
2. **杜绝AI幻觉**：普通 AI 写文献综述会凭空捏造参考文献。RubyCite 支持**勾选多篇本地文献**投喂，由 AI 严格基于你的文献库生成带 `{作者, 年份}` 标准格式的综述。
3. **完美对接 Zotero / EndNote**：生成的综述可直接复制到 Word，一键**导出标准 RIS 参考文献库文件**，导入文献管理软件后即可通过 Word 的 `Update Citations` 直接将临时引文无缝转为正式引用。
4. **数据保护与隐私**：支持内置本地模型（llama.cpp）与 Ollama，**100% 物理断网运行**。学术选题创意和未发表的论文资产绝不上云，死守隐私红线。

---

### 🛠️ 核心功能工作流

* **📄 转换 (无损脱水)**：批量导入英文 PDF，一键提取出纯文本 Markdown、元数据（自动通过 Crossref 补全）以及论文插图。
* **📊 分析 (单篇速读)**：AI 自动为单篇论文生成 3 张轻量化摘要卡片（`.digest.md`），帮你 1 分钟看清科学问题、方法和实验系统，并支持随时追加个人阅读笔记。
* **🕸️ 综述 (多篇综述)**：勾选多篇文献（Full 或 Digest），输入你的综述要求，AI 自动产出严谨、带有引文锚点的学术综述正文。
* **💾 导出 (文献联动)**：一键导出应用内生成的 `library.ris`，完美对接你现有的传统文献管理工具。

---

### ⚡ 工具定位
本项目是一个**运行在本地的、可断网的科研文献资产高能转化工具**。它**不是**普通的 AI 语言润色工具，而是专门用来解决科研人员“读论文慢、提取插图繁琐、写综述引文对齐痛苦”的硬核生产力工具。
