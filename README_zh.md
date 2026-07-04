简体中文 | [English](./README.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
# ♦️ RubyCite  — 科研IDE工作台
<p align="left">
  <img src="https://img.shields.io/badge/版本-v2.0%20Stable-green?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/架构-本地优先%20%7C%20Local--First-blueviolet?style=flat-square" alt="Architecture">
  <img src="https://img.shields.io/badge/安全-100%25%20离线隐私保护-success?style=flat-square" alt="Privacy">
  <img src="https://img.shields.io/badge/平台-macOS%20 或者windows 64位系统%20-blue?style=flat-square" alt="Platform">
</p>

**RubyCite** 是一款面向 **macOS 与 Windows** 的桌面应用，把电脑变成你的**科研IDE工作台**：导入论文、本地阅读与检索、对文库智能问答、带引文写稿，并顺畅对接 Word 与文献管理软件 —— 默认情况下，不必把 PDF 文库交给云端。

转换正文、文献记录、向量索引、笔记与项目稿件都保存在本机。

---

## 适合谁用

RubyCite 面向：

- 需要管理大量**英文期刊 PDF**（及 RIS/BibTeX 题录）做综述、开题、写学位论文的研究者与研究生；
- 希望对自己的文献做**语义检索与问答**，而不是泛泛搜索网络；
- 写稿时需要**按句推荐引文**、快速插入 `{Author, Year}` 标记；
- 用 **Markdown** 写长文，再导出 **Word**，配合 EndNote 风格或 CSL 排版；
- 倾向使用**本地大模型**（内置 llama.cpp 或 Ollama）或**自备 API** 的用户。

---

## 三种用法

### 1. 文库主线 — 导入、建索引、写稿加引文

先建可检索文库，再在外部或本应用内写稿时使用。

```text
导入 PDF 或 RIS / BibTeX / EndNote .enw / Markdown
   → 分组管理；编辑元数据；预览转换正文
   → 勾选文献并建立索引
   → 在 AI 面板提问（可选）
   → 引文辅助：粘贴草稿 → 生成 {Author, Year} 标记
   → 导出 RIS → Word / Zotero / EndNote
```

### 2. 分析副线 — 单篇摘要、多篇综述

```text
导入文献
   → AI Summary：每篇五张结构化卡片 + 个人读书笔记
   → Review assist：勾选多篇 → 生成文献综述
   → 导出 RIS 或复制综述到 Word
```

### 3. 写作工作区 — 在 RubyCite 里完成成稿

打开项目文件夹，像轻量写作 IDE 一样使用：

```text
从模板新建项目（论文 / 综述 / 基金 / 结题报告 / 空白）
   → CodeMirror 编辑 .md；@ 插入引文
   → 大纲、预览、参考文献、概览、问题清单等/workbench 标签
   → 导出 Word（EndNote 临时引文 / 静态 CSL / RubyCite 控件）
   → 可选：Word 插件刷新引文
```

三条路径共用同一套**文库**与**项目参考文献**。

---

## 当前已实现的功能

### 导入与 PDF 转换

- 转换**Born-digital** 期刊 PDF（文字可选中；Elsevier、Springer、IEEE 等版式）。
- 提取**正文、表格、插图**，并处理双栏等阅读顺序。
- 文本过少或扫描版会提示不支持。
- 另支持导入 **RIS、BibTeX、EndNote `.enw`、Markdown**。
- 可**手动新建**文献条目（无需 PDF）。

### 文库与元数据

- 中央**文献表** + **全文检索**（本地数据库）。
- **手动分组**与**智能分组**（如有 PDF、已有 AI 摘要、2020 年及以后等）。
- **元数据编辑**：题名、作者、年份、期刊、DOI、cite key；**Crossref 按 DOI 更新**；**CSTR 校验**。
- **查找并合并重复**文献。
- **论文 Preview**：阅读转换后的 Markdown（标题、表格、图片、参考文献逐条显示）。
- 独立标签：**AI 摘要卡片**、**读书笔记**、**插图列表**、**Metadata / CSL 引文预览**。
- 文献表**右键**：元数据、预览、索引操作、删除。
- **一键复制书目**（GB/T 7714、APA 7、IEEE、著者—出版年）及**导入自定义 CSL 样式**。

### Index / Q&A（索引与问答）

- 使用内置 **multilingual-e5-small** 模型建立**本地向量索引**。
- 自行勾选要索引的文献；Settings 可调**切片大小**（修改后需重建索引）。
- **自然语言提问**；**回答语言跟随提问语言**。
- 可查看索引状态、已索引文件，并**单篇移出索引**。

### Citation assist（引文辅助）

- 粘贴全文草稿，**按句**检索索引。
- 每句最多 **3 条**相关片段；同一篇文献合并为一个 `{Author, Year}`。
- 可查看每句匹配来源；**复制带引文标记的全文**到 Word。
- 需先 **Build index**。

### AI Summary（单篇摘要）

- 生成 **五张 AI 卡片**：科学问题、创新点、核心发现、局限与展望、后续研究方向。
- 保存轻量 **`.digest.md`**，与全文关联；**读书笔记**在单独标签编辑。
- **导出 digest**（如 Obsidian）。
- 可选择 **AI 输出语言**。

### Review assist（综述辅助）

- 勾选文献 → **Feed to model** → 选择模板：**期刊论文 / 学位论文 / 调研报告**。
- 自定义 Review 提示词，在 AI 面板生成长文综述。
- **保存或复制**综述；**导出 RIS**。

### 写作工作区

- **资源管理器**浏览项目目录；新建文件/文件夹；多标签编辑稿件。
- **CodeMirror 6** Markdown 编辑器（语法高亮）。
- 侧栏 **PROJECT BIBLIOGRAPHY（项目参考文献）**，把文库文献挂到当前项目。
- 同一文档支持 **`[@cite_key]`** 与 **`{Author, Year}`** 两种引文写法。
- 输入 **`@`** 检索文库并插入 cite key。

**当前稿件可用的工作台标签：**

| 标签 | 作用 |
|------|------|
| **Outline（大纲）** | 按标题跳转 |
| **Preview（预览）** | 渲染稿件；**KaTeX** 公式、**Mermaid** 图；引文经 CSL 引擎预格式化 |
| **Bibliography** | 未解析引文、项目书目检查 |
| **Overview（项目概览）** | 稿件字数、书目规模、索引状态等 |
| **Problems（问题）** | 未解析引文、孤立书目项、缺失图片 — 可点击定位 |
| **Citation network** | 各稿件引用了哪些文库文献 |
| **Gap analysis（缺口分析）** | 对项目书目做主题与覆盖缺口分析 |
| **AI pre-review（AI 预评审）** | 创新/证据/覆盖/写作等维度评分 + 问题清单 |

**编辑器辅助**（需 Settings 配置 LLM；证据与段落建议需已建索引）：

- 悬停 `[@cite_key]` 查看信息；**F12** 跳转文库条目。
- 当前段落 **Suggested citations**（需索引）。
- **Cmd+K** 按指令改写；**Cmd+L** 对选区提问。
- 右键：改写、学术化、扩写、缩写、添加引文、**Find evidence（找证据）**。
- **找证据**：将索引文献分为支持、矛盾、中性/相关。
- 段末停笔后出现 **Tab 续写** 灰色建议，**Tab** 接受。

**导出 Word（.docx）：**

- **EndNote 模式** — `{Author, Year}`，供 Word「更新引文」。
- **Static CSL** — 按所选 CSL 样式输出文中与文末参考文献。
- **RubyCite 模式** — Word 内容控件，可用插件刷新。
- 可选工作区 **`reference.docx`** 控制字体与标题样式（内置 Pandoc 转换）。

项目扫描存在**未解析引文**时，导出可能被拦截（确认后可继续）。

### 项目模板

- **空白** — 仅项目元数据  
- **论文（paper）** — 稿件 + 图片目录  
- **综述（review）** — 综述稿 + 主题笔记  
- **基金（grant）** — 背景、缺口、科学问题、方法、创新、计划、预算等章节 + 实验目录  
- **结题报告（final_report）** — 结题报告结构  

支持**从模板新建文件夹**，或对已打开工作区**套用模板**。

### Word 插件

- 通过本机 **HTTPS** 连接 RubyCite（需保持桌面端运行）。
- 任务窗格：**检索文库、插入引文、格式化参考文献**。
- 在 **Tools** 菜单完成**证书信任**与**安装 manifest**。

### 设置与界面

- **LLM**：内置 llama.cpp（本地 `.gguf`）、Ollama、LM Studio、vLLM、OpenAI 兼容 API（OpenAI、DeepSeek、Groq、OpenRouter、Moonshot、SiliconFlow、Azure 等）。
- **六种界面语言**：English、中文、日本語、Français、Español、Deutsch。
- **四套主题**：默认、蓝色浅色、暖色浅色、蓝色深色。
- **Crossref** 邮箱用于 DOI 元数据补全（可选，需联网）。

---

## 本地优先

- 转换 Markdown、`library.db`、向量索引、RIS、综述与工作区文件均在**本机数据目录或工作区目录**。
- AI 可完全**本地运行**，或通过**你配置的 API** 调用 — 不强制绑定厂商云账号。
- Word 插件仅访问 **localhost**，不上传文库到 RubyCite 服务器。

---

## 使用前请知悉

| 条件 | 说明 |
|------|------|
| PDF | 需能选中复制文字（非纯扫描） |
| 索引 / 引文辅助 | 须先对目标文献 **Build index** |
| AI 功能 | 在 **Settings** 配置 LLM 并 **Test connection** |
| Word 插件 | 信任证书、安装插件、保持 RubyCite 运行 |
| 网络 | 仅 Crossref、云端 LLM 或模型下载时需要 |

详细操作见应用内 **Help → User guide（用户指南）**。

---

## 延伸阅读

| 资源 | |
|------|--|
| 应用内 **用户指南** | 完整手册 |
| **About** | 版本与法律声明 |
| [EULA.md](EULA.md) | 许可协议 |
| [COPYRIGHT.md](COPYRIGHT.md) | 版权说明 |

**联系：** [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com)

---

*RubyCite 2.0 — Copyright © 2026 Hongtao Lu. All rights reserved.*


