CORE COMPONENTS
* a. Ozed Runtime (Blockchain Core)
  Built using Substrate FRAME.
  Implements custom pallets to handle:
  - Data Registration: Hashing and anchoring data records on-chain.
  - Data Verification: Ensuring data integrity via cryptographic proofs.
  - Access Control: Permissioned access using on-chain logic.
  - Governance: DAO-like structure for proposal, voting, and protocol upgrades.
  - Each pallet will follow Substrate’s modular design to ensure upgradability and interoperability.

* b. Data Layer
  Off-chain storage using IPFS/Filecoin for large data payloads.
  On-chain references store:
  - data_id (hash of content)
  - owner (wallet address)
  - metadata (data type, timestamp, access level)
  - cid (IPFS reference)
  
  Merkle proofs are used to validate integrity between the off-chain data and its on-chain reference.
  Flow:
  - User uploads data → IPFS generates CID.
  - System hashes the content → produces data_id.
  - Data metadata and CID are recorded in a Substrate pallet.
  - Verification queries can later re-hash content and confirm authenticity.

* c. Governance Layer
  - Based on a DAO-like model using FRAME Governance Pallets (for instance, collective, democracy, council ...).
  - Token-weighted or role-based voting depending on the data governance model.
  - Supports on-chain proposal submission, review, and parameter adjustment.
  Governance will oversee:
  - Approval of new data protocols or pallet updates.
  - Validator set management.
  - Fee structures and network upgrades.

* d. Interoperability Layer
  - Integrates with Polkadot for cross-chain data sharing.
  - Uses Substrate Bridge Pallets for communication with external chains.
  - Targets future deployment as a parachain to the Polkadot relay chain.
  Key objectives:
  - Enable other blockchains to query verified data states from Ozed Network.
  - Facilitate multi-chain data governance and trust interoperability.
  - Use XCM (Cross-Consensus Messaging) for cross-chain transactions and proof sharing.

* e. Identity & Access Layer
  Integrates Decentralized Identifiers (DIDs) for unique user and organization representation.
  Enables role-based permissions, allowing data owners to:
  - Grant or revoke access.
  - Create delegated roles (e.g., organization, validator, researcher).
  - Designed for compatibility with SSI (Self-Sovereign Identity) standards.

* f. Application / User Interface
  Frontend built using React + TypeScript + Polkadot.js API.
  Includes:
  - Dashboard: View registered data, proofs, and permissions.
  - Governance Console: Submit and vote on proposals.
  - Validator Panel: Manage node performance and staking.


CORE PROTOCOLS
| **Protocol**                   | **Purpose**                                          | **Mechanism**                         |
| ------------------------------ | ---------------------------------------------------- | ------------------------------------- |
| **Data Registration Protocol** | Registers verifiable data objects (VDOs)             | Hashing, IPFS CID, on-chain anchoring |
| **Data Verification Protocol** | Confirms data authenticity                           | Merkle proof comparison               |
| **Governance Protocol**        | Handles community voting and updates                 | FRAME democracy/council pallets       |
| **Access Control Protocol**    | Manages permission grants and revocations            | Role-based or token-based permissions |
| **Cross-chain Data Protocol**  | Enables interoperability with Polkadot/Kusama chains | XCM message passing                   |


ARCHITECTURE OVERVIEW
Layered Architecture
+--------------------------------------------------+
|                 - Application Layer              |
|  (Dashboard, Validator Console, Governance UI)   |
+--------------------------------------------------+
|        - Identity & Access Management Layer      |
|  (DIDs, role-based access, key management)       |
+--------------------------------------------------+
|             - Blockchain Runtime Layer           |
|  (Substrate FRAME, data pallets, governance)     |
+--------------------------------------------------+
|             - Interoperability Layer             |
|  (Polkadot relay, bridges, XCM protocols)        |
+--------------------------------------------------+
|            - Data & Storage Layer                |
|  (IPFS, Filecoin, off-chain workers)             |
+--------------------------------------------------+
|          - Infrastructure & Security Layer       |
|  (Nodes, libp2p, cryptography, auditing)         |
+--------------------------------------------------+


DEPLOYMENT ARCHITECTURE
Stage 1:
- Substrate standalone chain (testnet).
- IPFS integration for storage.
- PoC for data registration and verification.
Stage 2:
- Governance and access control pallets.
- API and UI layer integration.
- Launch on Kusama for real-world testing.
Stage 3:
- Cross-chain bridge deployment.
- Parachain registration on Polkadot.
- On-chain governance activation.


SECURITY and VALIDATION
- Cryptography: SHA-256, Ed25519, and Merkle proofs for integrity.
- Node validation: NPoS for consensus and validator selection.
- Auditing: Regular smart contract and runtime module reviews.
- Data privacy: Encryption of sensitive metadata and private records.


LIMITATIONS
At the preliminary stage, the network will:
- Focus on data management and governance, not token economics.
- Use external decentralized storage (not native storage).
- Limit smart contract deployment to controlled modules during MVP testing.
