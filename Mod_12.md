# Module 12 Cheatsheet

## Security Attacks

### TCP SYN Flooding Attack
- **Mechanism**: 
  - Hostile client sends TCP SYN requests with fake IP addresses.
  - Server responds with SYN/ACK, waiting for ACK that never arrives.
  - Server resources are exhausted, leading to a Denial-of-Service (DoS) attack.
- **Mitigation**: 
  - SYN cookies, firewalls, and rate limiting.

### SYN Scanning Attack
- **Purpose**: Find open ports by sending SYN requests and analyzing responses.
- **Detection**: SYN/ACK indicates an open port; RST indicates a closed port.

### IP Source Address Spoofing
- **Usage**: Forge IP addresses to launch SYN flood DoS attacks.
- **Mitigation**: 
  - Ingress filtering (RFC 2827/BCP 38) prevents packets with spoofed addresses.
  - Cooperation with ISPs is crucial.

## Scanning Techniques

### Types of Scanning
- **Host Discovery**: Identifies active devices on a network.
- **Port Scanning**: Identifies open ports and services.
- **Version Detection**: Determines application versions.
- **OS Detection**: Identifies operating systems and hardware characteristics.

### NMAP Scanning Tool
- **Features**: Host discovery, port scanning, version detection, OS detection.
- **Common Commands**:
  - `nmap -sP [target]`: Ping scan.
  - `nmap -sS [target]`: TCP SYN scan.
  - `nmap -sT [target]`: TCP connect scan.
  - `nmap -O [target]`: OS detection.
  - `nmap -sV [target]`: Service/version detection.
  - `nmap -A [target]`: Aggressive scan (OS detection, version detection, script scanning, and traceroute).

### Host Discovery Techniques
- **ICMP Sweeps**: Send ICMP ECHO requests; alive hosts reply.
- **TCP Sweeps**: Send TCP SYN/ACK packets; response indicates open ports.
- **UDP Sweeps**: Send UDP packets; lack of ICMP PORT UNREACHABLE indicates open port.

## Port Scanning Techniques

### Types of Port Scans
- **TCP Connect Scan**: Complete 3-way handshake, detectable by system logs.
- **TCP SYN Scan**: Half-open scan, sends SYN and waits for SYN/ACK, then RST.
- **Stealth Scans**: Avoid detection by sending unusual packet flags (e.g., FIN, XMAS, NULL).

### Port Scanning with NMAP
- **Commands**:
  - `nmap -sS [target]`: SYN scan.
  - `nmap -sT [target]`: Connect scan.
  - `nmap -p [portlist] [target]`: Scan specified ports.
  - `nmap -F [target]`: Fast scan, fewer ports.
  - `nmap --top-ports [number] [target]`: Scan most common ports.
  - `nmap -sV [target]`: Service/version detection.
  - `nmap -O [target]`: OS detection.

## Security Assessment and Auditing
- **Purpose**: Evaluate security, identify vulnerabilities, and ensure compliance.
- **Tools**: NMAP, Wireshark, SNORT.

## Summary
Understanding and mitigating security attacks like TCP SYN flooding and IP spoofing, along with mastering scanning techniques using tools like NMAP, are essential for maintaining secure systems. Effective security assessments and auditing help in identifying and addressing vulnerabilities.