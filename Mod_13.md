# Module 13 Cheatsheet

## Firewalls and Intrusion Detection Systems (IDS)

### Firewalls

#### Overview
- **Firewall**: A device installed between the internal network and the internet to filter and forward packets based on predefined rules.
- **Purpose**: Prevent unauthorized access and protect internal networks.

#### Firewall Policies
- **Actions**:
  - **Accepted**: Permitted through the firewall.
  - **Dropped**: Not allowed through, no indication of failure.
  - **Rejected**: Not allowed through, informs the source of rejection.
- **Rules Based On**:
  - Protocol (TCP, UDP)
  - Source/Destination IP addresses
  - Source/Destination ports
  - Application-level payload (e.g., virus detection)

#### Blacklists and Whitelists
- **Blacklist (default-allow)**: Allows all traffic except that which matches rules in the blacklist.
  - **Pros**: Flexible.
  - **Cons**: Unexpected malicious traffic might pass.
- **Whitelist (default-deny)**: Denies all traffic except that which is specifically allowed.
  - **Pros**: Safer.
  - **Cons**: Must account for all legitimate traffic.

#### Types of Firewalls
- **Packet Filters (Stateless)**: Inspects packets individually without context.
- **Stateful Filters**: Maintains state of active connections and can inspect packets in context.
- **Proxy Firewalls**: Understands application protocols, inspects traffic content for security threats.

### Intrusion Detection Systems (IDS)

#### Overview
- **IDS**: Monitors network/system activities for malicious actions or policy violations.
- **Types**:
  - **Rule-Based IDS**: Uses predefined rules and signatures to identify known attack patterns.
  - **Statistical IDS**: Establishes a baseline of normal behavior and flags significant deviations.

#### IDS Components
- **IDS Manager**: Analyzes data from sensors to detect intrusions and sounds alarms.
- **IDS Sensors**: Collects data for analysis.

#### Possible Alarm Outcomes
- **True Positive**: Correctly identifies an intrusion.
- **False Positive**: Incorrectly identifies normal activity as an intrusion.
- **True Negative**: Correctly identifies normal activity.
- **False Negative**: Fails to identify an intrusion.

## Firewall and IDS Example Commands

### NMAP
- **Host Discovery**:
  - `nmap -sP [target]`: Ping scan.
- **Port Scanning**:
  - `nmap -sS [target]`: SYN scan.
  - `nmap -sT [target]`: Connect scan.
  - `nmap -p [portlist] [target]`: Scan specified ports.
  - `nmap -O [target]`: OS detection.
  - `nmap -sV [target]`: Service/version detection.
  - `nmap -A [target]`: Aggressive scan.
- **Stealth Scanning**:
  - `nmap -sN [target]`: Null scan.
  - `nmap -sF [target]`: FIN scan.
  - `nmap -sX [target]`: Xmas scan.

## Summary
Understanding firewalls and IDS is crucial for protecting networks from unauthorized access and detecting malicious activities. Firewalls filter traffic based on rules, while IDS monitor and analyze network behavior to identify and respond to threats.