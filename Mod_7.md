# Module 7 Cheatsheet

## Diffie-Hellman Algorithm for Key Exchange

### Overview
- **Diffie-Hellman Key Exchange**: First public-key scheme, proposed by Diffie and Hellman in 1976.
- **Purpose**: Securely exchange a secret key used for subsequent encryption.
- **Functionality**: Based on exponentiation in a finite field (modulo a prime).

### Key Concepts
- **Public-Key Distribution**: Establishes a common key known only to the participants.
- **Security**: Relies on the difficulty of computing discrete logarithms.

### Algorithm Steps
1. Agree on a large prime number \( p \) and a base \( g \).
2. Each participant selects a private key: \( a \) for Alice and \( b \) for Bob.
3. Compute public keys:
   - Alice: \( A = g^a \mod p \)
   - Bob: \( B = g^b \mod p \)
4. Exchange public keys.
5. Compute shared secret key:
   - Alice: \( K = B^a \mod p \)
   - Bob: \( K = A^b \mod p \)

### Example
- **Prime \( p \)**: 353
- **Base \( g \)**: 3
- **Private Keys**:
  - Alice: \( a = 97 \)
  - Bob: \( b = 233 \)
- **Public Keys**:
  - Alice: \( A = 3^{97} \mod 353 = 40 \)
  - Bob: \( B = 3^{233} \mod 353 = 248 \)
- **Shared Secret Key**:
  - Alice: \( K = 248^{97} \mod 353 = 160 \)
  - Bob: \( K = 40^{233} \mod 353 = 160 \)

## Security Considerations

### Man-in-the-Middle Attack
- An attacker can intercept and modify the exchanged keys.

### Security Measures
- Use large prime numbers (at least 1024 bits) to ensure security.

### Practical Implementation
- Requires "multiple precision" software to handle large integers.

## Highlights
- Diffie-Hellman: Establishes a shared secret key using public-key cryptography.
- Security: Based on the difficulty of computing discrete logarithms.
- Example: Demonstrates the key exchange process and shared secret computation.

## Summary
Understanding the Diffie-Hellman key exchange algorithm is crucial for secure key distribution in public-key cryptography. The security of the algorithm depends on the computational difficulty of discrete logarithms, making it a practical method for securely exchanging keys.
