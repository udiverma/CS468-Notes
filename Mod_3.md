# Module 3 Cheatsheet

## AES Overview
- **AES (Advanced Encryption Standard)**: Block cipher with 128-bit blocks.
- **Key Lengths**: 128, 192, or 256 bits.
- **Rounds**:
  - 10 rounds for 128-bit keys.
  - 12 rounds for 192-bit keys.
  - 14 rounds for 256-bit keys.
- **Round Structure**: Substitution, permutation, mixing, round key addition.
- **Security**: Remains theoretically secure due to high time complexity.

## Block Ciphers
- **Long Messages**: Vulnerable to periodicity and repetitive structures.

## Encryption Modes of Operation
- **Fixed Size Blocks**: Encrypt fixed size blocks; handle arbitrary data with different modes.
- **Modes**:
  - **ECB (Electronic Codebook)**:
    - Encrypts each block independently.
    - **Advantage**: Simple.
    - **Disadvantage**: Not secure for long messages.
  - **CBC (Cipher Block Chaining)**:
    - XORs plaintext block with previous ciphertext block before encryption.
    - **Advantage**: Masks repetitive patterns.
    - **Disadvantage**: IV must be known, changes propagate.
  - **CFB (Cipher Feedback)**:
    - Converts block cipher into a stream cipher.
    - **Advantage**: Suitable for stream data.
    - **Disadvantage**: Errors propagate.
  - **OFB (Output Feedback)**:
    - Encrypts an IV, then XORs with plaintext.
    - **Advantage**: Bit errors do not propagate.
    - **Disadvantage**: Synchronization needed.
  - **CTR (Counter)**:
    - Encrypts counter values.
    - **Advantage**: Fast, suitable for parallel processing.
    - **Disadvantage**: Synchronization needed.

## Stream Ciphers
- **Operation**: Encrypts plaintext one byte at a time using a pseudorandom keystream.
- **Security**: Long period to prevent repetition.
- **Advantage**: Ideal for real-time data like audio and video.
- **Example**: RC4.

## Highlights
- AES: Secure due to complexity.
- Modes of Operation: ECB (simple but weak), CBC, CFB, OFB, CTR (better security for various uses).
- Stream Ciphers: Good for real-time data transmission.

## Summary
Understanding AES, its modes of operation, and stream ciphers is crucial for implementing secure communication systems. Each mode has specific advantages and limitations based on the data and transmission requirements.