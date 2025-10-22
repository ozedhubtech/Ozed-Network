Data Models & API Specifications

1. Data Model
Verifiable Data Object (VDO) Schema

{
  "data_id": "unique_hash_identifier",
  "owner": "wallet_address",
  "metadata": {
    "name": "project_document.pdf",
    "type": "file/document/record",
    "category": "enterprise/personal/public",
    "timestamp": "block_number",
    "access_level": "private/public/shared"
  },
  "storage": {
    "cid": "ipfs_cid_or_filecoin_link",
    "size": "2.4MB"
  },
  "proof": {
    "hash": "sha256_hash",
    "signature": "digital_signature",
    "block_reference": "block_number"
  },
  "status": "active/revoked/expired"
}
Explanation:
- The data_id acts as the immutable on-chain reference.
- The owner corresponds to the user's Polkadot wallet address.
- The proof component links to the cryptographic validation of the data.
- Storage.cid connects on-chain data to off-chain storage (IPFS/Filecoin)


2. API Specifications
These APIs represent the intended functionality exposed to clients and external systems.

a. Register Data
Registers a new data object on-chain and stores its reference.

POST /api/v1/registerData

Request:
{
  "owner": "wallet_address",
  "cid": "ipfs_hash",
  "metadata": {
    "name": "record_name",
    "type": "document",
    "access_level": "private"
  }
}

Response:
{
  "status": "success",
  "data_id": "unique_hash_identifier",
  "transaction_hash": "0xabc123..."
}

b. Verify Data Integrity
Verifies the authenticity of a data entry based on its hash.

GET /api/v1/verifyData/{data_id}

Response:
{
  "data_id": "unique_hash_identifier",
  "verified": true,
  "owner": "wallet_address",
  "block_reference": 452100,
  "timestamp": "2025-10-21T10:45:00Z"
}

c. Grant / Revoke Access
Allows data owners to grant or revoke permissions.

POST /api/v1/grantAccess

Request:
{
  "data_id": "unique_hash_identifier",
  "delegate": "receiver_wallet_address",
  "permission": "read/write"
}
POST /api/v1/revokeAccess

Request:
{
  "data_id": "unique_hash_identifier",
  "delegate": "receiver_wallet_address"
}

d. Retrieve Data Metadata
Fetches metadata for a given data ID.

GET /api/v1/metadata/{data_id}

Response:
{
  "data_id": "unique_hash_identifier",
  "metadata": {
    "name": "project_document.pdf",
    "type": "document",
    "timestamp": "block_number"
  },
  "status": "active"
}



=============================================================
Current Development Stage
At this stage, these data models and APIs are being prototyped conceptually within a Substrate development environment. The initial implementation will focus on:
- Defining the Verifiable Data Object (VDO) structure as a Substrate pallet.
- Implementing the registerData and verifyData functions.
- Integrating IPFS for decentralized off-chain storage.

Future Expansion
Future iterations will include:
- Governance APIs for on-chain proposal and voting.
- Cross-chain APIs to share data proofs with other Polkadot parachains.
- Identity APIs linking user credentials to verified data ownership (via DID or SSI frameworks).

