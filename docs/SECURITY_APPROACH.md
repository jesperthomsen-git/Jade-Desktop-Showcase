# Security and privacy

**Jade Desktop is an engineering and learning project, not an independently audited secure product.**

## Principles

- Default-deny sensitive operations.
- Grant only the minimum operation, scope, purpose, and lifetime required.
- Verify native peer identity rather than assuming local processes are trustworthy.
- Treat retrieved notes, model output, and future external tool data as untrusted.
- Keep security decisions outside language-model-generated text.
- Distinguish synthetic test evidence from production assurance.

## Current limitations

The demonstrated desktop uses a development communication path. Production IPC security, separate Windows service identities, replay and revocation, packaged application protections, and end-to-end private-data authorization have not yet been verified.

Real Obsidian vault access is **disabled**. Future searching, retrieving, and sharing an excerpt with a model would require separate explicit authorization.

## Public disclosure boundary

This repository does not publish credentials, private notes, internal host paths, unredacted logs, sensitive configuration, or detailed live attack procedures. Security lessons are shared at a high level after review.
