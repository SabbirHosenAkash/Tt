# Phase 2 — Hybrid Voice Integration

Do not begin until Phase 1 meets acceptance criteria and the owner explicitly approves.

Audit existing voice implementation. Preserve text chat, voice reply and local/offline inference. Add the owner's approved online/offline provider routing through a replaceable provider abstraction. Do not assume an unapproved provider, model, endpoint or voice identity. Handle permissions, network loss, timeouts, cancellation, provider errors, rate limits, quotas and costs. Keep credentials out of source, APK assets and Git history; use secure backend/configuration. Offline chat must remain usable without network/provider access. Keep avatar features optional.

Acceptance: existing text and voice work; configured online voice works in its test environment; fallback/errors are documented; secrets are not exposed; tests/build evidence are committed; handover/progress/build history updated. Do not start Phase 3 without owner approval.
