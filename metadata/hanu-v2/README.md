# HANU v2 contract metadata (ERC-7572)

The token's `contractURI()` is fixed to `https://gojicrypto.com/hanu/v2/contract.json`. The document
behind it changes over time (mainnet addresses, disclosures, links); the URL never does.

## Publishing a new version
1. Edit `contract.json` here (bump `version`, set `updated`).
2. Compute the snapshot: `sha256sum contract.json` and pin the file to IPFS (Pinata, web3.storage, or a
   Goji-run node); record the CID and sha256 in `snapshot` and re-pin the final file.
3. Deploy to `https://gojicrypto.com/hanu/v2/contract.json` (short cache, ETag) and update the
   DNSLink record `_dnslink.gojicrypto.com` to the new CID so IPFS gateways serve the same document.
4. Governance emits the on-chain `ContractURIUpdated()` event (`announceContractURI(reason)`) so
   wallets and explorers re-fetch.
5. Add a CHANGELOG entry with the version and the CID.

## Why not `ipfs://CID` in the token
A CID changes with every edit; the URL is bytecode. IPFS is used for immutable, verifiable snapshots
of each version, not as the pointer. `ipns://` was rejected for weak wallet support and key overhead.
