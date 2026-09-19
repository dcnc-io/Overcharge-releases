# Future Windows signing procedure

This unsigned beta does not enroll in or purchase a signing service.

1. Confirm the publisher identity and current issuer eligibility, then complete verification with Microsoft Artifact Signing or another supported public code-signing issuer.
2. Keep private keys in supported secure storage, a hardware token/HSM or signing service. Grant only required signing permissions; do not commit credentials.
3. Configure the pinned electron-builder version and replace the unsigned-only checks. Sign the app, installer and uninstaller using SHA-256 with an RFC 3161 timestamp. Fail the release if required signing is absent.
4. Verify the publisher, chain and timestamp with `signtool verify /pa /all /v` and `Get-AuthenticodeSignature`.
5. Calculate checksums after signing. Publish a new version, verify anonymous downloads and Windows installation, and update the web manifest. Never replace previously published versioned files.

Signing does not guarantee immediate SmartScreen reputation.

- [Microsoft Artifact Signing FAQ](https://learn.microsoft.com/en-us/azure/artifact-signing/faq)
- [electron-builder v26 Windows signing](https://www.electron.build/v26/docs/features/code-signing/code-signing-win/)
- [Microsoft SignTool](https://learn.microsoft.com/en-us/windows/win32/seccrypto/signtool)
