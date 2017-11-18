# Computer Networks Midterm Review

# Chapter 1 Computer Networks and the Internet

## Section 1.1 What is the Internet?

**R1. What is the difference between a host and an end system? List several different types of end systems. Is a Web server an end system?**

There is no difference beween a host and an end system.

End systems include laptops, smartphones, tablets, TVs, game consoles, watches, eye glasses, etc.

A Web server is an end system.

**R3. Why are standards important for protocols?**

Standards are important for protocols so that people can create networking systems and products that interoperate.

## Section 1.2 The Network Edge

**List six access technologies. Classify each one as home access, enterprise access, or wide-area wireless access.**

Home Access

- Digital Subscriber Line (DSL)
- Cable
- Fiber to the Home (FTTH)
- Dial-up
- Satellite

Enterprise Access

- Ethernet
- WiFi

Wide-Area Wireless Access

- 3G
- LTE


**R5. Is HFC transmission rate dedicated or shared among users? Are collisions possible in a downstream HFC channel? Why or why not?**

HFC bandwidth is shared among the users. On the downstream channel, all packets emanate from a single source, namely, the head end. Thus, there are no collisions in the downstream channel.

**R7. Why is DSL much faster than dial-up access?**

???

**R8. What are some of the physical media that Ethernet can run over?**

- Twisted-Pair Copper Wire
- Fiber Optics

**R9. Dial-up modems, HFC, DSL and FTTH are all used for residential access. For each of these access technologies, provide a range of transmission rates and comment on whether the transmission rate is shared or dedicated.**

- Dial-up

Up to 56 Kbps.

Bandwidth is dedicated.

- DSL

Up to 55 Mbps downstream and 15 Mbps upstream.

Bandwidth is dedicated.

- HFC

Up to 42.8 Mbps downstream and 30.7 Mbps upstream.

Bandwidth is shared.

- FTTH

Up to gigabits per second (potentially).

Bandwidth is not shared. (???)

## Section 1.3 The Network Core

**R12. What advantage does a circuit-switched network have over a packet-switched network? What advantages does TDM have over FDM in a circuit-switched network?**

**Packet Switching Versus Circuit Switching**

- Better sharing of transmission capacity as circuit switching is wasteful during silent periods.
- Simpler, more efficient and less costly to implement
- Not suitable for real-time services because of its variable and unpredictable end-to-end delays (primarily quesing delays).
- A circuit-switched network can guarantee a certain amount of end-to-end bandwidth for the duration of a call.

FDM requires sophisticated analog hardware to shift signal into appropriate frequency bands.

**R14. Why will two ISPs at the same level of the hierarchy often peer with each other? How does an IXP earn money?**

If the two ISPs do not peer with each other, then when they send traffic to each other they have to send the traffic through a provider ISP (intermediary), to which they have to pay for carrying the traffic. By peering with each other directly, the two ISPs can **reduce their payments to their provider ISPs**.

An Internet Exchange Points (IXP) (typically in a standalone building with its own switches) is a meeting point where multiple ISPs can connect and/or peer together.

An ISP earns its money by **charging each of the the ISPs that connect to the IXP** a relatively small fee, which may depend on the amount of traffic sent to or received from the IXP.

**R15. Why is a content provider considered a different Internet entity today? How does a content provider connect to other ISPs? Why?**

A content provider is considered a different Internet entity because it's often interconnected and via private network, which is separate from the public Internet.

A content provider connect to lower-tier ISPs, either by direct connection or by connecting with them at IXPs. It attempts to "bypass" the upper tiers of the Internet.

It do so to reduce its payments to upper-tier ISPs and to have greater control of how its services are ultimately delivered to end users.

## Section 1.4 Dealy, Loss and Throughput in Packet-Switched Networks

**R16. Consider sending a packet from a source host to a destination host over a fixed route. List the delay components in the end-to-end delay. Which of these delays are constant and which are variable?**

$d_{nodal} = d_{proc} + d_{queue} + d_{trans} + d_{prop}$

$d_{proc}$, $d_{trans}$, $d_{prop}$ is constant if the length of the packet is fixed.

$d_{queue}$ is variable.

**R20. Suppose end system A wants to send a large file to end system B. At a very high level, describe how end system A creates packets from the file. When one of these packets arrives to a packet switch, what information in the packet does the switch use to determine the link onto which the packet is forwarded? Why is packet switching in the Internet analogous to driving from one city to another and asking directions along the way?**

End system A **breaks** the large file into chunks. It **adds header** to each chunk, thereby **generating multiple packets** from the file. The header (**Network Layer**) in each packet includes the IP address of the destination (end system B).

The packet switch uses the **destination IP address** in the packet to determine the outgoing link.

