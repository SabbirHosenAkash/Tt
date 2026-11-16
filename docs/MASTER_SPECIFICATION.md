# PRILINA — Master Project Specification

## Purpose
Maintain PRILINA as an Android personal AI app with a model-independent local inference engine and optional hybrid online capabilities. This repository is the durable source of truth across AI Studio sessions and Google accounts.

## Non-negotiable rules
- Preserve all existing working features unless the owner approves a change.
- Inspect actual source before editing; never invent unseen files or claim unperformed tests.
- Commit real source changes to this repository when write access exists.
- Never commit API keys, passwords, tokens, signing keys, private model files or personal secrets.
- Keep GGUF support model-independent, not limited to one model.
- Do not claim builds, tests, uploads, installs or device tests unless they succeeded.
- Keep previous APK releases; publish a new version only after a successful verified build.
- Update handover, progress and build history after each session/phase.

## Product requirements

### Local AI
- Integrate llama.cpp natively when compatible with the actual Android source, NDK and ABIs.
- Support compatible GGUF models through a generic interface (Qwen, Llama, Mistral, Gemma etc. only where verified).
- Correctly handle model import, validation, loading, active state, inference, output, cancellation, unload, errors and cleanup.
- Never mark a failed model load as active.
- Prevent indefinite running states with explicit states, timeouts, cancellation and clear errors.
- Manage memory realistically; storage does not replace RAM during inference.

### Hybrid voice
- Preserve existing text chat and voice reply.
- Keep online voice optional/provider-replaceable where practical.
- Handle permissions, network loss, latency, errors, quotas and costs.
- Keep credentials out of source, APK assets and Git history. Do not promise unlimited provider usage.

### Android compatibility
- Inspect Gradle, Kotlin/Java, SDK, NDK, CMake, JNI and ABI configuration before changing toolchains.
- Previously mentioned Android 11 and 8 GB RAM are not proof of the current test device; reconfirm.
- CI build success is not physical-device verification.

## Phases
### Phase 1 — Local GGUF engine
Audit the complete source and llama.cpp integration. Reproduce and fix the reported model-active-but-no-answer/stuck-running problem. Verify import, loading, prompt template/tokenizer, inference, output, cancellation, timeout, unload and cleanup. Preserve existing app features.

Acceptance: source builds; at least one compatible GGUF model returns a coherent response; invalid models fail clearly; no indefinite spinner; existing chat/voice regressions pass; test environment and limitations are recorded.

### Phase 2 — Hybrid voice
Start only after Phase 1 is accepted by the owner. Audit existing voice flows, implement the approved provider/routing strategy, protect credentials, handle quotas/network errors and preserve offline chat.

Acceptance: existing text/voice work; configured online voice works in its test environment; fallback and failures are documented; secrets are not exposed.

### Phase 3 — Integration and release readiness
Start only after Phase 2 is accepted. Integrate into the complete app without removing features or unexpectedly changing app identity/data/navigation. Test lifecycle, permissions, performance, accessibility and regressions.

Acceptance: source committed; CI/tests documented; APK release available if build succeeds; physical-device test status explicit.

## Definition of done
A phase is complete only when source is committed, build/test evidence exists, known issues are listed, handover/progress/build history are updated, and a real APK release is linked if successfully built. Owner approval is required before the next phase.

## Cross-account continuity
A new AI Studio account connects to this same repository with read/write access, pulls latest main, reads this specification, handover, progress, build history and active phase prompt, inspects recent commits and continues from the next incomplete task. GitHub stores committed files/history, not previous chat history, unsaved workspace changes, quotas or API credentials.

## Session report
Include branch/commit, changed files, build command/environment/result, APK links, tests/results, device-test status, blockers and next authorized action.
