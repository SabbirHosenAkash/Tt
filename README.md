# PRILINA — GitHub Project Hub

This repository is the persistent source of truth for PRILINA: Android source code, phase status, decisions, handover notes, build reports and downloadable APK releases.

## Start here
1. Read docs/MASTER_SPECIFICATION.md.
2. Read docs/PROJECT_HANDOVER.md, docs/PROGRESS.md and docs/BUILD_HISTORY.md.
3. Follow docs/WORKFLOW_GUIDE.md.
4. Give the coding agent prompts/MASTER_EXECUTION_PROMPT.md and only the currently authorized phase prompt.
5. Import the complete Android source before running a build.

## Downloads
- APK Releases (newest successful build marked latest; older releases retained): https://github.com/SabbirHosenAkash/Tt/releases
- Source ZIP: use the repository Code → Download ZIP option.

## Current truth
This repository currently contains the continuity/workflow scaffold. The complete PRILINA Android source has not yet been imported, so no APK has been built from this repository. Never represent a workflow file as an app build.

## Security
Never commit API keys, passwords, access tokens, signing keystores, private model weights or personal secrets. Use GitHub Actions secrets for sensitive build configuration.