Asking which road to take is analogous to a packet asking which outgoing link it should be forwarded on, given the packet’s destination address.

## Section 1.5 Protocol Layers and Their Service Models

**R22. If two end-systems are connected through multiple routers and the data-link level between them ensures reliable data delivery, is a transport protocol offering reliable data delivery between these two end-systems necessary? Why?**

???

Tips: garbled data in routers.

**R25. Which layers in the Internet protocol stack does a router process? Which layers does a link-layer switch process? Which layers does a host process?**

Routers process network, link and physical layers.

> This is a little bit of a white lie, as modern routers sometimes act as firewalls or caching
components, and process Transport layer as well.

Link layer switches process link and physical layers (layers 1 through2).

Hosts process all five layers.


## Section 1.6 Networks Under Attack

**R26. If you want to spy on what websites your classmates are visiting with their laptops thourgh the university's WiFi network, what could you do?**

Place a passive receiver in the vicinity of the wireless transmitter, that receiver can obtain a copy of every packet that is transmitted.

# Chapter 2 Application Layer

## Section 2.1 Principles of Network Applications

**R1. List five nonproprietary Internet applications and the application-layer protocols that they use.**

Application  | Application-Layer Protocol  |  Underlying Transport Protocol
--|---|--
Electronic mail  | SMTP  | TCP
Remote terminal access  |Telnet   |  TCP
Web  | HTTP  |  TCP
File transfer  | FTP  |  TCP
Streaming multimedia  |  HTTP |  TCP
Internet telephony  |  SIP, RTP, or proprietary (eg. Skype) |  UDP or TCP

**R3. For a communication session between a pair of processes, which process is the client and which is the server?**

The process which initiates the communication is the client; the process that waits to be contacted is the server.

**R6. What components are needed to complete a Web application?**

1. A standard for document formats (HTML)
2. Web browsers
3. Web servers
4. An application-layer protocol (HTTP)

**R8. List the four broad classes of services that a transport protocol can provide. For each of the service classes, indicate if either UDP or TCP (or both) pro- vides such a service.**

- Reliable Data Transfer (TCP)
- Throughput (Neither)
- Timing (Neither)
- Security (Neither)

**R9. Does SSL operate at the transport layer or the application layer? If the application developer wants TCP to be enhanced with SSL, what does the developer have to do?**

SSL operates at the application layer.

If the application developer wants TCP to be enhanced with SSL, she has to include the SSL code (existing, highly optimized libraries and classes) in the application.

## Section 2.2 - 2.4 HTTP, SMTP, IMAP, POP3, DNS

**R10. What is meant by a handshaking protocol?**

A protocol uses handshaking if the two communicating entities first exchange control packets before sending data to each other.

SMTP uses handshaking at the application layer whereas HTTP does not.

**R11. What does a stateless protocol mean? Is IMAP stateless? What about SMTP?**

???
A stateless protocol maintains no information about the clients. IMAP is stateful. SMTP and POP3 are stateless.

**R12. How can websites keep track of users? Do they always need to use cookies?**

By using cookies. Cookie technology has four components,

- A cookie header line in the HTTP response message
- A cookie header line in the HTTP request message
- A cookie file kept on the user's end system and managed by the user's browser
- A back-end database at the Web site

???
Yes.

**R13. Will Web caching reduce the delay for all objects requested by a user or for only some of the objects? Why?**

Web caching can reduce the delay for all objects, even objects that are not cached, since caching reduces the traffic on links.

**R15. How can arbitrary data be transmitted over SMTP?**

The data has to be encoded into 7-bit ASCII before being put into one message.

**R19. Why are MX records needed?**

An organization’s mail server and Web server can have the same alias for a host name.

**R20. What is the difference between recursive and iterative DNS queries?**

With recursive queries, the host asks the DNS server to obtain the DNS mapping on its behalf. With iterative queries, the DNS  server directly returns the replies.

## Section 2.5 P2P

$D_{CS} = \max \{ \frac{NF}{u_s}, \frac{F}{d_{min}} \}$

$D_{P2P} = \max \{ \frac{F}{u_s}, \frac{F}{d_{min}}, \frac{NF}{u_s + \sum_{i=1}^N{u_i}} \}$

**R22. Consider a new peer Alice that joins BitTorrent without possessing any chunks. Without any chunks, she cannot become a top-four uploader for any of the other peers, since she has nothing to upload. How then will Alice get her first chunk?**

Recall that in BitTorrent, a peer picks a random peer and optimistically unchokes the peer for a short period of time.

Therefore, Alice will eventually be optimistically unchoked by one of her neighbors, during which time she will receive chunks from that neighbor.

## Section 2.6 Video Streaming and CDNs

**R24. CDNs typically adopt one of two different server placement philosophies. Name and briefly describe them.**

