# Module 9 Cheatsheet

## Introduction to Networking

### Internet Basics
- **Internet**: A network of networks connecting millions of computing devices.
- **Hosts/End Systems**: Devices running network applications (e.g., smartphones, PCs).
- **Communication Links**: Fiber, copper, radio, satellite.
- **Packet Switches**: Routers and switches forward data packets.

### Internet Structure
- **Network Edge**: Hosts (clients and servers).
- **Access Networks**: Connect end systems to the network (e.g., home networks, Ethernet).
- **Network Core**: Interconnected routers, network of networks.

### Protocols
- Define the format and order of messages sent and received among network entities.
- **Examples**: TCP, IP, HTTP, FTP.

### OSI and Internet Protocol Stacks
- **Internet Protocol Stack**:
  1. Application
  2. Transport
  3. Network
  4. Link
  5. Physical
- **OSI Model**: Includes additional Presentation and Session layers.

## Network Security

### Security Threats
- **Malware**: Viruses, worms, spyware.
- **Packet Sniffing**: Intercepting packets on a network.
- **IP Spoofing**: Sending packets with a false source address.
- **Denial of Service (DoS)**: Overwhelming a resource with bogus traffic.

### Client/Server Network Model
- **Client**: Requests services.
- **Server**: Provides services.
- **Internet Servers**: Long-running processes that handle requests (e.g., web, FTP, mail servers).

### Key Concepts
- **IP Address**: Unique identifier for hosts on the Internet.
- **Port Numbers**: Identifiers for specific processes/services on a host.

### URLs and Domain Name System (DNS)
- **URL**: Uniform Resource Locator, used to specify addresses on the web.
- **DNS**: Translates human-readable domain names to IP addresses.

## Web Security

### HTTP
- **HTTP**: Protocol for web communication.
- **Methods**: GET, POST.
- **GET**: Retrieves data, parameters in URL.
- **POST**: Submits data, parameters in request body.

### Application Layer Security
- **Cross-Site Scripting (XSS)**: Injecting malicious scripts into web pages.
- **Cross-Site Request Forgery (CSRF)**: Forcing authenticated users to perform actions without their consent.

### Solutions
- **XSS**: Validate and sanitize input, use Content Security Policy (CSP).
- **CSRF**: Use tokens, confirm sensitive actions with a secondary mechanism, prefer POST requests.

### Information Leakage
- Avoid exposing sensitive information in error messages or source code.
- Ensure proper server configuration to prevent unintended information disclosure.

### Insecure Direct Object Reference
- **Issue**: Exposing internal implementation details (e.g., file paths, database keys).
- **Solution**: Validate input, use indirect references.

### SQL Injection
- **Definition**: Injecting malicious SQL code into queries.
- **Prevention**: Use parameterized queries, input validation.

## Highlights
- Networking involves various layers and protocols.
- Security threats are prevalent at different layers of the network.
- HTTP and web application security are crucial for protecting data and users.
- Proper input validation and server configuration are key to preventing common vulnerabilities.

## Summary
Understanding the structure and protocols of the Internet, along with common security threats and mitigation techniques, is crucial for building and maintaining secure networked systems. This includes protecting against malware, sniffing, spoofing, and ensuring the security of web applications through best practices in coding and configuration.