# Copyright Notice / 版权声明

## English

**RubyCite v1.0** (Tauri desktop application and related original materials in this repository) is an **original work** by Hongtao Lu.

**Copyright © 2026 Hongtao Lu. All rights reserved.**

RubyCite is a literature workflow tool for born-digital **English journal PDFs**: conversion to Markdown (with extracted figures), single-paper AI summary cards, multi-paper literature reviews, and RIS export for reference managers.

Hongtao Lu is the individual copyright owner of the original application source code, user interface, documentation, and project-specific assets (excluding third-party components listed below).

**The original source code is proprietary.** It is **not** open source. No license is granted to use, copy, modify, or distribute the source code except under a **separate written license agreement** with Hongtao Lu. See [LICENSE](LICENSE).

Use of compiled application binaries (e.g. macOS `.dmg`, `.app`, or other release builds) is permitted only under the terms of your paid license or evaluation agreement with Hongtao Lu, unless otherwise agreed in writing.

### Third-party and bundled components

The following are **not** covered by the proprietary license above and remain subject to their own terms:

| Component | Location / notes |
|-----------|------------------|
| Rust open-source dependencies | See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and `Cargo.lock` |
| **Pdfium** (`libpdfium.dylib`) | Bundled under `bin/` for PDF rendering |
| **llama.cpp** (`llama-server` and related `.dylib` files) | Bundled under `bin/` when built-in local inference is enabled |
| **User-supplied GGUF models** | Placed by the user in `models/` (or app data directory); upstream model licenses apply |
| **User data** | Converted Markdown, PDFs, RIS, reviews, and settings created while using the app |

For licensing inquiries, contact: **Hongtao Lu** — [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com)

---

## 中文

**RubyCite v1.0**（本仓库中的 Tauri 桌面应用程序及相关原创材料）为 Hongtao Lu 的**原创作品**。

**版权所有 © 2026 Hongtao Lu。保留一切权利。**

RubyCite 面向可复制的**英文 SCI 期刊 PDF**，提供：PDF 转 Markdown（含插图提取）、单篇 AI 摘要卡片、多篇文献综述，以及供 EndNote / Zotero 等使用的 RIS 导出。

Hongtao Lu 为本项目原创应用程序源代码、用户界面、文档及项目专有资源（不含下列第三方组件）的著作权人。

**原创源代码为专有软件，并非开源软件。** 除与 Hongtao Lu **另行签订书面授权协议**外，不授予任何人使用、复制、修改或分发源代码的权利。详见 [LICENSE](LICENSE)。

编译后的应用程序（如 macOS `.dmg`、`.app` 或其他发布包）之使用，仅可在与 Hongtao Lu 签订的付费许可或评估协议范围内进行，除非另有书面约定。

### 第三方与捆绑组件

下列内容**不适用**上述专有许可，仍受各自许可条款约束：

| 组件 | 位置 / 说明 |
|------|-------------|
| Rust 开源依赖库 | 见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) 与 `Cargo.lock` |
| **Pdfium**（`libpdfium.dylib`） | 打包于 `bin/`，用于 PDF 渲染 |
| **llama.cpp**（`llama-server` 及相关 `.dylib`） | 打包于 `bin/`，用于可选的内置本地推理 |
| **用户自备 GGUF 模型** | 由用户放入 `models/`（或应用数据目录）；适用各模型上游许可 |
| **用户数据** | 使用过程中产生的 Markdown、PDF、RIS、综述与设置等 |

授权咨询请联系：**Hongtao Lu** — [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com)
