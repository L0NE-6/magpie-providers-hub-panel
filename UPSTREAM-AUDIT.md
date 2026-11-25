# Upstream Audit

Snapshot: 2026-11-26. Upstream remains
[`Gyl1219/magpie-providers-hub`](https://github.com/Gyl1219/magpie-providers-hub).
Its `main` is at `270a8cc1`; the maintenance `panel` includes that history.

## Upstream Security Sync

| Upstream commit | Coverage | Validation |
| :--- | :--- | :--- |
| [`270a8cc`](https://github.com/Gyl1219/magpie-providers-hub/commit/270a8cc13cf8d977780fef2fdf603603f7ecb198) | AStudio, Loomy and Magicrew local sign-in endpoints now reject cross-site requests before routing. This closes the remaining loopback CSRF paths after PR #21. | Full `npm test`: 450 pass, 0 fail, 3 skipped, 0 cancelled. |

## Open Pull Requests

| Item | State | Maintenance decision |
| :--- | :--- | :--- |
| [#22](https://github.com/Gyl1219/magpie-providers-hub/pull/22) | Clean and mergeable upstream candidate | The panel carries the Accio account-id fingerprint fix plus AutoClaw camelCase token coverage. Focused `tests/pool.test.mjs` is 19/19; full `npm test` is 450 pass, 0 fail, 3 skipped. Real two-account Accio and AutoClaw logins were not available. |
| [#21](https://github.com/Gyl1219/magpie-providers-hub/pull/21) | Merged upstream | The per-window token and same-origin `/paste` protection are included in the current upstream history. The full panel suite passes 450/0/3/0. |
| [#2](https://github.com/Gyl1219/magpie-providers-hub/pull/2) | Conflicting and too broad | Do not merge as one change. The catalog-key half already landed upstream; the account-import half must be rebased as a separate PR. |

## Open Issues

| Item | State | Next evidence |
| :--- | :--- | :--- |
| [#1](https://github.com/Gyl1219/magpie-providers-hub/issues/1) | Architecture discussion | Keep the aggregate wrapper. Document failover and per-provider settings tradeoffs rather than splitting packages without a distribution plan. |
| [#3](https://github.com/Gyl1219/magpie-providers-hub/issues/3) | Panel carries an opt-in callback override | Accio and LobsterAI can now use a public callback origin, bind host and fixed port while preserving state validation. Defaults remain `127.0.0.1`. Offline URL/config tests pass; a real Linux host plus remote-browser callback is still unverified. |
| [#5](https://github.com/Gyl1219/magpie-providers-hub/issues/5) | Fixed upstream in 0.13.2 | Accio China and international entries now pass the region through sign-in, exchange, renewal and catalog calls. Waiting for reporter confirmation. |
| [#6](https://github.com/Gyl1219/magpie-providers-hub/issues/6) | Fixed upstream in 0.13.1 | Browser sign-in now uses the user's default browser instead of the automation CDP browser. Waiting for reporter confirmation. |
| [#7](https://github.com/Gyl1219/magpie-providers-hub/issues/7) | Fixed upstream in 0.13.1 | MonkeyCode China and international preserve tier prefixes with `modelHasSlash`. Waiting for a remaining model ID and log if 404 persists. |
| [#20](https://github.com/Gyl1219/magpie-providers-hub/issues/20) | Upstream risk-control response | The 0.13.5 diagnostics no longer invent a cause. A real `4100404` response still needs a vendor-side explanation or a reproducible account/device comparison. |

## Verification Rules

- A merged commit is not the same as a reporter-confirmed fix.
- No real account, cookie, token or private prompt belongs in a fixture or issue.
- A Linux-only callback change needs either a Linux test host or a documented,
  reproducible callback relay.
- The fork never publishes the upstream npm package.
