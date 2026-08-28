# Changelog (public notices)

All parameter changes to Goji contracts on Robinhood Chain are announced here before they take
effect (fee switch, bucket wallets, bridge limits, migration windows, governance actions).

## Unreleased
- 2026-08-28: Project opened. No mainnet addresses exist yet; anything claiming to be HANU v2 on
  mainnet before it is announced here is not ours.

## Testnet, post-audit redeploy (Robinhood Chain Testnet, chain id 46630) — 2026-08-28
An internal security audit (static analysis, property tests, two independent adversarial reviews)
found 9 medium and 12 low issues; all were fixed or accepted with a written rationale, and the
contract set was redeployed. Highlights holders should know: a fee policy can never block a
transfer (any bad answer makes the transfer fee-free), fee increases and wallet re-pointing take
effect only after a one-day public delay, mint approvals expire and re-check live signers, bridge
payouts are rate-limited and need multiple relayers, and float withdrawals are announced two days
ahead. The earlier testnet addresses below are superseded and must not be used.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0x7ab5c80336a58Ce21AE970f5881EB41718ec29b4` |
| Fee policy (tax = 0, three buckets) | `0x3B338D6dc587F87222E241a06cb84C0B66f56ab2` |
| v1 → v2 migrator (lock) | `0xc2cC4A6095F07BEfeEae719499f52877C78897f0` |
| Lock-release bridge | `0xE3E14Bc3Ee9da75bBa131bdeac0c7dFf73af79A0` |
| Mock v1 (testnet only) | `0x8E0dE5f74286A72e0839d537a7A3C72945da678E` |

## Testnet, first deployment (superseded) — 2026-08-28
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
