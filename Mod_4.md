# Module 4 Cheatsheet

## Random Numbers in Cryptography
- **Uses**: Nonces, session keys, public key generation, keystreams for one-time pads.
- **Requirements**:
  - **Randomness**: Uniform distribution, independence.
  - **Unpredictability**: Future values cannot be predicted from previous values.

## True Random Number Generator (TRNG)
- **Entropy Source**: Physical processes (e.g., radioactive decay, keystroke timing).
- **Processing**: Converts analog source to binary output, removes bias.
- **Examples**: Intel's thermal noise chip, LavaRnd project.

## Pseudorandom Number Generators (PRNGs)
- **Description**: Deterministic algorithms that simulate randomness.
- **Requirements**:
  - **Randomness**: Uniformity, scalability, consistency.
  - **Unpredictability**: Forward and backward unpredictability.
- **Testing**: NIST SP 800-22 includes tests like Frequency Test, Runs Test, Maurer’s Universal Statistical Test.

## Using Block Ciphers as PRNGs
- **Cryptographic Applications**: Generate random numbers for session keys.
- **Modes**:
  - **CTR Mode**: \( X_i = E_K[V_i] \)
  - **OFB Mode**: \( X_i = E_K[X_{i-1}] \)

## Comparison of PRNGs and TRNGs
- **PRNGs**: Efficient, deterministic, periodic.
- **TRNGs**: Inefficient, non-deterministic, aperiodic.

## Stream Ciphers
- **Operation**: Process message bit by bit or byte by byte.
- **Keystream**: Pseudorandom and combined with plaintext using XOR.
- **Security**: Never reuse the stream key.

## The RC4 Stream Cipher Algorithm
- **Description**: Variable key length, byte-oriented stream cipher.
- **Initialization**: State Vector (S) and Key Scheduling Algorithm (KSA).
- **Pseudorandom Byte Stream Generation**: Produces keystream XORed with plaintext.
- **Security**: Secure if used correctly, but WEP protocol is vulnerable due to key reuse.

## WiFi Security Protocols
- **WEP, WPA, WPA2**: Encryption protocols for WiFi.
  - **WEP**: Uses RC4, considered insecure.
  - **WPA**: Improved over WEP but still not very secure.
  - **WPA2**: Uses AES, provides strong security.

## WPA2 Authentication
- **Modes**:
  - **WPA2-Personal**: For small office/home use.
  - **WPA2-Enterprise**: More secure, per-user authentication.
- **Authentication Services**: Based on IEEE 802.1x and EAP.

## RC4 in WEP
- **Key Management**: Combines a 24-bit IV and root key.
- **Security Issue**: Reusing keystreams allows plaintext recovery by XORing ciphertext streams.

## WPA2 Improvements
- **Encryption**: Uses AES in Counter mode (CTR).
- **Integrity Check**: Uses CBC-MAC (Cipher Block Chaining - Message Authentication Code).

## Highlights
- Random number generation is critical for cryptographic security.
- TRNGs and PRNGs serve different purposes.
- Stream ciphers like RC4 provide efficient encryption but require correct usage.
- WiFi security protocols have evolved, with WPA2 offering significant improvements.

## Summary
Understanding random number generation, stream ciphers, and secure communication protocols is crucial for cryptographic security. Correct implementation and avoiding key reuse are essential to prevent vulnerabilities.