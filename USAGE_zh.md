简体中文| [English](./USAGE.md) 
# 💎 RubyCite Pro v1.2 使用说明书

本文档面向 **RubyCite Pro** 的中文用户，提供从安装、配置到日常使用的完整指南。

---

## 目录
- [RubyCite Pro 使用帮助文档](#rubycite-pro-使用帮助文档)
  - [目录](#目录)
  - [系统要求](#系统要求)
  - [安装与启动](#安装与启动)
  - [界面概览](#界面概览)
  - [核心工作流](#核心工作流)
    - [主线：索引 → 问答 → 引文](#主线索引--问答--引文)
    - [副线：分析 → 综述](#副线分析--综述)
  - [功能详解](#功能详解)
    - [Convert（转换）](#convert转换)
    - [Index / Q\&A（索引 / 问答）](#index--qa索引--问答)
    - [Analyze（分析）](#analyze分析)
    - [Review assist（综述辅助）](#review-assist综述辅助)
    - [Citation assist（引文辅助）](#citation-assist引文辅助)
    - [Settings（设置）](#settings设置)
  - [常见问题 FAQ](#常见问题-faq)
  - [数据存储位置](#数据存储位置)
  - [技术支持与反馈](#技术支持与反馈)

---

## 系统要求
| 平台 | 要求 |
|------|------|
| macOS | Apple Silicon 优先，Intel 亦可（需安装对应的 `rust` 编译链） |
| Windows | Windows 10/11（使用官方安装包） |

* 需要 **可选中文字的 PDF**（扫描版可能识别不完整）
* 若使用 AI 功能，请确保已配置 LLM（本地模型或云端 API）
* 索引与向量化使用内置 `multilingual-e5-small` 模型，网络环境仅在使用 Crossref 补全或云端 LLM 时必需。

---

## 安装与启动
1. **下载**：从 GitHub Release 页面获取对应平台的安装包。
2. **解压/安装**：macOS 双击 `.dmg`，Windows 双击 `.exe`。
3. **启动**：双击桌面图标。
4. **首次运行**：软件会在 `~/Library/Application Support/RubyCite/`（macOS）或 `%APPDATA%\RubyCite\`（Windows）创建数据目录。

---

## 界面概览
![](ui/app-icon.png)（左上角图标）

| 区域 | 功能 |
|------|------|
| **顶部栏** | 语言切换按钮、全局操作按钮 |
| **左侧活动栏** | 7 个标签页：Convert、Index / Q&A、Analyze、Review assist、Citation assist、Settings、About |
| **主工作区** | 根据当前标签页显示文献列表、Markdown 编辑区或 AI 结果 |
| **右侧面板** | Convert/Review 时显示插图与元数据；Index / Q&A 时显示索引统计 |

界面采用 **Codicons** 图标库，支持深色主题，语言可在 Settings 中切换（中/英）。

---

## 核心工作流
软件提供两条主线工作流，用户可根据需求单独使用或组合使用。

### 主线：索引 → 问答 → 引文
```text
① Convert 导入 PDF 或 Markdown
   ↓
② Index / Q&A 勾选文献 → Build index（建立向量索引）
   ↓
③ 向文库提问（可选）
   ↓
④ Citation assist 输入草稿 → 自动添加 `{Author, Year}` 引文
   ↓
⑤ Export RIS → 导入 EndNote / Zotero → Word 更新引文
```

### 副线：分析 → 综述
```text
① Convert 导入文献
   ↓
② Analyze 生成单篇摘要卡片（.digest.md）
   ↓
③ Review assist 勾选多篇 → 生成综述文稿
   ↓
④ Export RIS → Word 更新引文
```

---

## 功能详解

### Convert（转换）
* **Select PDFs…** 或 **Import Markdown…** 导入文献。
* 支持 PDF → Markdown 转换，自动提取正文、表格、图片。
* 转换后文件保存在 `markdown/` 目录，可在左侧列表预览。

### Index / Q&A（索引 / 问答）
1. 在左侧勾选需要建立索引的 `.md`（不包括 `.digest.md`）。
2. 点击 **Build index**，后台使用 `multilingual-e5-small` 生成向量索引。
3. 在右侧输入问题，点击 **Ask**，AI 将基于向量检索给出答案，回答语言随提问语言自动切换。

### Analyze（分析）
* 选中单篇 Markdown，点击 **Generate cards**，生成包含 **科学问题、创新点、核心发现** 的 AI 摘要卡片（`.digest.md`）。
* 可在卡片中手动添加笔记，点击 **Save notes** 保存。

### Review assist（综述辅助）
1. 勾选多篇文献 → **Feed to model**。
2. 编写 **Review prompt**（可指定输出语言）。
3. 点击 **Generate review**，生成综述草稿并可导出为 RIS。

### Citation assist（引文辅助）
1. 在左侧输入或粘贴完整草稿。
2. 点击 **添加引文**，系统按句检索文库并在右侧显示带 `{Author, Year}` 的全文。
3. 复制带标记的全文粘贴到 Word，使用 **Export RIS** 导入 EndNote/Zotero，随后在 Word 中更新引用。

### Settings（设置）
* **LLM 提供商**：内置 llama.cpp、Ollama、LM Studio 或 OpenAI 兼容 API。
* **模型**：选择模型并 **测试连接**。
* **界面语言**、**切片大小**（索引用），修改后需重新 **Build index**。
* 其他选项：网络代理、日志级别等。

---

## 常见问题 FAQ
1. **引文辅助没有匹配？**
   - 请先在 **Index / Q&A** 中完成 **Build index**，确保草稿句子与库内文献主题相关。
2. **索引 / 问答的回答语言为何不随界面语言变化？**
   - 回答语言跟随提问语言，与 UI 语言设置无关。
3. **修改切片大小后需要做什么？**
   - 在 **Settings** 中修改后，必须重新 **Build index** 才会生效。
4. **PDF 转换失败怎么办？**
   - 确认 PDF 为可选中文本的出版社原版，扫描版识别率低。
5. **digest 与 full 的区别？**
   - `full .md` 包含完整正文；`.digest.md` 为 AI 生成的摘要卡片，仅用于 Review，不参与索引。

---

## 数据存储位置
| 目录/文件 | 内容 |
|-----------|------|
| `markdown/` | 转换后的 Markdown |
| `markdown_assets/` | 提取的图片 |
| `pdfs/` | 原始 PDF |
| `models/` | 本地 `.gguf` 模型 |
| `embedmodels/` | 嵌入模型（索引用） |
| `cite_index.db` | 向量引文索引库 |
| `library.json` / `library.ris` | 文库与 RIS |
| `review.md` | 最近生成的综述 |
| `settings.json` | 应用设置 |

在 UI 中可通过 **Settings → Open data folder** 快速打开该目录。

---

## 技术支持与反馈
* **问题反馈**：发送邮件至 [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com)。
* **开源仓库**：<https://github.com/chemiker2010/RubyCite>（欢迎提交 Issue 与 PR）。

---

祝您使用愉快！如有任何疑问，请随时联系我们。
