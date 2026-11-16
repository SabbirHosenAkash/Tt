# GitHub Workflow Guide

## Import the Android project
This repository currently contains the continuity scaffold, not the Android app. Export the complete latest source from the Phase 1 AI Studio session. Import the full Android project (Gradle wrapper, settings/build files, app source, native C/C++/JNI sources and safe configuration) at root or a documented subfolder. Exclude build caches. Preserve docs/, prompts/ and .github/workflows/; merge conflicts carefully.

## Phase cycle
1. Read specification, handover, progress, build history and authorized phase prompt.
2. Pull latest main and inspect commits/working tree.
3. Audit actual source and plan changes.
4. Implement only the authorized phase.
5. Run tests, lint and Android build.
6. Review diff for regressions, deleted features, generated files and secrets.
7. Commit source changes.
8. Update handover, progress and build history.
9. Verify Actions run and APK release.
10. Wait for owner approval before next phase.

## Switch Gmail / AI Studio account
Both AI Studio sessions must be separately authorized for the same GitHub repository. Connect/import the same repository, pull latest main, read handover/progress/build history, inspect recent commits, and continue from the next incomplete task. Chat history and unsaved workspace changes do not transfer. Never overwrite unsaved work blindly.

## APK downloads and archive
Use the repository Releases tab to download APKs. Each successful build gets a unique release tag and remains available as an older version. Newest successful release is marked latest. Actions artifacts are also attached to each run and may expire according to retention settings.

## Build limits
The workflow requires a real Android Gradle project and Gradle wrapper. This scaffold cannot build an APK by itself. llama.cpp may require a specific NDK, CMake, ABI and native dependencies; inspect and configure them. CI success does not prove physical-device runtime.

## Secrets
Never commit API keys, tokens, passwords, keystores or private model files. Configure secrets in repository settings and use Actions secrets. Rotate any secret accidentally committed; removing it from the latest file does not erase Git history.
