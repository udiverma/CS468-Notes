# Module 1 Cheatsheet

## Security Pillars
- **Confidentiality**: Access by authorized parties only.
- **Integrity**: Modification by authorized parties only.
- **Availability**: Accessible to authorized parties when needed.

## Attack Profiles
- **Passive Attacks**: Eavesdropping, Traffic analysis.
- **Active Attacks**: Masquerade, Replay, Modification, Denial of Service.

## Aspects of Security
- **Security Attack**: Compromises security.
- **Security Service**: Enhances security.
- **Security Mechanism**: Detects, prevents, or recovers from attacks.
- **Threat, Vulnerability, Risk**: Damage potential, Weakness, and Likelihood of threat exploitation.

## Security Services (X.800)
- **Authentication**: Assurance of identity.
- **Access Control**: Prevention of unauthorized use.
- **Data Confidentiality**: Protection from unauthorized disclosure.
- **Data Integrity**: Assurance data is unaltered.
- **Non-Repudiation**: Prevent denial of communication.
- **Availability**: Resources are accessible when needed.

## Cryptography Terminology
- **Plaintext**: Original message.
- **Ciphertext**: Coded message.
- **Cipher**: Encryption algorithm.
- **Key**: Info used in cipher.
- **Encrypt**: Convert plaintext to ciphertext.
- **Decrypt**: Convert ciphertext to plaintext.

## Types of Encryption
- **Symmetric-Key Encryption**: Same key for encryption/decryption (e.g., AES).
- **Public-Key Encryption**: Different keys for encryption and decryption (e.g., RSA).

## Classical Ciphers
- **Caesar Cipher**: Shift each letter by a fixed number.
  - Example: "ATTACK AT DAWN" -> "DWWDFN DW GDZQ"
- **Monoalphabetic Cipher**: Any permutation of the alphabet.
  - Example: "I prefer freedom with danger to slavery with ease." -> "W UYMZMY ZYMMLEX DWGO LJIKMY GE TNJFMYC DWGO MJTM."
- **Vigenère Cipher**: Multiple Caesar ciphers using a keyword.
  - Example: Keyword: "mason", Plaintext: "althoughthiswasaspeech" -> Ciphertext: "mllvbggzhuusoofmshsroh"

## Cryptanalysis
- **Objective**: Recover key or plaintext.
- **Brute-Force Attack**: Try all possible keys.
- **Frequency Analysis**: Analyze letter frequencies.

## Kerckhoff’s Principle
- Security depends only on the secrecy of the key, not the algorithm.

## Transposition Ciphers
- **Rail Fence Cipher**: Write message in a zigzag pattern and read off row by row.
  - Example: "meet me after the toga party" -> "MEMATRHTGPRYETEFETEOAAT"

## Advanced Concepts
- **One-Time Pad**: Unbreakable cipher if key is random, as long as the message, and used only once.
- **Product Ciphers**: Combine multiple ciphers (e.g., substitution + transposition).

## Important Points
- **Security through obscurity is not effective.**
- **Combination of cryptographic techniques and careful key management is crucial.**