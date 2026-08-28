# Changelog (public notices)

All parameter changes to Goji contracts on Robinhood Chain are announced here before they take
effect (fee switch, bucket wallets, bridge limits, migration windows, governance actions).

## Unreleased
- 2026-08-28: Project opened. No mainnet addresses exist yet; anything claiming to be HANU v2 on
  mainnet before it is announced here is not ours.

## Testnet (Robinhood Chain Testnet, chain id 46630) — 2026-08-28
Test deployment for public review. These are TESTNET contracts with a stand-in v1 token; they hold no
value and will be redeployed. Verified source on the testnet explorer.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0xa51110eCe1D5abA506A02D59f5011152fC67d529` |
| Fee policy (tax = 0, three buckets) | `0xB39c8832A554787e49744C8e2EF787d5D4dF4cdc` |
| v1 → v2 migrator (lock) | `0x471299F7E1126591cf3476ffF67EcE38Cdc680E0` |
| Lock-release bridge | `0xF5e6FbE0380Dc151D5B760b05a18147B8CB238C2` |
| Mock v1 (testnet only) | `0xA337Ece73dF3F89F94C9fF89da0FB553b30Eb6D5` |

Exercised on chain: a governed mint (proposal, approval, execution), a 1,000 v1 → 1,000 v2 lock
migration, and an announced burn of 200 locked v1 that can only execute after the seven-day delay.
