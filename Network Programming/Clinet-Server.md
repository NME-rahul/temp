# socket()
    socket(int domain, int type, int protocol);


#### Domain:-
* **(i) AF_INET** (Address Family - IPv4):
AF_INET stands for Address Family: Internet. It tells the socket() function that the socket will use the IPv4 protocol.
Other common address families include:
   * **AF_INET6**: For IPv6 addresses.
   * **AF_UNIX**: For local inter-process communication using Unix domain sockets.
In this case, AF_INET specifies that the socket will communicate over the IPv4 network (e.g., using an IPv4 address).

- **(ii) SOCK_STREAM** (Socket Type - Stream-Based):
SOCK_STREAM specifies the type of socket, and it indicates that this socket will provide stream-based communication. This is typically used for TCP (Transmission Control Protocol) sockets.
Characteristics of
  * **SOCK_STREAM (TCP)**:
Connection-oriented: Establishes a connection before data is exchanged.
Reliable: Guarantees that data will arrive in the correct order and without errors.
  * **Byte stream**: Data is delivered as a continuous stream, rather than discrete packets.
Other common socket types include:
  * **SOCK_DGRAM**: Used for datagram-based communication, typically for UDP (User Datagram Protocol). It's connectionless and unreliable but faster than TCP.
  * **SOCK_RAW**: Allows direct access to lower-level protocols like ICMP or raw IP.
  
- **(iii) 0** (Protocol - Automatically Chosen for TCP):
The protocol argument specifies the protocol to be used with the socket. Setting it to 0 means the system will automatically choose the default protocol for the specified socket type.
In this case, because the type is **SOCK_STREAM**, the default protocol is TCP.
If you wanted to specify a different protocol explicitly (e.g., IPPROTO_TCP for TCP or IPPROTO_UDP for UDP), you could pass that protocol's identifier here, but 0 is typically sufficient to choose the appropriate default.


- **Full Breakdown:**
AF_INET: This socket will use the IPv4 protocol for communication.
SOCK_STREAM: This socket is a stream-based socket, meaning it will use TCP, which provides reliable, connection-oriented communication.
0: The default protocol for SOCK_STREAM is TCP, and passing 0 tells the system to automatically select TCP.

