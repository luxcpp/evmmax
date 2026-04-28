# LICENSE-NOTICE — luxcpp/evmmax

Snapshot of [ethereum/evmone](https://github.com/ethereum/evmone), specifically
the `evmmax` modular-arithmetic header used by EVM-style precompiles.

| Field      | Value                                                    |
| ---------- | -------------------------------------------------------- |
| Upstream   | https://github.com/ethereum/evmone                       |
| Pinned     | `v0.21.0` (matching upstream evmone release)             |
| License    | Apache-2.0                                               |
| SPDX       | `SPDX-License-Identifier: Apache-2.0`                    |
| Tag        | `v0.21.0`                                                |

## Why a fork

luxcpp/crypto consumes `evmmax::evmmax` (header-only INTERFACE; provides the
Montgomery `ModArith` template) via FetchContent from this fork at a pinned
tag. Forking guarantees reproducibility, audit surface, and resilience against
upstream availability disruptions.

## Tag policy

* Semver tags only — mirrors upstream evmone releases.
* No `latest` / no `master` consumption — luxcpp/crypto pins by tag.
* New tags are cut only after KATs in luxcpp/crypto pass against the new tree.

## Updating

1. `git fetch upstream master`
2. Audit the diff against upstream changelog (specifically `lib/evmmax/`).
3. Run luxcpp/crypto KATs (`ctest -R 'bn254|modexp'`) against this branch.
4. Tag a new `vX.Y.Z` matching upstream only after KATs pass.

Apache-2.0 — attribution preserved via the upstream LICENSE in the repo root.
