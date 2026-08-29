# Changelog (public notices)

All parameter changes to Goji contracts on Robinhood Chain are announced here before they take
effect (fee switch, bucket wallets, bridge limits, migration windows, governance actions).

## Unreleased
- 2026-08-28: Project opened. No mainnet addresses exist yet; anything claiming to be HANU v2 on
  mainnet before it is announced here is not ours.

## Bridge policy and CCIP rehearsal — 2026-08-28
- **Migration**: one migrator, on Ethereum, against the original HANU (`0x72e5…dbcc0`). Holders on
  Polygon, BSC, Base, Solana or any other chain return to Ethereum through the bridge they used
  (Polygon PoS, the Goji bridge, Wormhole) and migrate there; there is no deadline.
- **Bridging v2**: Chainlink CCIP (Burn & Mint) on every chain HANU v2 lives on. Wormhole is not used
  for v2; the Goji relayer bridge is a fallback only.
- **Rehearsal**: a trial HANU v2 at the same address on Robinhood Chain Testnet and Ethereum Sepolia
  (`0xB9C034213A5D05D4c290701fCA579A8D12F8d0F1`, testnet only, no value) completed a CCIP round trip:
  1,000 HANU Robinhood → Sepolia (message `0x6eef…bbd1`) and back (`0xecf2…791e`). Supply on each
  side burned and minted exactly, and the pools' mint allowances returned to their starting values.

## Testnet, future-proofing redeploy + public metadata (Robinhood Chain Testnet, chain id 46630) — 2026-08-28
What changed for holders: a fee bucket can now burn instead of paying a wallet; transfer restrictions
(if ever enabled) can be directional; allowlist memberships can expire; lawful-order holds can cover
part of a balance instead of the whole address; contract wallets can use gasless approvals; audited
third-party bridges can be plugged in by role; the token can register with the canonical Arbitrum bridge.
Bridge operations gained a guardian role that can only tighten. Every hook was chosen so that no
foreseeable scenario needs a v3 token (ADR 0010).

Token metadata (ERC-7572) is now live at the fixed URL `https://gojicrypto.com/hanu/v2/contract.json`,
served from Goji's own infrastructure, pinned on Goji's IPFS node (directory CID `bafybeib7zxlh6qxb55eqaqfvhn3gtlsizwi7jb47lhysqiuxmwnffwq6ua`, file CID `bafkreibfotzzmiqtibh4qrjnu6zm6ujhcd25qwmzzceaalk4m6x4knbfce`)
and resolvable through DNSLink (`_dnslink.gojicrypto.com`). Version 1.0.0-testnet.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0xbAC9Edf9d813a7165202e8e3e837Aa2Fd5D43fD9` |
| Mint controller | `0x23E76a330587B88b74496E319C1b128a133fad8C` |
| Fee policy (tax = 0, three buckets) | `0x74aC1534128aa00069483Ae6FbDDD75C5d4fEEcC` |
| v1 → v2 migrator (lock) | `0x53dF90478385aaD73670c0722f036Dc7b83552CA` |
| Lock-release bridge | `0xe0a153BEa0194F410A2E871742dfEdbE83C98Ac1` |
| Compliance module | `0xff381AC706A6a4fd79a160A92CEd5Aac948f74d0` |
| Mock v1 (testnet only) | `0xbDf2C054eAb2Af7dc77b6fD38d7F4338C51553E1` |

## Testnet, mint-controls redeploy (superseded) — 2026-08-28
Two more holder-facing controls:
- **Every privileged action now carries a written reason on-chain** (mint proposals, approvals, fee
  changes, parameter changes, pauses, freezes, governance actions). Empty reasons are rejected.
- **Minted tokens can only ever land in approved company wallets** (treasury, migration float,
  bridge float). Adding a wallet to that list takes a public two-day delay; a compromised mint key
  cannot route new tokens anywhere else. The mint process lives in its own contract
  (`MintController`) so it can be replaced without touching the token.
Addresses below supersede all earlier testnet sets.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0xfCeD5f5bbD194c104949F629C19d65cE54C2BaB1` |
| Mint controller | `0x659b79f1649a82499e8Bb23011953AEcE1223915` |
| Fee policy (tax = 0, three buckets) | `0x77c78cA27607FE9f94F5c418C198d78526ae8D30` |
| v1 → v2 migrator (lock) | `0xa9eaaC624C81303DACC0D0096Bdd55124d4d6cFD` |
| Lock-release bridge | `0xB4C15e39Dd7f716D09da7EADC9920aA32Df73437` |
| Compliance module | `0xaac432934e2c632c7DB783D2d31E334f6AB3ED4a` |
| Mock v1 (testnet only) | `0x817A759Aa447777eF386C357858c2c5f90af60Ff` |

## Testnet, compliance-controls redeploy (superseded) — 2026-08-28
HANU v2 now carries lawful-order controls, designed so they can never be used quietly:
- A compliance officer can place a **provisional freeze** on an address (no sending, no receiving),
  always with an order reference on-chain. It **thaws by itself after 14 days** unless the company
  multisig ratifies it with public notice.
- **Seizure or destruction of funds is possible only from a ratified freeze**, only after a public
  announcement and a seven-day delay, and every such action is published here first.
- An **allowlist mode** exists for the case that HANU is ever brought under a securities regime; it is
  off, and switching it on requires fourteen days of public notice.
- The process lives in a separate, replaceable module; the freeze state lives in the token, so a
  process change can never silently freeze or thaw anyone.
Addresses below supersede all earlier testnet sets.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0xb380aF161605E8daCc86087501edbE27F771b4eb` |
| Fee policy (tax = 0, three buckets) | `0x9a3fcb38e1b098597f6aBAa124E743A348600c04` |
| v1 → v2 migrator (lock) | `0x1E5C33E30e5E6846744964708Cf476420B3d1Ca8` |
| Lock-release bridge | `0xBc3Af89EF41b2017e47B95848AE3e64c03D464A2` |
| Compliance module | `0x0784AFCaeDadF280B66d3f0b40a6acd24f2fE7C7` |
| Mock v1 (testnet only) | `0x003e6be78093D8676401e52193926Df21DcBE025` |

## Testnet, governed-parameters redeploy (superseded) — 2026-08-28
The protections that were hard-coded (fee ceiling, pause cap and cooldown, fee and policy delays,
governance delays, bridge withdrawal delay and refill period) are now tunable by the company
multisig **inside fixed fences**: any change that weakens a protection is announced and waits at
least one day; any change that strengthens one applies at once. The absolute fee fence is 15%; the
live ceiling remains 10%. Addresses below supersede all earlier testnet sets.

| Contract | Address |
|---|---|
| Hanu Yokia v2 (HANU) | `0xd0aEfA9321C570BBb33065dd14D9f10Dc9476C19` |
| Fee policy (tax = 0, three buckets) | `0x270e9ccd8B4769cA838a8C229871aEd594C01894` |
| v1 → v2 migrator (lock) | `0xbfde67f8cf5Cf7f3639B9b73c1a7DFE12a359389` |
| Lock-release bridge | `0xeB6f446b49b3e963cDB35E8a02c07d995cC13F0e` |
| Mock v1 (testnet only) | `0x62FE2a1D847cb4d311A77a0c6Bd0FC80a2E2d0b0` |

## Testnet, post-audit redeploy (superseded) — 2026-08-28
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
