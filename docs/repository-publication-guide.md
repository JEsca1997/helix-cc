# Helix repository publication guide

Date: 2026-09-15

## Repository surfaces

- `JEsca1997/helix-cc` is the public CC/API distribution surface.
- `JEsca1997/helix-cv` is the private CV/SDK implementation surface.
- VC and VV session, contractor, vault, account, and governance data remain private and local.

## CC behavior

CC artifacts may be downloadable while remaining encoded. Downloadability does not grant readable source or executable entitlement. Helix authorization, signature verification, payment state, and token metering must be enforced by the runtime service. Decryption and signing keys must never be committed to GitHub.

Guest mode is anonymous `cc/free`. API pricing uses the triangular rank delta:

`T(toRank) - T(fromRank)`, where `T(n) = n * (n + 1) / 2`.

## CV behavior

CV contains the readable SDK, MCTL, training pipeline, extensions, and tier-specific tools. The SDK ladder is `free -> lite -> plus -> pro -> suite -> enterprise`, gated by the authenticated account and company scope.

## Publication checklist

- Keep secrets, passwords, private keys, cookies, account databases, vault data, and personal documents out of both repositories.
- Keep large binaries and generated runtimes in private artifact storage or Git LFS.
- Publish path manifests and SHA-256 indexes for excluded material so the complete local tree remains auditable.
- Verify CC artifacts are encoded and runtime authorization is enforced before release.

## Credentials to configure privately

Store these in the local Helix secret manager or environment, never in Git:

- GitHub token with repository write permission: `<configure locally>`
- CC artifact encryption key: `<configure in service secret store>`
- CC signing/private key: `<configure in service secret store>`
- Billing/metering credentials: `<configure in service secret store>`
- CV deployment and artifact-storage credentials: `<configure locally>`
- Helix account/session credentials: `<configure locally>`

This document intentionally contains no real passwords, tokens, cookies, or private keys.

