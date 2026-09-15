# Phase and tier schema update

Date: 2026-09-15

## Canonical rule applied

- `cc` is the continuous API surface. It has no SDK tier directories and no SDK entitlement gate. Tier rank is used only as API pricing weight.
- `cv` is the SDK surface. It exposes the ordered ladder `free -> lite -> plus -> pro -> suite -> enterprise`.
- `vc` and `vv` remain authentication/session phases and do not become product tiers.
- API pricing uses the triangular rank delta: `T(to) - T(from)`, where `T(n) = n(n+1)/2`.

## Updated roots

The canonical `phase-tier-model.json` is now present and validated at:

- `C:\Users\honey\Desktop\honeydev\phase-tier-model.json`
- `C:\Users\qwert\Desktop\qwerty_enterprises\phase-tier-model.json`
- `C:\Users\honey\Desktop\senpai_productions\phase-tier-model.json`

All three files carry the same schema, identify their owning entity, and record the Helix junction as `honeydev`, `qwerty`, and `senpai` at one third each with `escamillajoseph44` recorded as the account context.

## Escamilla junction audit

The Escamilla account-tree junction was checked at:

`C:\Users\honey\Desktop\honeydev\pro\Organization\Company\v\vv\Governance\centralized\proprietor\escamillajoseph44.__account-tree`

The account tree exists and contains all four phase branches: `c\cc`, `c\cv`, `v\vc`, and `v\vv`. The junction is therefore phase-complete. No historical data was deleted or moved.

## Validation

All three model files parse as JSON. Each reports `cc` as API with no tiers, `cv` as SDK with six tiers, and the same three-owner junction. The legacy `src_deprecated` trees remain retained as historical materialization; they are not treated as the canonical entitlement layout.

## Honeydev SDK relocation

The active 41,999-file SDK tree that was incorrectly visible at `c\\cc\\products\\sdk` was synchronized into `c\\cv\\products\\sdk` (41,999 source files copied; the destination retains its three pre-existing canonical files). The old tree is preserved at `c\\cc\\products\\sdk.legacy-20260915` for rollback and historical inspection. The original incorrect path no longer exists, so directory discovery cannot treat CC as an SDK surface.

