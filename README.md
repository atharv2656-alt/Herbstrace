# HERBTRACE — Blockchain-Powered Botanical Traceability for Ayurvedic Herbs

**Team**: ROGUE LOGIC  
**Members**: Ekansh Kumar, Atharv Roy  
**Event**: Elite Coders CodeSprint 2026 — National Hackathon Prototype

---

## 1. Executive Summary

HERBTRACE connects every stage of the Ayurvedic botanical supply chain—from wild collection or farm harvest to final consumer formulation—using GPS geo-tagging, cryptographic SHA-256 off-chain document hashing, and a permissioned Polygon-compatible EVM smart contract (`HerbTraceRegistry.sol`).

### Scientific & Legal Integrity Principle
HERBTRACE strictly distinguishes between **recorded provenance** and biological authentication:
- **What HERBTRACE proves**: A batch record was created at a specific timestamp, linked to specific GPS coordinates, transferred through an unbroken chain of authorized custodians, linked to specific laboratory quality certificates (via SHA-256 digest), and incorporated into a specific finished formulation lot.
- **What requires physical verification**: Plant species identity, harvest site authenticity, and chemical purity rely on field inspection and NABL/AYUSH laboratory assays (`HPLC`, `GC-MS`, `Heavy Metal Screen`), whose tamper-evident hashes are anchored on-chain.

---

## 2. Repository Structure

```text
herbtrace-fullstack/
├── package.json                  # Monorepo scripts (dev, seed, test, deploy)
├── .env.example                  # Safe environment variable template
├── contracts/                    # Solidity Smart Contract & Hardhat suite
│   ├── contracts/
│   │   └── HerbTraceRegistry.sol # Role-protected provenance smart contract
│   ├── scripts/
│   │   └── deploy.js             # Localhost & Polygon Amoy deployment script
│   ├── test/
│   │   └── HerbTraceRegistry.test.js
│   └── hardhat.config.js
├── backend/                      # Node.js + Express + MongoDB + Ethers API
│   ├── src/
│   │   ├── blockchain/           # Hybrid EVM relayer & SHA-256 hashing service
│   │   ├── config/               # Environment loader
│   │   ├── middleware/           # JWT authentication & RBAC authorization
│   │   ├── models/               # Mongoose schemas (User, Batch, Formulation, Product)
│   │   ├── routes/               # Versioned REST endpoints (/api/v1/*)
│   │   ├── seed/                 # Coherent multi-herb demonstration dataset
│   │   ├── tests/                # Automated backend & provenance test runner
│   │   └── validators/           # Input & regulator compliance rule validators
│   └── package.json
├── frontend/                     # Responsive Web Application (Canvas + Vite)
└── docs/
    ├── ARCHITECTURE.md
    ├── API.md
    ├── BLOCKCHAIN.md
    ├── SETUP.md
    └── DEMO.md
```
