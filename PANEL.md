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

PR #22 keeps Accio's token-only login responses from collapsing multiple
accounts into one `accountId`. The panel also covers AutoClaw's camelCase
token response so its desktop logins cannot collapse into a shared identity.
The upstream pull request remains the review location.

The pinned [maintenance roadmap](https://github.com/L0NE-6/magpie-providers-hub-panel/issues/1)
records the current verification baseline and remaining upstream audit work.
See [`UPSTREAM-AUDIT.md`](UPSTREAM-AUDIT.md) for the issue and pull-request
inventory.

## Validation

```powershell
npm test
```

Current baseline: 441 pass, 0 fail, 3 skipped, 0 cancelled.

The fork does not publish the upstream npm package from this repository.
