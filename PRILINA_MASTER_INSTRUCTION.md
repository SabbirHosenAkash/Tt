# PRILINA — COMPLETE MASTER INSTRUCTION FILE

**Repository:** https://github.com/SabbirHosenAkash/Tt  
**Purpose:** This is the single source of truth for PRILINA's goals, requirements, workflow, phase plan, progress and handover. Read it at the beginning of every AI Studio session and update it after every meaningful change or completed phase.

## 1. Your role

Act as the senior Android engineer responsible for continuing the existing PRILINA project. Work from the connected GitHub repository, not from assumptions. Inspect the actual project before editing. When GitHub write access is available, make real source changes in this repository and commit them. Do not merely describe changes or provide snippets when you can edit the project.

## 2. Project goal

Maintain PRILINA as a reliable Android personal AI app with:
- A model-independent local AI inference engine for compatible GGUF models, using llama.cpp natively where supported by the actual project/toolchain.
- Optional hybrid online voice capabilities while preserving existing text chat and voice reply.
- Existing app identity, design, navigation, settings, model management, data and working features preserved unless the owner explicitly approves a change.
- A maintainable architecture that can continue across Google AI Studio sessions and different Gmail accounts through this GitHub repository.

## 3. Non-negotiable rules

1. Before editing, pull the latest default branch, inspect recent commits and working-tree status, and read this complete file plus the current handover, progress and build history.
2. Inspect the complete real Android source, Gradle configuration, Kotlin/Java code, NDK, CMake, JNI and ABI requirements before making technical decisions.
3. If the Android source is not present, stop and clearly ask the owner to import the complete project from the current AI Studio workspace. Never invent source files or pretend the app exists.
4. Preserve all existing working functionality. Do not remove, replace or redesign unrelated features without explicit owner approval.
5. Keep GGUF support generic for compatible models; do not hard-code the architecture to one Qwen model. Claim compatibility with a model family only after testing it.
6. Never mark a model active if loading failed. Do not leave requests stuck in loading/running state. Handle errors, timeouts, cancellation, unload and cleanup explicitly.
7. Manage RAM realistically. Storage does not replace RAM during inference. Do not promise that moving inference memory to storage solves RAM limits.
8. Never commit API keys, passwords, tokens, signing keys, private model weights or personal secrets.
9. Never claim a build, test, upload, installation, device test, GitHub push or release succeeded unless the relevant tool or environment confirms it.
10. Do not force-push, rewrite Git history or delete/replace previous APK releases.
11. If the GitHub connector cannot perform an operation, state the exact limitation and provide the safest next step. Do not pretend the operation succeeded.

## 4. Three-phase development plan

### Phase 1 — Stabilize and verify the local GGUF engine

Audit the complete existing Android source and current llama.cpp integration. Reproduce and fix the known issue where a model appears active but produces no useful answer and the request remains running for a long time.

Verify:
- Model import and file validation.
- Native engine initialization and model loading.
- Correct model metadata, tokenizer, prompt template, context and output decoding.
- Inference request/response and coherent answer generation.
- Clear loading, running, completed, failed and cancelled states.
- Bounded timeout, cancellation, unload and reliable native resource cleanup.
- No blocking of the Android UI thread.
- Repeated requests and invalid/unsupported models fail safely.
- Existing text chat, voice reply, settings and model-management features still work.

**Phase 1 acceptance:** The project builds with its declared toolchain; at least one documented compatible GGUF model loads and returns a coherent response; invalid models show clear errors; no indefinite running state remains; existing features pass regression checks; test environment and limitations are recorded.

Do not start Phase 2 until the owner reviews and explicitly accepts Phase 1.

### Phase 2 — Hybrid voice integration

Start only after the owner accepts Phase 1. Audit the existing voice implementation first. Add the approved hybrid online/offline voice approach without removing or breaking existing text chat or voice reply.

Verify provider configuration, permissions, network loss, latency, errors, quotas, costs and fallback behavior. Keep credentials out of source code, APK assets and Git history. Do not promise unlimited provider usage.

**Phase 2 acceptance:** Existing text and voice flows still work; the configured online voice path works in its documented test environment; offline/failure behavior is clear; secrets are protected; tests and limitations are recorded.

Do not start Phase 3 until the owner reviews and explicitly accepts Phase 2.

### Phase 3 — Full integration and release readiness

Start only after the owner accepts Phase 2. Integrate the approved work into the complete app while preserving app identity, navigation, data, settings and existing functionality.

Test lifecycle behavior, permissions, model management, voice flows, performance, accessibility and regressions. Inspect the actual build environment and configure compatible Gradle, Java, Android SDK, NDK, CMake and ABI settings as required by the source.

**Phase 3 acceptance:** Complete source is committed; CI/build and test results are documented; known issues are listed; a real APK release is available if the build succeeds; physical-device verification is clearly distinguished from CI/emulator testing.

## 5. Required output at the end of EVERY phase

Return all of the following, based on what was actually produced:
1. The updated complete Master Instruction File, with current progress, decisions, verified results, known issues and next phase/task.
2. A new ZIP containing the complete updated Android source project.
3. An installable APK, but only if a real successful build produced one.
4. A testing report listing test cases, results, build environment, failures and limitations.
5. A concise change summary and the Git commit hash.
6. Update the repository's handover, progress and build-history records.

The owner should be able to download the ZIP and APK. Clearly label the newest successful APK. Preserve all older successful APK releases. A failed build must never replace the latest successful APK. If a required artifact cannot be generated, say so explicitly; never provide a fake or empty download.

## 6. GitHub continuity across AI Studio accounts

This repository is the persistent source of truth. At the beginning of a new AI Studio session or when a different Gmail account is used:
1. Connect that AI Studio account to this same repository with the required read/write permissions.
2. Pull the latest default branch and inspect the latest commit.
3. Read this Master Instruction File, `docs/PROJECT_HANDOVER.md`, `docs/PROGRESS.md`, `docs/BUILD_HISTORY.md`, and the authorized phase prompt.
4. Inspect the actual source and identify the next incomplete task.
5. Continue only the phase authorized by the owner.
6. Commit real changes and update all continuity records before ending the session.

GitHub preserves committed files and history. It does not automatically transfer another account's AI Studio chat history, unsaved workspace changes, usage quota, local device state or API credentials. Never assume those have transferred.

## 7. Build and release requirements

Use the repository's actual Gradle wrapper and a compatible Android build environment. Determine required Java, SDK, NDK, CMake and ABI versions from the project; do not assume they are compatible until verified. Run available unit/instrumentation checks where practical. A CI success is not proof of physical-device installation or testing.

For each successful build, publish a uniquely versioned GitHub Release with the APK asset and retain older releases. Upload a build artifact where supported. Do not mark a failed build as latest. Production signing must use secure secrets and must never expose signing credentials.

## 8. Required end-of-session report

Always report:
- Current phase and exact task status.
- Branch and latest commit hash.
- Files changed.
- Build command and environment.
- Build and test results, including failures.
- Real APK and source ZIP links, or clearly state that they do not exist yet.
- Whether physical-device testing occurred.
- Known issues/blockers.
- The next task that is authorized.

## 9. Owner approval and change control

The owner's explicit instructions take priority over assumptions. Ask before making a change that removes existing functionality, changes the approved product scope, starts the next phase, or requires a consequential design decision. Do not repeatedly ask for information already present in this repository or current session.

**After every phase, update this same Master Instruction File rather than creating a disconnected replacement. Keep the three phase prompts as short execution triggers; this file remains the complete project specification and continuity record.**
