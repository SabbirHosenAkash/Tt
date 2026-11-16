# Phase 1 — Stabilize and Verify Local GGUF Engine

Read the master execution prompt and master specification first. Work only on Phase 1.

Audit the complete Android source, Gradle files, NDK/CMake/ABI setup, JNI and llama.cpp integration. Trace model import, validation, loading, active state, inference, output, cancellation, unload and cleanup. Reproduce the reported model-active-but-no-answer/stuck-running problem. Distinguish verified device facts from assumptions.

Requirements:
- Keep GGUF handling generic for compatible models, not hard-coded to one Qwen model.
- Propagate native initialization/inference errors to the UI.
- Use explicit loading/running/completed/failed/cancelled states.
- Add bounded timeouts, cancellation and reliable resource cleanup.
- Validate actual model prompt template, tokenizer, context and output decoding.
- Never block the UI thread.
- Manage memory realistically; storage does not replace RAM.
- Preserve existing chat, voice reply, settings, model management and unrelated features.
- Add tests/logging without exposing secrets or private data.

Acceptance:
1. Android project compiles with declared toolchain.
2. One documented compatible GGUF model loads.
3. Test prompt returns coherent output and UI returns idle.
4. Invalid/unsupported model fails clearly.
5. Cancellation, unload and repeated requests do not crash in tested cases.
6. Existing text chat and voice reply still work.
7. CI/test evidence is recorded; physical-device tests are distinguished from CI/emulator.

Commit source, update handover/progress/build history, report evidence and publish a real APK release if build succeeds. Do not start Phase 2 until owner reviews and approves Phase 1.
