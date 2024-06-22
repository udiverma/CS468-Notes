# Module 10 Cheatsheet

## SSL/TLS for Transport Layer Security

### Overview
- **SSL (Secure Socket Layer)**: Developed by Netscape in 1995 to secure and authenticate connections between browsers and servers.
- **TLS (Transport Layer Security)**: SSL Version 3 became an open standard in 1999 (RFC 2246) and was renamed TLS.
- **Purpose**: Provides security for web commerce, email servers, chat servers, remote login, instant messaging, and some VPNs.
- **Certificates**: Issued by Certificate Authorities (CA) to authenticate endpoints.

### SSL/TLS Protocols
1. **SSL Handshake Protocol**: Authenticates clients and servers, establishes security parameters.
2. **SSL Record Protocol**: Transmits data securely using encryption and MAC.
3. **SSL Change Cipher Spec Protocol**: Updates the cipher spec.
4. **SSL Alert Protocol**: Conveys alerts.

### SSL Handshake Protocol
- **Phase 1**: Client sends `ClientHello` with supported SSL version, random number, session ID, cipher suite, and compression methods.
- **Phase 2**: Server responds with `ServerHello`, sends its certificate, may send `ServerKeyExchange` and `CertificateRequest`, and ends with `ServerHelloDone`.
- **Phase 3**: Client sends its certificate (if requested), `ClientKeyExchange` with session key encrypted by server's public key, and `CertificateVerify` if needed.
- **Phase 4**: Both client and server send `ChangeCipherSpec` messages, followed by `Finished` messages to complete the handshake.

### SSL Record Protocol
- **Steps**:
  1. Fragmentation: Split data into blocks ≤ 16,384 bytes.
  2. Compression: (Optional) Compress data.
  3. MAC: Compute and append Message Authentication Code.
  4. Encryption: Encrypt compressed data and MAC using symmetric key.
  5. SSL Record Header: Add header indicating content type, SSL version, and length.

### SSL Session and Connection
- **Connection**: One-time transport of information, transient.
- **Session**: Enduring association, can consist of multiple connections, established by the SSL Handshake Protocol.

### SSL Session State
- Parameters:
  - Session Identifier
  - Peer Certificate
  - Compression Method
  - Cipher Spec
  - Master Secret
  - IsResumable flag

### SSL Connection State
- Parameters:
  - Server Write MAC Secret
  - Client Write MAC Secret
  - Server Write Key
  - Client Write Key
  - Initialization Vectors
  - Sequence Numbers

## SSL Socket Programming

### The Socket Interface
- **Socket**: Endpoint for communication, combination of IP address and port.
- **Socket Pair**: Uniquely identifies a communication.
- **Server Operations**: `socket()`, `bind()`, `listen()`, `accept()`, `recv()`, `send()`, `close()`.
- **Client Operations**: `socket()`, `connect()`, `send()`, `recv()`, `close()`.

### Example Code

#### SSL Server Code
```
import java.io.*;
import java.net.*;
import javax.net.ssl.*;

public class JavaSSLServer {
    public static void main(String args[]) {
        SSLServerSocketFactory sslServerSocketFactory = (SSLServerSocketFactory) SSLServerSocketFactory.getDefault();
        try {
            ServerSocket sslServerSocket = sslServerSocketFactory.createServerSocket(8000);
            while (true) {
                Socket socket = sslServerSocket.accept();
                ObjectOutputStream oOutputStream = new ObjectOutputStream(socket.getOutputStream());
                ObjectInputStream oInputStream = new ObjectInputStream(socket.getInputStream());
                String message = (String) oInputStream.readObject();
                oOutputStream.writeObject(message);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

#### SSL Client Code
```
import java.net.*;
import java.io.*;
import javax.net.ssl.*;
import javax.swing.*;

public class JavaSSLClient {
    public static void main(String args[]) {
        SSLSocketFactory sslSocketFactory = (SSLSocketFactory) SSLSocketFactory.getDefault();
        try {
            Socket socket = sslSocketFactory.createSocket("127.0.0.1", 8000);
            ObjectOutputStream oOutputStream = new ObjectOutputStream(socket.getOutputStream());
            ObjectInputStream oInputStream = new ObjectInputStream(socket.getInputStream());
            String message = JOptionPane.showInputDialog("Enter a message");
            oOutputStream.writeObject(message);
            String echo = (String) oInputStream.readObject();
            System.out.println("The echoed message is: " + echo);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Key Points
- **SSL/TLS**: Ensures secure communication over the Internet.
- **Handshake Protocol**: Establishes security parameters and authenticates endpoints.
- **Record Protocol**: Encrypts and ensures integrity of data.
- **Socket Programming**: Enables secure communication using SSL/TLS with Java sockets.

## Summary 
Understanding SSL/TLS protocols and their implementation in socket programming is essential for secure communication. SSL/TLS provides the necessary encryption, authentication, and integrity for data transmitted over networks.

