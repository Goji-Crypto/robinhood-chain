# Goji Crypto on Robinhood Chain

Public home for the marketing direction and product wireframes of two Goji Crypto products on
Robinhood Chain (an Ethereum L2 built on Arbitrum technology, chain id 4663):

1. **Goji Stock Deck** (working name): an independent, read-only market dashboard for the tokenized
   stocks and ETFs issued on Robinhood Chain. Prices, on-chain corporate-action multipliers,
   corporate actions, and read-only holdings for any address. It does not trade.
2. **Hanu Yokia v2 (HANU)**: the next version of the HANU token, issued natively on Robinhood Chain
   and managed by Goji Crypto Holdings LLC, with a lock-based migration path from v1 on the chains
   where v1 lives today.

| Folder | Contents |
|---|---|
| `docs/marketing-direction.md` | Positioning, audiences, messaging pillars, naming, compliance guardrails |
| `wireframes/` | Low-fidelity screen flows (HTML source + PNG exports) for both products |
| `CHANGELOG.md` | Public notices for parameter changes (fee switch, bridge limits, migration windows) |

Architecture decisions and code live in a separate private repository.

## Important notices
- Goji Crypto is **not affiliated with, endorsed by, or operated by Robinhood**. Robinhood names and
  marks belong to their owners and are used only to identify the network.
- Stock Tokens are tokenized debt securities issued by Robinhood Assets (Jersey) Limited. They are
  **not available to US persons** or in restricted jurisdictions (Canada, the United Kingdom,
  Switzerland, and sanctioned countries, per the issuer's published list). Nothing in this repository
  is an offer, solicitation, or investment advice.
- HANU is a utility token of the Goji ecosystem. Contract addresses will be announced only here and
  on the Goji Crypto channels; verify addresses on the block explorer before interacting.
