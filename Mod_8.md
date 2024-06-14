# Module 8 Cheatsheet

## Cryptographic Hash Functions

### Overview
- **Definition**: Takes a variable-sized input message and produces a fixed-sized output (hash value or message digest).
- **Properties**:
  - Non-invertible: Hard to reverse.
  - Collision-resistant: Hard to find two different inputs with the same output.

### Popular Hash Functions
- **MD5**: 128-bit hash, no longer secure.
- **SHA-1**: 160-bit hash, not recommended for collision resistance.
- **SHA-2 Variants**:
  - **SHA-256**: 256-bit hash.
  - **SHA-512**: 512-bit hash.
  - Other variants: SHA-224, SHA-384.

## Hashing Applications
- **User Account Registration and Authentication**: Verifies user credentials.
- **File Integrity Verification**: Ensures files have not been altered.
- **Message Authentication Codes (MACs)**: Verifies message integrity and authenticity.

## Digital Signatures

### Overview
- **Purpose**: Verifies author, date, and time of a signature; authenticates message contents; can be verified by third parties.
- **Properties**:
  - Verifiable by anyone.
  - Ensures non-repudiation.

### Digital Signature Process
1. **Signing**:
   - Sender encrypts hash of the message with their private key.
2. **Verification**:
   - Receiver decrypts the hash with the sender's public key and compares it with the hash of the received message.

## Public-Key Certificates

### Certificate Authorities (CAs)
- **Role**: Authenticate public keys by signing certificates.
- **Hierarchy**:
  - **Root CAs**: Top-level, trusted by default.
  - **Intermediate CAs**: Certified by root CAs.
- **Types of Certificates**:
  - **Extended Validation (EV)**: Rigorous identity verification.
  - **Organization Validation (OV)**: Moderate identity checks.
  - **Domain Validation (DV)**: Verifies control of the domain.

### Certificate Revocation
- **Reasons**: Compromised keys, no longer certified.
- **Certificate Revocation List (CRL)**: List of revoked certificates maintained by CAs.

## Key Exchange Protocol

### Direct Key Exchange
1. **Party A**: Generates public/private key pair, sends public key to B.
2. **Party B**: Generates secret session key, encrypts it with A's public key, sends it to A.
3. **Party A**: Decrypts the session key with their private key.
4. Both parties use the session key for secure communication.

### Man-in-the-Middle Attack
- An attacker intercepts and modifies messages between two parties during key exchange.

## Summary
Understanding cryptographic hash functions, digital signatures, and public-key certificates is crucial for secure communication. Hash functions ensure data integrity, digital signatures provide non-repudiation, and certificates authenticate public keys in a hierarchical structure managed by CAs.
