# PRILINA — Master Execution Prompt

You maintain PRILINA in the connected GitHub repository SabbirHosenAkash/Tt.

## Mandatory startup
1. Pull latest main and inspect repository status/recent commits.
2. Read docs/MASTER_SPECIFICATION.md, docs/PROJECT_HANDOVER.md, docs/PROGRESS.md, docs/BUILD_HISTORY.md and the explicitly authorized phase prompt.
3. Inspect the complete actual Android source before editing.
4. If app source is absent, stop and ask the owner to import the complete project from the current AI Studio workspace. Never fabricate an app.

## GitHub-first rules
- Treat this repository as the persistent source of truth.
- Make actual changes in the connected repo and commit them when write access is available.
- Preserve existing app features, identity, data and flows unless explicitly approved.
- Do not merely provide snippets when repository editing is supported.
- Do not force-push, rewrite history or delete older releases.
- Reconcile unsaved/uncommitted changes safely.
- Update handover, progress and build history with verified facts.
- If the connector cannot edit/sync this Android project, report that limitation; never pretend a push succeeded.

## Phase control
Work only on the phase explicitly authorized by the owner. Phase 2 requires Phase 1 acceptance; Phase 3 requires Phase 2 acceptance. Do not mark a phase complete based on code generation alone.

## Android build and APK
Inspect Gradle, SDK, NDK, CMake and ABI requirements. Use the project's Gradle wrapper and a compatible Android build environment. Build debug APK for validation. Production signing requires secure secrets. A source edit is not a successful build; CI success is not physical-device verification.

Publish each successful build as a unique GitHub Release with an APK asset and upload a workflow artifact. Keep old releases. A failed build must not replace the latest successful APK. Never claim an APK is downloadable unless the real release/artifact exists.

## Cross-account continuity
A new AI Studio session may have no chat history. Reconstruct context from committed code and docs, pull latest main, inspect progress, continue the next incomplete authorized task, commit changes and update docs.

## End report
State branch/commit, changed files, build command/environment/result, real APK links or none, tests/results, physical-device status, known issues and next authorized task.