- Enter Deep

Enter deep into the access networks of ISP by deploying server clusters in access ISPs all over the world.

- Bring Home

Bring the ISPs home by building large clusters at a smaller number of sites (typically place their clusters in IXPs [Internet Exchange Points]).

**R26. In Section 2.7, the UDP server described needed only one socket, whereas the TCP server needed two sockets. Why? If the TCP server were to support $n$ simultaneous connections, each from a different client host, how many sockets would the TCP server need?**

With the UDP server, there is **no welcoming socket**, and all data from different clients enters the server through this one socket.

With the TCP server, there is a welcoming socket, and each time a client initiates a connection to the server, a new socket is created.

Thus, to support n simultaneous connections, the server would need n+1 sockets.

**R27. For the client-server application over TCP described in Section 2.7, why must the server program be executed before the client program? For the client- server application over UDP, why may the client program be executed before the server program?**

For the TCP application, as soon as the client is executed, it **attempts to initiate a TCP connection** with the server.

If the TCP server is not running, then the client will fail to make a connection.

For the UDP application, the client does not initiate connections (or attempt to communicate with the UDP server) immediately upon execution.

# Chapter 3 Transport Layer

## Section 3.1 - 3.3 Introduction, Multiplexing and Demultiplexing, UDP

User Datagram Protocol

**R3. How is a UDP socket fully identified? What about a TCP socket? What is the difference between the full identification of both sockets?**

UDP: (destination IP address, destination port number)

TCP: (source IP address, source port number, destination IP address, destination port number)

**R4. Describe why an application developer might choose to run an application over UDP rather than TCP.**

- Avoid congestion control
- Do not need reliable data transfer

**R5. Why is it that voice and video traffic is often sent over TCP rather than UDP in today’s Internet? (Hint: The answer we are looking for has nothing to do with TCP’s congestion-control mechanism.)**

Since **most firewalls** are configured to block UDP traffic, using TCP for video and voice traffic lets the traffic though the firewalls.

**R6. Is it possible for an application to enjoy reliable data transfer even when the application runs over UDP? If so, how?**

Yes. The application developer can put reliable data transfer into the application layer protocol. This would require a significant amount of work and debugging, however.

**R7. Suppose a process in Host C has a UDP socket with port number 6789. Sup- pose both Host A and Host B each send a UDP segment to Host C with destination port number 6789. Will both of these segments be directed to the same socket at Host C? If so, how will the process at Host C know that these two segments originated from two different hosts?**

Yes, both segments will be directed to the same socket.

For each received segment, at the socket interface, the operating system will provide the process with the **IP addresses** to determine the origins of the individual segments.

**R8. Suppose that a Web server runs in Host C on port 80. Suppose this Web server uses persistent connections, and is currently receiving requests from two different Hosts, A and B. Are all of the requests being sent through the same socket at Host C? If they are being passed through different sockets, do both of the sockets have port 80? Discuss and explain.**

For each persistent connection, the Web server creates a separate “connection socket”.

When host C receives and IP datagram, it examines these four fields in the datagram/segment to determine to which socket it should pass the payload of the TCP segment. Thus, the requests from A and B pass through different sockets.

The identifier for both of these sockets has 80 for the destination port; however, the identifiers for these sockets have different values for source IP addresses.

## Section 3.4 Principles of Reliable Data Transfer

**R9. In our $rdt$ protocols, why did we need to introduce sequence numbers?**

Sequence numbers are required for a receiver to find out whether an arriving packet contains **new data or is a retransmission**.

**R10. In our $rdt$ protocols, why did we need to introduce timers?**

To **handle losses** in the channel.

If the ACK for a transmitted packet is not received within the duration of the timer for the packet, the packet (or its ACK or NACK) is assumed to have been lost. Hence, the packet is retransmitted.

**R11. Suppose that the roundtrip delay between sender and receiver is constant and known to the sender. Would a timer still be necessary in protocol rdt 3.0, assuming that packets can be lost? Explain.**

To **detect the loss**, for each packet, a timer of constant duration will still be necessary at the sender.

## Section 3.6 TCP

Transmission Control Protocol

**R16. Consider the Telnet example discussed in Section 3.5. A few seconds after the user types the letter ‘C,’ the user types the letter ‘R.’ After typing the letter ‘R,’ how many segments are sent, and what is put in the sequence number and acknowledgment fields of the segments?**

3 segments.

- First segment: seq = 43, ack =80;
- Second segment: seq = 80, ack = 44;
- Third segment; seq = 44, ack = 81

## To do list

Format

- HTTP
- SMTP
- DNS
- TCP
- UDP

Procedure

- rdt 1.0 - 3.0
- Socket Programming
- GBN
- SR

Concepts Review

Slides












...
