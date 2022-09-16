# HTTP 2/3

**What is HTTP:** <br>HyperText Transfer Protocol(or HTTP) is an application-layer protocol for transmitting hypermedia documents, such as HTML<br>This protocol was designed for communication between web servers and web browsers. HTTP follows a client-server model, with the client opening a connection to make request, then waiting until it receives a responese( there is no databetween the two requests ).

#
1. `HTTP/2`

> The primary goals for HTTP/2 are to reduce latency by enabling full request and response multiplexing, minimize protocol overhead with efficient compression of HTTP header fields and add support for request prioritization and server push.

- How the HTTP/2 protocol differs from HTTP/1.1:

  - It's a binary protocol rather than a text protocol which dictates how the HTTP messages are encapsulated and transferred between the client and server.
  - It's a multiplexed protocol
  - It compresses headers which removes the duplication and overhead of data transmitted.
  - It allows a server to populate data in a client cache through a mechanism called the server push.

- The evolution of HTTP/2:
  - Support for `Alt-Svc` allowed the dissociation of the identification and the location of a given resource.
  - The introduction of `Client-Hints` allowed the browser or client to proactively communicate info about it's requirements and hardware constraints to the server.
  - Security-related prefixes in the Cookie header helped guarantee that secure cookies couldn't be altered.

#
2. `HTTP/3`
> HTTP/3 will be the first major update to the hypertext transfer protocol scince HTTP/2 was approved.<br> The difference in HTTP/3 is that runs on QUIC instead TCP/TLS for the transport layer portion. QUIC is designed for mobile-heavy internet usage in which people carry smartphones that constantly switch from one network to another. To handle that switching QUIC relies on the User Datagram Protocol(UDP) which enables faster connections and faster user ecperience when browsing online.

- QUIC improvements and benefits over HTTP/2:
  - Developing a workaround for the sluggish performance when a smartphone switches from WiFi to cellular data.
  - When one packet of information does not make it to its destination, it will no longer block all streams of information.
  - Faster connection establishment.
  - More comprehensive encryption (will provied encryption by default).
  
#
3. [HTTPS](https://www.cloudflare.com/en-gb/learning/ssl/what-is-https/)
  
  > HTTPS(or Hypertext transfer protocol secure) is the secure version of HTTP which means it's encrypted in order to increase security of data transfer. This is particularly important when users transmit sensitive data, such as by logging into a bank account, email service, or health insurance provider.
  
- [How does HTTPS work](https://www.youtube.com/watch?v=hExRDVZHhig):
  - It uses an encryption protocol to encrypt communications. The protocol is called `Transport Layer Security (TLS)`, although formerly it was known as `Secure Sockets Layer (SSL)`. This protocol secures communications by using what’s known as an asymmetric public key infrastructure. 
  - This type of security system uses two different keys to encrypt communications between two parties:
     - The private key which is controlled by the owner of a website.
     - The public key which is available to everyone who wants to interact with the server in a way that’s secure.
