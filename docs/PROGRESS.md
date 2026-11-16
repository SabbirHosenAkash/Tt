# PRILINA — Progress Tracker

Mark items complete only with evidence and add commit/workflow/release links.

## Repository setup
- [x] Define master specification and handover.
- [x] Define phase and repair prompts.
- [x] Add Android CI workflow scaffold.
- [ ] Import complete PRILINA Android source.
- [ ] Run CI against real source.
- [ ] Verify APK installation/runtime on physical device.

## Phase 1 — Local GGUF engine
- [ ] Import latest source from active AI Studio session.
- [ ] Audit llama.cpp/JNI/NDK/ABI integration.
- [ ] Reproduce model loading/inference failure.
- [ ] Fix states, output delivery, cancellation, timeout and cleanup.
- [ ] Verify one compatible GGUF model returns a coherent answer.
- [ ] Regression-test existing text chat and voice reply.
- [ ] Commit source and test evidence.
- [ ] Build and publish APK.

Status: owner reported Phase 1 started in a separate AI Studio session; not imported or independently verified in this repository.

## Phase 2 — Hybrid voice
- [ ] Start only after Phase 1 acceptance and owner approval.
- [ ] Audit voice implementation and add approved provider/routing.
- [ ] Handle permissions, network/provider errors, quotas and secrets.
- [ ] Test online voice and offline fallback.
- [ ] Commit source, tests and APK release.

Status: Not started.

## Phase 3 — Integration and polish
- [ ] Start only after Phase 2 acceptance and owner approval.
- [ ] Integrate without removing existing features.
- [ ] Test lifecycle, navigation, permissions, performance and regressions.
- [ ] Commit source, reports and APK release.

Status: Not started.

## Account continuity
- [x] Document new-account handover.
- [ ] Verify second Google account can access repo and continue work.

## Build status
No Android build has run from this repository because the app source is not imported.
