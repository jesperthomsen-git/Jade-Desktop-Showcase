# Jade Desktop 🌿

**A local-first AI companion — built with privacy, thoughtful design, and security-minded engineering.**

*Public development showcase · Windows-first, Linux-ready · November 2026*

> **Status:** A working Windows **development** desktop has been demonstrated with Tauri, React, a Python backend, and local Ollama/Qwen chat. It is **not** a packaged or security-hardened release. Private memory access remains disabled.

## Meet Jade

Jade Desktop is an independent personal project exploring how to build an approachable AI companion while keeping its owner in control. The long-term vision combines local conversation, a polished desktop interface, a Live2D character, and selectively authorized access to personal knowledge and tools.

This repository is a **public portfolio**, not the application source or a downloadable release.

## Progress at a glance

| Capability | Status |
| --- | --- |
| Native Windows development window | Demonstrated |
| React desktop interface | Demonstrated |
| App-managed Python backend startup/shutdown | Demonstrated in development |
| Local Ollama / Qwen conversation | Demonstrated in development |
| Authenticated production desktop/backend IPC | Research and validation in progress |
| Private Obsidian memory access | **Disabled** pending security and permission gates |
| Windows packaged distribution | Planned |
| Linux validation | Planned |
| Live2D Jade and polished companion HUD | Planned |

**Demonstrated** means observed in a development setup, not production-ready or independently audited.

## Technology

- **Desktop:** Tauri / Rust
- **Interface:** React / TypeScript
- **Core:** Python / FastAPI
- **Local model:** Ollama / Qwen
- **Future knowledge integration:** permission-scoped Markdown / Obsidian
- **Future character:** Live2D

## Engineering values

**Local-first.** Favor on-device processing and explicit dependencies.

**Least privilege.** Sensitive capabilities should be separately authorized, narrowly scoped, and disabled by default.

**Evidence over claims.** Synthetic test passes are useful, but do not establish production security.

**Modular and portable.** Keep shared application logic separate from Windows- and Linux-specific security mechanisms.

**Iterative learning.** Record milestones, blockers, trade-offs, and lessons rather than hiding unfinished work.

## Explore the project

- [Project vision](docs/PROJECT_OVERVIEW.md)
- [Development milestones](docs/PROGRESS.md)
- [Architecture overview](docs/ARCHITECTURE.md)
- [Security and privacy approach](docs/SECURITY_APPROACH.md)
- [Visual direction](docs/VISUAL_DIRECTION.md)

## Visual direction

Jade's character concept features silver-white hair, violet eyes, jade-green botanical accents, and a dark outfit with a light jacket. The interface direction favors a readable dark HUD with restrained mint and violet highlights.

Concept art is **not** the same as a finished, integrated Live2D model. A reviewed screenshot and artwork gallery can be added later.

---

*This public showcase intentionally excludes private notes, credentials, sensitive implementation details, and unreviewed development screenshots.*
