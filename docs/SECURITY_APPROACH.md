# Security engineering and privacy

**Jade Desktop is an independent learning project, not an independently audited or production-hardened security product.** The terms below describe engineering principles, controls being evaluated, and future goals. A documented method is not proof of implementation.

## Core architecture and engineering terms

| Term | Meaning and intended use |
| --- | --- |
| **Zero Trust Architecture (ZTA)** | Explicitly verify identity and authorization for sensitive operations, regardless of whether traffic is local. |
| **Least privilege** | Restrict a component to the minimum capabilities, operations, data and duration needed. |
| **Default deny / fail closed** | Refuse access when permission, identity, validation or required evidence is absent. |
| **Defense in depth** | Use independent safeguards so one failure need not expose everything. |
| **Component and process isolation** | Separate UI, backend, model runtime and private-data access across appropriate boundaries. |
| **Authentication vs. authorization** | Establish *who or what* is communicating, then separately decide *what it may do*. |
| **Authenticated local IPC** | Verify the real peer and active process instance over a local communication channel; localhost and PID alone are insufficient. |
| **OS-enforced access control** | Use native identities and permissions rather than relying only on application-level claims. |
| **Credential minimization and protection** | Avoid broadly shared or long-lived secrets; protect delivery, use, rotation and disposal. |
| **Replay resistance and revocation** | Reject stale/reused requests and remove authorization when a grant or process instance expires. |
| **Input validation and bounded processing** | Enforce accepted schemas, sizes, operations and failure behavior at trusted boundaries. |
| **Attack-surface reduction / secure defaults** | Expose only required interfaces and capabilities, disabled unless explicitly needed. |
| **Secure development lifecycle** | Review changes, test boundaries, document assumptions and revisit unresolved risks. |
| **Adversarial and negative testing** | Test that unauthorized operations fail, using isolated, synthetic data and environments. |
| **Cross-platform security adapters** | Preserve portable contracts while independently validating Windows and Linux OS protections. |

## AI and prompt-injection defense terminology

| Term | Defensive intent |
| --- | --- |
| **Untrusted-input separation** | Treat Markdown notes, retrieved text, model output and future web/email/tool content as data, not privileged instructions. |
| **Prompt-injection resistance** | Prevent instructions embedded in untrusted content from changing the system's permissions or behavior. |
| **Tool authorization outside the model** | Enforce each tool operation in trusted application code, never solely on the model's wording. |
| **Scope-bound consent** | Distinguish permission to search, read, and pass an excerpt into a model; each requires its own applicable approval. |
| **Provenance and path containment** | Identify where data came from and restrict any future filesystem access to explicitly approved boundaries. |
| **Output and action validation** | Verify structured requests and intended effects before privileged operations. |
| **Indirect and multi-turn attack testing** | Evaluate whether untrusted content or accumulated context can undermine authorization across turns. |
| **Data-exposure prevention** | Minimize personal data in prompts, logs, diagnostics, exports and public documentation. |

These controls are **design requirements or planned validation activities unless specifically marked demonstrated**.

## Current evidence and limits

- **Demonstrated:** Windows development desktop lifecycle and local chat; private memory endpoint remains denied.
- **Explored synthetically:** Windows health-only IPC fixtures, peer-proof checks and unauthorized-peer cases. These do **not** establish production security.
- **Observed limitation:** Same-user process access-rights testing showed insufficient isolation in the tested development environment.
- **Blocked:** Separate Windows service-identity verification awaits an approved disposable guest.
- **Not yet verified:** Production IPC identity, secure bootstrap, OS isolation, replay/revocation, hardened packaged Tauri capabilities and CSP, authenticated Ollama instance, end-to-end consent, and robust prompt-injection resistance.
- **Not enabled:** Real private Obsidian vault access, automated memory writes, and permission-sensitive external services.

## MITRE-informed review process

We use public defensive knowledge bases to help identify *relevant* risks, not to claim exhaustive coverage:

- [MITRE ATT&CK](https://attack.mitre.org/) — adversary behavior and defensive context.
- [MITRE ATLAS](https://atlas.mitre.org/) — threats affecting AI-enabled systems.
- [MITRE CWE](https://cwe.mitre.org/) — software weakness categories.

**When a relevant MITRE weakness or technique arises:**

1. **Triage privately with Codex.** Determine relevance to Jade's actual components and trust boundaries. Record the reference, affected milestone, risk, evidence and confidence.
2. **Define defensive acceptance criteria.** Prefer narrowly scoped mitigations, least-privilege checks, synthetic regression tests, and an explicit owner approval gate for any privileged or sensitive changes.
3. **Verify and document.** Separate a proposed mitigation from a tested one; record negative tests, remaining limitations, and follow-up actions. Keep real secrets and private notes out of fixtures.
4. **Publish only a reviewed summary.** After the finding is appropriately addressed or safely scoped for disclosure, describe the broad risk category, security principle, and verified progress without exposing attack instructions, exact bypasses, secret locations, exploitable endpoints, or sensitive configuration.

A new reference **does not automatically authorize Codex** to change the working host, provision services, access the real vault, publish a finding, or merge a PR. Owner approvals and the existing roadmap still apply.

## Public disclosure boundary

This showcase intentionally avoids exploit walkthroughs, payloads, weaponizable implementation detail, live attack paths, credentials, private data, internal filesystem paths and unredacted logs. We may describe what was learned and how we test defensively, while retaining enough private engineering evidence for honest review.

**No security system is guaranteed exploit-proof.** This project aims to reduce risk through explicit trust boundaries, measured tests, and ongoing review.
