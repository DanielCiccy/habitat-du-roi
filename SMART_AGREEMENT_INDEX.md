# Smart Agreement Indexed: an hybrid approach to Web3 contractualization

## Context

As part of the **Habitat du Roi®** project, we have designed an open and original approach to contractualization.  
Rather than coding complex logic directly into a blockchain-based smart contract, we chose a more accessible, flexible, and interoperable path:

- Contracts are **authored and enriched off-chain** (via a dedicated interface).
- A **SHA-256 hash** is computed to create a unique, immutable fingerprint.
- Only this hash is **anchored on the Solana blockchain** through a signed transaction (`txnId`).
- The full content of the contract is stored off-chain, yet cryptographically verifiable through its hash.

> We call this method:
> **Smart Agreement Indexed**

---

## Why this approach?

Unlike classical smart contracts (on Ethereum, Solana, etc.), which are **fully on-chain programs**, our model prioritizes:

- **Freedom of expression**: contracts written in natural or structured language, enriched with attachments (PDF, 3D files, legal documents).
- **Cost efficiency**: no execution or deployment costs—only a standard transaction.
- **Interoperability by design**: the hash is universal and can be verified across chains.
- **User accessibility**: ideal for non-technical actors (local authorities, developers, citizen groups).

---

## Interchain Portability

Because only the hash is stored on-chain:

- It can be **replicated and verified** on other protocols (Solana, Ethereum, Starknet, etc.).
- It enables **bridging** through oracles or simple relay systems.
- It provides **proof of authorship, authenticity, and integrity** without locking logic into one infrastructure.

This makes it compatible with multi-chain strategies and institutional standards.

---

## Security and Sovereignty

The Smart Agreement Indexed model ensures:

- **Integrity**: the hash proves that the contract has not been altered.
- **Structured storage**: contract metadata and contents are stored in a relational database, indexed by `txnId`.
- **Sovereignty**: local authorities or project initiators retain full control over the content and governance logic of their agreements.

---

## A Web3 Philosophy Rooted in Reality

We believe Web3 can serve **collective empowerment** when placed at the service of real-world needs:

- A contract remains a **human agreement**, not just executable code.
- Blockchain provides **verification and anchoring**, not semantic constraints.
- The balance between transparency, freedom, and rigor is at the core of this model.

---

## Outlook

The **Smart Agreement Indexed** model serves as a **bridge between Web2 and Web3**, enabling real-world contractual logic to meet cryptographic integrity.

It is applicable beyond real estate: to cultural commons, decentralized governance, and collective projects where trust and transparency are key.

**Habitat du Roi®** introduces this model as a foundational tool for **structuring projects around collective intelligence and solvable demand**—anchored, verified, and yet open.

---

[← Back to MODELS_DETAILS.md](./MODELS_DETAILS.md)

For more about how collective decisions are handled, see [VOTE_MODEL_PROCESS.md](./VOTE_MODEL_PROCESS.md).


**#CredimusInOptimumHumanis**  
*We believe in the best of each man.*
