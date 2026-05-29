# Third-Party Notices / 第三方组件声明

**RubyCite** — original application code: **Copyright © 2026 Hongtao Lu** — **proprietary / all rights reserved** (see [LICENSE](LICENSE)). Not open source.

---

## Rust dependencies (Cargo)

Direct dependencies of the `rubycite` core library and `rubycite-desktop` shell (typical licenses):

| Crate | License (typical) |
|-------|-------------------|
| tokio, reqwest | MIT OR Apache-2.0 |
| ureq | MIT OR Apache-2.0 |
| serde, serde_json, serde_yaml | MIT OR Apache-2.0 |
| regex | MIT OR Apache-2.0 |
| chrono | MIT OR Apache-2.0 |
| base64 | MIT OR Apache-2.0 |
| png | MIT OR Apache-2.0 |
| pdfium-render | MIT OR Apache-2.0 |
| tauri, tauri-plugin-dialog, tauri-build (desktop) | MIT OR Apache-2.0 |

Full dependency tree: `Cargo.lock` and `src-tauri/Cargo.lock`

---

## Bundled binaries (`bin/`)

These are copied into the application bundle via Tauri (`tauri.conf.json` → `bundle.resources`).

| Component | Notes |
|-----------|--------|
| **libpdfium.dylib** | Pdfium — see `bin/LICENSE.pdfium` or [ui/licenses/pdfium_LICENSE](ui/licenses/pdfium_LICENSE) |
| **llama-server** (+ related `.dylib`) | llama.cpp / ggml — MIT; verify upstream release and any bundled `LICENSE` in `bin/` |

Other files in `bin/` may be added at build time. Check each upstream license before redistribution.

---

## User-supplied AI models (`models/`)

RubyCite does **not** ship GGUF weights in the repository. Users place `.gguf` files in the application `models/` directory (or equivalent data folder). Those model files are **not** authored by Hongtao Lu. Verify upstream Hugging Face / model card licenses before use or redistribution (e.g. Qwen, Llama, Mistral).

RubyCite **不**在仓库中捆绑 GGUF 权重。用户自行将 `.gguf` 放入应用 `models/` 目录；该等文件**非** Hongtao Lu 创作，使用前请查阅各模型上游许可。

---

## User data

Markdown, PDFs, RIS files, reviews, and settings created while using RubyCite are user data and are not covered by the proprietary source license above.

---

## Contact

**Original code:** Hongtao Lu — [chemiker2010@gmail.com](mailto:chemiker2010@gmail.com) — commercial licensing only. See [LICENSE](LICENSE).
