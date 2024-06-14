# Module 5 Cheatsheet

## Public-Key Cryptography

### Overview
- **Public-Key Cryptography**: Uses two keys – a public key and a private key.
  - **Asymmetric**: Parties are not equal.
  - Complements, rather than replaces, private-key cryptography.
- **Developed to Address**:
  - **Key Distribution**: Secure communication without a Key Distribution Center (KDC).
  - **Digital Signatures**: Verify message integrity and origin.
- **Inventors**: Whitfield Diffie and Martin Hellman (1976).

### Public-Key Encryption
- Anyone knowing the public key can encrypt messages or verify signatures but cannot decrypt messages or create signatures.
- **Confidentiality**: Ensured as only the private key can decrypt the message encrypted with the public key.

### Hybrid Cryptosystem
- Uses public-key cryptography to share a symmetric key, then shifts to symmetric-key cryptography for data encryption.

## Number Theoretic Concepts

### Divisors
- **Divisor**: Non-zero number \( b \) divides \( a \) if \( a = mb \) for some integer \( m \).
- **Notation**: \( b|a \) means \( b \) is a divisor of \( a \).

### Properties of Divisibility
- If \( a|1 \), then \( a = \pm 1 \).
- If \( a|b \) and \( b|a \), then \( a = \pm b \).
- Any \( b \neq 0 \) divides 0.
- If \( a|b \) and \( b|c \), then \( a|c \).
- If \( b|g \) and \( b|h \), then \( b|(mg + nh) \) for arbitrary integers \( m \) and \( n \).

### Division Algorithm
- **Definition**: For \( a = qn + r \), \( 0 \leq r < n \), \( q = \text{floor}(a/n) \).
- **Modulo Operator**: \( a \mod n \) is the remainder when \( a \) is divided by \( n \).

### Modular Arithmetic
- **Operations**:
  - \( (a + b) \mod n = [(a \mod n) + (b \mod n)] \mod n \)
  - \( (a - b) \mod n = [(a \mod n) - (b \mod n)] \mod n \)
  - \( (a \times b) \mod n = [(a \mod n) \times (b \mod n)] \mod n \)

### Greatest Common Divisor (GCD)
- **Definition**: Largest integer that divides both \( a \) and \( b \).
- **Relatively Prime**: Two numbers are relatively prime if their GCD is 1.

### Euclidean Algorithm
- Efficient way to find GCD.
- **Algorithm**: \( \text{GCD}(a, b) = \text{GCD}(b, a \mod b) \).

### Extended Euclidean Algorithm
- Calculates not only GCD but also integers \( x \) and \( y \) such that \( ax + by = \text{GCD}(a, b) \).
- Useful for finding modular inverses.

### Finding Inverses
- **Extended Euclidean Algorithm**: Finds multiplicative inverses in finite fields.
- **Example**: Finding inverse of 550 in GF(1759).

## Highlights
- Public-Key Cryptography: Uses asymmetric keys for encryption and digital signatures.
- Hybrid Cryptosystem: Combines public-key and symmetric-key cryptography.
- Number Theory: Divisors, modular arithmetic, GCD, and Euclidean algorithm are fundamental concepts.

## Summary
Understanding public-key cryptography and the underlying number theoretic concepts is crucial for implementing secure communication systems. These concepts provide the foundation for encryption, digital signatures, and key management.
