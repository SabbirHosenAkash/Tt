# PRILINA — Safe Repair Prompt

Read master execution prompt, specification, handover and progress first.

Use the latest complete source, exact error/log, reproduction steps, expected behavior and actual behavior. If essential evidence is missing, ask rather than guessing.

1. Pull latest repository state and inspect commits/working tree.
2. Reproduce issue or explain why not possible.
3. Identify root cause from code/evidence.
4. Make smallest safe fix and preserve unrelated features.
5. Add/update regression tests where practical.
6. Run relevant tests, lint and Android build.
7. Review diff for regressions, accidental deletions and secrets.
8. Commit fix and update handover/progress/build history.
9. Keep older known-good APK releases; publish a new unique release only after successful build.
10. Report changes, tests, uncertainties and actual artifact link.

Never claim a bug is fixed solely because code changed. Never fabricate tests, logs, builds, APKs or device verification.
