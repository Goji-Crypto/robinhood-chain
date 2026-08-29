# Security policy

HANU v2 and the read-only stock token dashboard are built in the open and we want to hear about
weaknesses before anyone else does.

## Reporting a vulnerability

Please do not open a public issue for a security problem.

- Use GitHub's private vulnerability reporting on this repository (Security tab, "Report a
  vulnerability"). It reaches the maintainers only.
- Include: the affected contract or component and its address or commit, the steps or a proof of
  concept (a Foundry test is ideal), and the impact as you understand it.
- We acknowledge within 3 business days and keep you updated while we work on a fix.

## Scope

- HANU v2 contracts (the token, FeePolicy, MintController, ComplianceModule, HanuMigrator, the
  Chainlink CCIP pool wiring, and the fallback lock-release bridge). Source and design records are in
  the private engineering repository; audited releases are published here with their commit hashes.
- The public metadata at `https://gojicrypto.com/hanu/v2/contract.json` and its IPFS snapshots.
- The stock token dashboard (read-only; it never handles keys or funds).

Out of scope: third-party infrastructure (Chainlink CCIP, the chains themselves, OpenZeppelin),
denial-of-service against public RPC endpoints, and social engineering.

## Disclosure

We ask for 90 days from acknowledgement before public disclosure, or less once a fix is deployed and
announced in `CHANGELOG.md`. We credit reporters in the changelog unless they prefer otherwise.

## Audits

The contract set goes through an independent audit before any mainnet deployment; the final report
is published in this repository. Until then, every deployment is on the Robinhood Chain testnet and
is listed in `CHANGELOG.md` with its addresses.
