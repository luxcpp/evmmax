# LUXFI-FORK

This is a luxfi-maintained fork of [ethereum/evmone](https://github.com/ethereum/evmone).

## Pin

- Upstream tag: `v0.21.0`
- Upstream commit: `35b7e1eecd25ec9564f7c010d9ed97062b020fe8`
- License: Apache-2.0 (see `LICENSE`)

## Why this fork exists

luxcpp/crypto consumes `lib/evmmax/evmmax.hpp` (Montgomery modular arithmetic)
for the `bn254`, `secp256r1`, `modexp`, and `evm256` cpp bodies via
`FetchContent`. Pinning to a luxfi-controlled mirror prevents upstream
deletion or rewrite from breaking deterministic builds.

The luxcpp consumer never links anything from this fork beyond the evmmax
INTERFACE target.

## Sync policy

- Track upstream tagged releases only. Never `master` HEAD.
- Pull tags into `sync/<tag>` branches.
- Re-run all luxcpp/crypto KAT suites that include `<evmmax/evmmax.hpp>`
  (bn254, secp256r1, modexp, evm256). Merge to `master` only when all KATs pass.
- If `evmmax.hpp` is unchanged across releases, the sync is a no-op.

## Maintainer

luxfi crypto team. Contact via the `luxfi/crypto` repo.
