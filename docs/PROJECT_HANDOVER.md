# PRILINA — Project Handover

Read this first when continuing from a new AI Studio session or Gmail account. Update it with verified facts after every meaningful change.

## Identity
- Project: PRILINA Android personal AI app.
- Repository: https://github.com/SabbirHosenAkash/Tt
- Default branch: main
- Source of truth: committed repository files.

## Verified state at setup
- Repository was newly created before this continuity setup.
- Continuity documentation, prompts and Android CI workflow are being added.
- Complete PRILINA Android source is NOT yet imported.
- No APK has been built from this repository.
- Owner reports Phase 1 was started in another AI Studio session; its changes are not here until imported/committed.

## Project context supplied by owner
- Local-first Android AI using llama.cpp and GGUF.
- Generic model support is desired, not only one Qwen model.
- Reported issue: model appears active but gives no answer, or request remains running.
- Android 11 and 8 GB RAM were mentioned previously; reconfirm current device/ABI.
- Hybrid voice is a later phase; preserve existing text chat, voice reply and offline features.

## Status
| Item | State | Evidence |
|---|---|---|
| Continuity documentation | Added in this repo | Current commits |
| Android CI scaffold | Added, not yet run against app | Workflow file |
| Android app source | Not imported | No app source tree |
| Phase 1 | Reported started externally; not verified here | Owner report |
| Phase 2/3 | Not started here | No source evidence |
| APK from this repo | None | No successful build |

## Next actions
1. Export the complete latest PRILINA source from the active Phase 1 AI Studio session.
2. Import the full Android project, including Gradle wrapper/settings/build files, app source and native C/C++/JNI sources.
3. Preserve docs/, prompts/ and .github/workflows/; merge any naming conflicts carefully.
4. Do not commit secrets, signing keys or private model weights.
5. Inspect actual SDK/NDK/CMake/ABI requirements and adapt CI.
6. Run CI and record real build/test evidence.
7. Compare imported source with the external Phase 1 report and update this file.

## Switching accounts
1. Authorize the new AI Studio session/account to access this GitHub repository.
2. Connect/import the same repository and pull latest main.
3. Read MASTER_SPECIFICATION, this file, PROGRESS, BUILD_HISTORY and the authorized phase prompt.
4. Inspect recent commits and working tree; do not overwrite unsaved work.
5. Continue from the next incomplete authorized task, then commit and update handover/progress.

GitHub does not transfer AI Studio chat history, unsaved workspace files, model quota, temporary context, API keys or local device state. Each Google account needs its own GitHub authorization.
