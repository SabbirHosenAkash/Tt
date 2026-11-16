# PRILINA — Build and APK History

Add a row only after GitHub Actions reports success and the APK artifact/release is verified.

| Build | Date | Commit | Variant | Result | Release |
|---|---|---|---|---|---|
| — | — | — | — | No build from this repository yet | None |

## APK policy
- Publish every successful build as a separately versioned GitHub Release.
- Keep previous releases and APK assets; never automatically delete old APKs.
- Mark the newest successful release as GitHub's latest release.
- Upload an Actions artifact for each run too.
- A failed build must not replace or be labeled as the latest successful APK.
- Debug APK is for testing, not a production-signed release.

Release notes should include build number, source commit, variant, application ID when known, environment/command, tests, known issues and physical-device test status.
