# Module 11 Cheatsheet

## IPSec and VPN

### IPSec Overview
- **IPSec**: A suite of protocols to provide security at the network layer by encrypting and authenticating IP packets.
- **Uses**: Secures data over public networks, commonly used for VPNs.
- **Modes**: Transport and Tunnel.

### IPSec Modes
- **Transport Mode**:
  - Protects the payload but not the IP header.
  - Used for end-to-end communication between hosts.
- **Tunnel Mode**:
  - Encapsulates the entire original IP packet within a new IP packet with a new IP header.
  - Used for network-to-network communications (gateway-to-gateway).

### IPSec Protocols
- **Authentication Header (AH)**:
  - Provides source authentication and data integrity.
  - Does not provide encryption.
- **Encapsulating Security Payload (ESP)**:
  - Provides confidentiality, data integrity, and authentication.
  - Can be used in both transport and tunnel modes.

### IPSec Services
- **Confidentiality**: Encryption of packet contents.
- **Integrity**: Ensures data has not been altered.
- **Authentication**: Verifies the sender's identity.
- **Anti-Replay**: Prevents replay attacks using sequence numbers.

### Security Association (SA)
- **SA**: Defines the parameters for IPSec communication (e.g., encryption keys, algorithms).
- **Unidirectional**: Requires two SAs for bidirectional communication.
- **IKE (Internet Key Exchange)**: Protocol used to establish SAs, can use PSK or PKI for authentication.

### Virtual Private Networks (VPN)
- **VPN**: Allows secure communication over public networks by creating an encrypted tunnel.
- **Types**:
  - **Remote Access VPN**: Connects individual clients to a private network.
  - **Site-to-Site VPN**: Connects entire networks securely over the internet.

### VPN Security
- **Confidentiality**: Encrypts data to prevent eavesdropping.
- **Integrity**: Ensures data is not tampered with.
- **Authentication**: Verifies the identity of users and devices.
- **Two-Factor Authentication (2FA)**: Enhances security by requiring two forms of verification.

### Common VPN Protocols
- **IPSec**: Used for secure IP communication, providing data integrity and encryption.
- **SSL/TLS**: Often used for secure web communications and VPNs, operates at a higher layer than IPSec.

## Key Concepts
- **Transport Mode**: Encrypts only the payload, leaves the IP header unchanged.
- **Tunnel Mode**: Encrypts the entire original IP packet, adding a new IP header.
- **AH Protocol**: Provides authentication and integrity, no encryption.
- **ESP Protocol**: Provides encryption, authentication, and integrity.

## Summary
Understanding IPSec and VPNs is crucial for securing network communications. IPSec provides robust security through encryption and authentication at the network layer, while VPNs use these protocols to create secure connections over public networks. IPSec's transport and tunnel modes offer flexibility for different security needs, and VPNs ensure data confidentiality, integrity, and authentication.