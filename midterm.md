# Computer Networks Midterm Review

## Chapter 1 Computer Networks and the Internet

### Section 1.1 What is the Internet?

**R1. What is the difference between a host and an end system? List several different types of end systems. Is a Web server an end system?**

There is no difference beween a host and an end system.

End systems include laptops, smartphones, tablets, TVs, game consoles, watches, eye glasses, etc.

A Web server is an end system.

**R3. Why are standards important for protocols?**

Standards are important for protocols so that people can create networking systems and products that interoperate.

### Section 1.2 The Network Edge

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

### Section 1.3 The Network Core

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

A content provider connect to lower-tier ISPs, either by directly connection or by connecting with them at IXPs. It attempts to "bypass" the upper tiers of the Internet.

It do so to reduce its payments to upper-tier ISPs and to have greater control of how its services are ultimately delivered to end users.

### Section 1.4 Dealy, Loss and Throughput in Packet-Switched Networks


























































...
