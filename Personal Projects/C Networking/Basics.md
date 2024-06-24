### Functions

1. **socket()**
    
    - **Prototype:** `int socket(int domain, int type, int protocol);`
    - **Description:** Creates an endpoint for communication and returns a file descriptor for the socket.
    - **Parameters:**
        - `domain`: Specifies the communication domain (e.g., `AF_INET` for IPv4, `AF_INET6` for IPv6).
        - `type`: Specifies the communication type (e.g., `SOCK_STREAM` for TCP, `SOCK_DGRAM` for UDP).
        - `protocol`: Specifies the protocol to be used (typically `0` to select the default protocol).
2. **bind()**
    
    - **Prototype:** `int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen);`
    - **Description:** Associates a local address with a socket.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `addr`: Pointer to a `struct sockaddr` containing the address to bind to.
        - `addrlen`: Length of the address.
3. **listen()**
    
    - **Prototype:** `int listen(int sockfd, int backlog);`
    - **Description:** Marks the socket as a passive socket, that is, as a socket that will be used to accept incoming connection requests.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `backlog`: Defines the maximum length to which the queue of pending connections for `sockfd` may grow.
4. **accept()**
    
    - **Prototype:** `int accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen);`
    - **Description:** Accepts a connection on a socket.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `addr`: Pointer to a `struct sockaddr` that will receive the address of the connecting entity.
        - `addrlen`: Pointer to a `socklen_t` that initially contains the size of `addr` and is modified to indicate the actual size.
5. **connect()**
    
    - **Prototype:** `int connect(int sockfd, const struct sockaddr *addr, socklen_t addrlen);`
    - **Description:** Initiates a connection on a socket.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `addr`: Pointer to a `struct sockaddr` containing the address to connect to.
        - `addrlen`: Length of the address.
6. **send()**
    
    - **Prototype:** `ssize_t send(int sockfd, const void *buf, size_t len, int flags);`
    - **Description:** Sends data on a connected socket.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `buf`: Pointer to the data to be sent.
        - `len`: Length of the data.
        - `flags`: Flags for controlling the send operation (usually `0`).
7. **recv()**
    
    - **Prototype:** `ssize_t recv(int sockfd, void *buf, size_t len, int flags);`
    - **Description:** Receives data from a connected socket.
    - **Parameters:**
        - `sockfd`: File descriptor of the socket.
        - `buf`: Buffer to receive the data.
        - `len`: Length of the buffer.
        - `flags`: Flags for controlling the receive operation (usually `0`).
8. **close()**
    
    - **Prototype:** `int close(int fd);`
    - **Description:** Closes a file descriptor, so that it no longer refers to any file and may be reused.

### Constants

1. **Address Families**
    
    - `AF_INET`: IPv4 Internet protocols.
    - `AF_INET6`: IPv6 Internet protocols.
    - `AF_UNIX`: Local communication.
2. **Socket Types**
    
    - `SOCK_STREAM`: Provides sequenced, reliable, two-way, connection-based byte streams. Uses TCP.
    - `SOCK_DGRAM`: Supports datagrams, which are connectionless, unreliable messages of a fixed maximum length. Uses UDP.
3. **Protocol Values**
    
    - `IPPROTO_TCP`: TCP protocol.
    - `IPPROTO_UDP`: UDP protocol.
4. **Socket Options**
    
    - `SO_REUSEADDR`: Allows reuse of local addresses.
    - `SO_KEEPALIVE`: Enables keep-alive packets for the socket connection.

### Structures

1. **struct sockaddr**
    
    - **Description:** Generic socket address structure.
    - **Members:**
        - `sa_family_t sa_family`: Address family (e.g., `AF_INET`).
        - `char sa_data[14]`: Protocol-specific address information.
2. **struct sockaddr_in**
    
    - **Description:** Structure used for IPv4 addresses.
    - **Members:**
        - `sa_family_t sin_family`: Address family (`AF_INET`).
        - `in_port_t sin_port`: Port number (network byte order).
        - `struct in_addr sin_addr`: IPv4 address.
        - `char sin_zero[8]`: Padding to make the structure the same size as `struct sockaddr`.
3. **struct in_addr**
    
    - **Description:** Structure that represents an IPv4 address.
    - **Members:**
        - `uint32_t s_addr`: IPv4 address (in network byte order).