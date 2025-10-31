Ozed Network is currently at the research and architecture stage.
For the grant we propose to deliver a Substrate-based PoC demonstrating immutable data anchoring,
IPFS integration, ownership & access controls, a minimal on-chain governance flow, and a reproducible demo (UI + verification API).
The PoC will include code, tests, documentation, and a demo script so evaluators can independently reproduce and audit the prototype.

## Overview
Ozed Network is a Layer 1 blockchain designed by **Ozed Hub Tech** to establish data sovereignty, transparency, and interoperability for individuals, enterprises, and organizations. 
This repository contains the research and PoC (Proof of Concept) phase of the Ozed Network project, built using **Substrate** and integrated with **IPFS** for decentralized data storage.

The PoC demonstrates:
- On-chain registration of **Verifiable Data Objects (VDOs)**
- Off-chain storage linkage (IPFS / Filecoin)
- Access control and ownership verification
- A minimal governance flow using Substrate’s on-chain voting


## Repository Structure
```
/repo-root
  /node          # Substrate node + runtime
  /pallets
    /vdo_registry
    /access_control
    /simple_governance
  /ui            # React + Polkadot.js interface
  /api           # Verification API (Node.js/Express)
  /docker        # Local setup (Substrate + IPFS)
  /docs          # Architecture, specs, diagrams
  README.md
```

---

## Getting Started

### Prerequisites
- [Rust](https://www.rust-lang.org/tools/install)
- [Substrate Node Template](https://docs.substrate.io/)
- [Docker](https://www.docker.com/)
- [Node.js](https://nodejs.org/en/)

### Setup
1. **Clone repository**
   ```bash
   git clone https://github.com/ozedhubtech/ozed-network-poc.git
   cd ozed-network-poc
   ```

2. **Run local node**
   ```bash
   ./scripts/start-node.sh
   ```

3. **Start IPFS node**
   ```bash
   docker compose up ipfs
   ```

4. **Start API and UI**
   ```bash
   cd api && npm install && npm start
   cd ui && npm install && npm run dev
   ```

---

## Demo Flow
1. Upload a file → IPFS generates a **CID**.  
2. Register the file → Ozed Network anchors CID + hash on-chain.  
3. Verify → API checks if file hash matches on-chain record.  
4. Governance → Propose and vote to change a sample parameter.  

---

## Goals of this PoC
- Validate Substrate integration and runtime pallets.
- Demonstrate the data registration and verification lifecycle.
- Provide a base for future parachain and Polkadot integration.
- Ensure security, reproducibility, and community testing.

---

## Next Steps
- Extend VDO pallet with more metadata fields.  
- Implement decentralized identity (DID) features.  
- Prepare deployment for Kusama testnet.  

---

## License
This project is released under the **Apache 2.0 License**.

---

© 2025 Ozed Hub Technology. All rights reserved.

