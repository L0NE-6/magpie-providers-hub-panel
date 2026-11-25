# Magpie Providers Hub Maintenance Panel

This is an unofficial public maintenance fork of
[`Gyl1219/magpie-providers-hub`](https://github.com/Gyl1219/magpie-providers-hub),
which adapts [`iJetLi/dsh-providers-hub`](https://github.com/iJetLi/dsh-providers-hub)
for Magpie.

## Branches

- `main` mirrors `Gyl1219/magpie-providers-hub` `main`.
- `panel` is the maintenance branch.
- `fix/<issue>-<slug>` contains one focused fix.

## Rules

- Upstream remains authoritative for releases and npm publishing.
- Fixes are tested with `npm test` before entering `panel`.
- No real account, cookie, token or private prompt belongs in a test fixture.
- No claim of a live vendor login unless it was actually performed.
- Upstream issues and PRs remain the primary discussion location.

## Current Security Work

PR #21 protects the local Baizhi and MonkeyCode login paste endpoints with a
per-window capability token and a same-origin check. The focused regression
suite is green; upstream review is still required.

## Validation

```powershell
npm test
```

The fork does not publish the upstream npm package from this repository.
