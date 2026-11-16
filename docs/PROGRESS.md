# Development milestones

*Updated November 16, 2026. These are development observations, not release certifications.*

## P0.1 — Unified Windows development desktop: demonstrated

A Windows development session showed:

- A native Tauri window hosting the React interface.
- App-managed Python Core startup and shutdown.
- Local Ollama/Qwen chat through the development integration.
- Cleanup of the app-owned backend on window close, without shutting down an independently running Ollama instance.

**Limitations:** Development-only transport; no hardened production IPC, packaged release, or authorized private vault access.

## P0.2 — Authenticated IPC and OS identity: in progress

A threat model and synthetic Windows named-pipe health fixtures have been explored. A same-user process-rights test showed that ordinary same-user isolation was insufficient in the tested environment.

A disposable Windows guest validation plan has been written, covering separate service identities, effective OS token checks, unauthorized peers, and rollback.

**Blocked:** No suitable disposable Windows guest was available for actual service-isolation tests. Production peer authentication, replay/revocation, secure credential bootstrap, and related boundaries remain unproven.

## Future milestones

1. Verify Windows IPC identity and authorization with isolated synthetic tests.
2. Define portable IPC contracts; later validate a Linux-specific adapter.
3. Improve local conversation reliability and recovery.
4. Validate read-only retrieval and cross-session recall with **synthetic** Markdown.
5. Seek separate owner approval before any real private notes are accessed or used as model context.
6. Secure Windows packaging and test Linux packaging and isolation.
7. Integrate the Jade avatar, polished HUD, and optional audio or connected services.

## Reading status labels

- **Demonstrated:** observed in a defined development setup.
- **In progress:** active design, testing, or implementation with unresolved work.
- **Planned:** not yet verified or implemented.
- **Disabled:** deliberately unavailable until required security and consent gates are met.
