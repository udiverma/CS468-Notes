# Module 6 Cheatsheet

## Public-Key Cryptography

### Overview
- **Public-Key Cryptography**: Uses two keys – a public key and a private key.
  - **Asymmetric**: Public key for encryption/verification, private key for decryption/signature creation.
- **Developed to Address**:
  - **Key Distribution**: Secure communication without a Key Distribution Center (KDC).
  - **Digital Signatures**: Verify message integrity and origin.
- **Inventors**: Whitfield Diffie and Martin Hellman (1976).

### Key Concepts
- **Trapdoor One-Way Function**:
  - **One-Way Function**: \( Y = f(X) \) is easy; \( X = f^{-1}(Y) \) is infeasible.
  - **Trapdoor**: \( Y = f_k(X) \) is easy if \( k \) and \( X \) are known; \( X = f_k^{-1}(Y) \) is easy if \( k \) and \( Y \) are known.

### Security
- Security relies on the infeasibility of deriving the private key from the public key.
- Public-key schemes use large key sizes (>512 bits) to ensure security.

## RSA (Rivest-Shamir-Adleman)

### Key Generation
1. Select two large primes \( p \) and \( q \).
2. Compute \( n = pq \) and \( \phi = (p-1)(q-1) \).
3. Choose \( e \) such that \( \text{gcd}(e, \phi) = 1 \).
4. Compute \( d \) such that \( e \cdot d \equiv 1 \mod \phi \).
5. **Public Key**: \( (e, n) \).
6. **Private Key**: \( (d, n) \).

### Encryption/Decryption
- **Encrypt**: \( C = M^e \mod n \).
- **Decrypt**: \( M = C^d \mod n \).

### Example
- Primes: \( p = 17 \), \( q = 11 \).
- \( n = pq = 187 \), \( \phi = 160 \).
- \( e = 7 \), \( d = 23 \).
- **Public Key**: \( (7, 187) \).
- **Private Key**: \( (23, 187) \).

### Fast Exponentiation
- Algorithm to efficiently compute \( a^b \mod n \).

## Public-Key Applications

### Uses
- **Encryption/Decryption**: Ensures confidentiality.
- **Digital Signatures**: Provides authentication.
- **Key Exchange**: Securely exchange symmetric keys.

## RSA Attacks

### Types
- **Factoring**: Factor \( n \) to find \( p \) and \( q \).
- **Timing Attacks**: Analyze time taken for decryption to reconstruct \( d \).

## Highlights
- Public-Key Cryptography: Asymmetric keys for encryption and digital signatures.
- RSA: Most widely used public-key scheme, based on the difficulty of factoring large numbers.
- Key Management: Public key for encryption, private key for decryption.

## Summary
Understanding public-key cryptography, especially RSA, is crucial for implementing secure communication systems. Key concepts include the use of asymmetric keys, trapdoor one-way functions, and the importance of large key sizes for security.
