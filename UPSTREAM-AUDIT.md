# Upstream Audit

Snapshot: 2026-11-25. Upstream remains
[`Gyl1219/magpie-providers-hub`](https://github.com/Gyl1219/magpie-providers-hub).

## Open Pull Requests

| Item | State | Maintenance decision |
| :--- | :--- | :--- |
| [#21](https://github.com/Gyl1219/magpie-providers-hub/pull/21) | Clean and mergeable upstream | Keep the per-window token and same-origin `/paste` protection. Focused tests pass 55/55; the full panel suite passes 433/0/3/0. |
| [#2](https://github.com/Gyl1219/magpie-providers-hub/pull/2) | Conflicting and too broad | Do not merge as one change. The catalog-key half already landed upstream; the account-import half must be rebased as a separate PR. |

## Open Issues

| Item | State | Next evidence |
| :--- | :--- | :--- |
| [#1](https://github.com/Gyl1219/magpie-providers-hub/issues/1) | Architecture discussion | Keep the aggregate wrapper. Document failover and per-provider settings tradeoffs rather than splitting packages without a distribution plan. |
| [#3](https://github.com/Gyl1219/magpie-providers-hub/issues/3) | Headless Linux callback design | Needs a configurable callback host/port or one-time callback-code relay. The owner has no Linux host, so this remains design work, not a verified fix. |
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
