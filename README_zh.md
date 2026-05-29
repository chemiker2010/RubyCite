**RubyCite** 是一款面向科研工作者的桌面文献工具，专注于 **英文 SCI 期刊 PDF** 的阅读、整理与写作辅助。它将「读论文 → 记笔记 → 写综述 → 管理引用」串联成一条清晰的工作流，数据保存在本机。

**一句话概括：** PDF → Markdown（含图表）→ 单篇 AI 摘要卡片 → 多篇综述 + RIS 导出

---

## 主要特点

| 特点 | 说明 |
|------|------|
| **PDF 结构化转换** | 将可复制的英文期刊 PDF 转为 Markdown，提取正文、表格与插图 |
| **智能元数据** | 自动识别 DOI、作者、期刊等信息；可通过 Crossref 补全（需联网） |
| **单篇 AI 分析** | 对每篇论文生成 3 张摘要卡片，并保存为轻量 digest 笔记 |
| **多篇文献综述** | 勾选多篇文献，由 AI 生成带 `{作者, 年份}` 引文格式的综述 |
| **参考文献管理** | 导出 RIS，可导入 EndNote、Zotero，便于在 Word 中更新引文 |
| **灵活 LLM 接入** | 支持内置本地模型（llama.cpp）、Ollama、LM Studio 及 OpenAI 等云端 API |
| **本地优先** | 论文、Markdown、笔记、RIS 均存储在本机 |

## 适用场景

- 阅读大量英文期刊 PDF，需要可编辑、可检索的 Markdown 笔记
- 撰写学位论文、项目报告中的 **文献综述** 章节
- 希望 AI 辅助读论文，且引文格式与 EndNote/Zotero 兼容
- 需要离线或使用自托管大模型（Ollama、内置 GGUF 等）

## 系统要求

- **macOS**（Apple Silicon 优先；具体以安装包为准）
- 出版社原版 PDF，文字 **可选中**（扫描版效果有限）
- 使用 AI 功能时需配置 LLM（本地或云端）
- Crossref 元数据补全、云端 API 需 **网络**

---

## 界面概览

| 标签页 | 功能 |
|--------|------|
| **Convert** | 导入 PDF，转换为 Markdown |
| **Analyze** | 对单篇文献生成 AI 摘要卡片 |
| **Review** | 多篇文献综述生成 |
| **Settings** | LLM、语言、Crossref 等设置 |
| **About** | 版本与版权信息 |

左侧为导航与文献列表，中间为主工作区，右侧为图表预览与元数据编辑。

---

## 推荐工作流

```
① Convert 导入 PDF
      ↓
② 检查元数据 / 图表（右侧面板）
      ↓
③ Analyze 生成单篇摘要卡片
      ↓
④ Review 勾选多篇 → 投喂 → 写提示词 → 生成综述
      ↓
⑤ 导出 RIS → 导入 EndNote/Zotero → Word 更新引文
```

---

## 分步使用说明

### 1. 配置 LLM（Settings）

1. 打开 **Settings（设置）**
2. 选择 **LLM 提供商**，例如：
   - **RubyCite built-in (llama.cpp)**：将 `.gguf` 模型放入 `models/` 文件夹
   - **Ollama**：本地运行 `ollama serve`
   - **OpenAI / DeepSeek 等**：填写 API 地址与密钥
3. 选择模型，点击 **测试连接**
4. 设置 **界面 / 综述语言**（中文或英文）
5. 点击 **保存设置**

可选：开启 **Crossref 元数据补全**，有 DOI 时自动补全作者、标题、期刊。

### 2. Convert — 导入 PDF

1. 进入 **Convert**，点击 **Select PDFs…**
2. 选择一个或多个英文期刊 PDF，等待转换
3. 在左侧列表点击文献，预览 Markdown 与右侧插图
4. 在 **Overview** 查看或编辑标题、作者、DOI、期刊等

**输出：**

| 路径 | 内容 |
|------|------|
| `markdown/{论文名}.md` | 完整 Markdown（正文 + 图表 + YAML） |
| `markdown_assets/{论文名}/` | 提取的图片 |
| `pdfs/` | 原始 PDF 副本 |

### 3. Analyze — 单篇 AI 摘要

1. 进入 **Analyze**，选择一篇 **完整 `.md`**（不要选 `.digest.md`）
2. 点击 **Generate cards**
3. 查看 3 张 AI 摘要卡片，在 **My notes** 中写阅读笔记并 **Save notes**

输出为 `{论文名}.digest.md`：YAML + 3 张卡片 + 你的笔记，不含全文图表。

### 4. Review — 多篇文献综述

1. 进入 **Review**，在左侧勾选要纳入的文献（digest 或 full 均可）
2. 点击 **Feed to model**
3. 在 **Review prompt** 中写综述要求
4. 点击 **Generate review**，可复制或保存结果

综述正文使用 `{Author, Year}` 临时引文（如 `{Smith, 2023}`）。

### 5. Export RIS — 对接 EndNote / Zotero

1. 在 Review 侧栏点击 **Export RIS…**
2. 将 `.ris` 导入 EndNote 或 Zotero
3. 把综述粘贴到 Word，使用 **Update Citations** 更新引文

RIS 基于 **完整 `.md` 的元数据**；若勾选 digest，会自动关联到对应全文条目。

---

## 数据存储位置

开发模式下数据一般在项目根目录；安装版通常在：

`~/Library/Application Support/RubyCite/`

| 目录/文件 | 内容 |
|-----------|------|
| `markdown/` | 转换后的 Markdown |
| `markdown_assets/` | 提取的图片 |
| `pdfs/` | 原始 PDF |
| `models/` | 本地 `.gguf` 模型 |
| `library.ris` | 参考文献库 |
| `review.md` | 最近生成的综述 |
| `settings.json` | 应用设置 |

侧栏 **Open data folder** 可快速打开数据目录。

---

## 常见问题

**PDF 转换失败或乱码？**  
请使用出版社原版 PDF（文字可选中）。HTML 另存为 PDF、纯扫描件通常不支持。

**Analyze / Review 提示 LLM 离线？**  
到 Settings 检查提供商与模型；本地模型需确保 Ollama 已启动，或内置 llama 的 `bin/llama-server` 与 `.gguf` 已就绪。

**DOI 或作者识别不准？**  
可在右侧 Overview 手动修改；有 DOI 时可尝试 Crossref 刷新。

**digest 和 full 有什么区别？**  
`full .md` 含完整正文与图表；`.digest.md` 是 AI 卡片 + 你的笔记，适合快速回顾和投喂 Review。

**能否处理中文 PDF？**  
当前版本面向 **英文期刊 PDF**，中文支持有限。



