# Marketing direction

Version 0.1 (draft for review), 2026-08-28.

## The one-line story
Goji brings its own token and its own market lens to the chain where tokenized stocks live.

## Why Robinhood Chain
- It is where tokenized equities are actually issued and traded around the clock, with a public,
  keyless data API and standard ERC-20 tokens anyone can build on.
- It is an Ethereum L2 (Arbitrum technology) with ETH gas, so Goji tooling and audits carry over.
- Being early and credible on a chain with real-world assets is a stronger position than being
  late on a general-purpose chain.

## Product 1: Goji Stock Deck (read-only dashboard)

**Audience.** Non-US crypto-native investors and analysts in eligible regions (EU/EEA, LATAM,
APAC) who hold or watch tokenized stocks and want a fast, honest view without a broker login.
Secondary: developers exploring stock token integrations.

**Promise.** See the whole tokenized-stock market on one screen, priced live, with the on-chain
multiplier that explains every split and dividend, plus any wallet's holdings, without connecting
a wallet.

**Messaging pillars**
1. Read-only by design. No trading, no custody, no signing. Trust follows from what we cannot do.
2. On-chain truth. The multiplier, supply, and contract identity come from the chain and the
   explorer, not from a screenshot.
3. Region-honest. The banner tells you plainly whether stock tokens are offered where you are, and
   we never pretend otherwise.

**Naming.** Working name "Goji Stock Deck". Alternatives to test: "Goji Ticker", "Goji Ledger View",
"Deck by Goji". The name must not contain "Robinhood" or suggest a partnership.

**Launch surface.** A subdomain of gojicrypto.com, a launch thread with three screenshots (market,
asset drawer, holdings), a short explainer on what the multiplier is, and a "how to verify a stock
token address" post.

## Product 2: Hanu Yokia v2

**Audience.** Existing HANU holders on Ethereum and Polygon (and other v1 chains once confirmed),
the Goji community, and DeFi users on Robinhood Chain looking for ecosystem tokens.

**Promise.** Same token, better home. HANU moves to a faster, cheaper chain with clear rules:
every admin power is a named role held by the company multisig, every parameter change is
announced first, and v1 tokens you migrate stay locked and visible on-chain.

**Messaging pillars**
1. Migration you can verify. Lock v1, receive v2 one-to-one. Locked v1 can only leave the migrator
   after a public seven-day notice.
2. No backdoors, and no quiet powers. v1's owner-only burn is gone. v2 has capped minting with
   multi-signer approval and a delay, a fee switch that starts at zero with a hard ceiling, and a
   pause that expires on its own. Lawful-order controls exist (freeze, seizure) but only under a
   published order reference, provisional unless the multisig ratifies with notice, and seizure only
   after a public seven-day announcement.
3. Built to travel. A Goji-operated bridge with pre-funded floats and per-day limits, and an
   upgrade path to a LayerZero OFT when the time is right.

**What we will not say.** Price targets, "stable", "guaranteed", "backed by stocks", "no blacklist"
(we have lawful-order freezes; say what they are), or anything that implies HANU is a security or is
tied to Robinhood.

## Compliance guardrails for all material
- No Robinhood logos, wordmarks, or brand colors; the network is named in plain text only.
- Every stock token page carries the eligibility banner and the issuer disclaimer.
- Never encourage VPN use or any workaround of regional restrictions.
- Contract addresses are published only in this repo and the block explorer; never in DMs.
- Marketing copy for HANU v2 is reviewed against the legal questions list before any campaign.

## Visual direction
Goji's existing identity (the owl mark, coin logos in `Goji-Crypto/branding`) on a dark,
data-dense surface. Isometric or tile-based illustration for "the chain map" motifs, monospace
numerals for anything financial, and a restrained accent (Goji green or teal) with status colors
reserved for eligibility and halts.
