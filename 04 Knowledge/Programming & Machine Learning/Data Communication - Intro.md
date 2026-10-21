---
tags: [machine-learning, networking, programming]
---

2026-08-05 10:38

Status: #Teen 

Tags: [[Data Communication]] [[OSI]]

# Data Communication - Intro

The OSI (Open System Interconnection) system divides the network communication into 7 layers each handling a specific job. Data goes down through these layers when sending, and up through them when receiving.

![[Screenshot 2026-08-05 at 10.40.56 AM.png]]

**How to read the stack:** data flows top to bottom when sending (an app hands data down through each layer, gaining headers along the way) and bottom to top when receiving.

**The two groups**

- **Host layers (7–4, purple)** — deal with the actual data and how applications use it. These run on your device.
- **Media layers (3–1, coral)** — deal with getting bits from one physical point to another across the network.

**A few things worth knowing:**

- **Encapsulation**: each layer wraps the data from the layer above with its own header (and sometimes trailer). By the time it hits layer 1, your original data is buried inside several nested envelopes.
- **TCP/IP is the real-world cousin**: most networking today uses the simpler 4-layer TCP/IP model, which merges Application/Presentation/Session into one "Application" layer, and merges Data link/Physical into one "Network access" layer. OSI is more of a conceptual teaching tool than something implemented layer-for-layer in practice.
- **Mnemonic** (top to bottom): "**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing."

### Application Layer
The application layer is the top of the stack — it's the only layer that actual software and users interact with directly. Everything below it (layers 6 down to 1) exists just to get the application's data from one machine to another.

**What it actually does**

It provides the interface between network services and the software you use. When your browser wants a webpage, your email client wants to send a message, or an FTP tool wants to transfer a file, the application layer defines the rules — the protocol — for how that request and response should be structured.

**Common protocols here**

- **HTTP/HTTPS** — web browsing
- **FTP** — file transfer
- **SMTP, IMAP, POP3** — sending and receiving email
- **DNS** — translating domain names to IP addresses
- **SSH** — secure remote login
- **DHCP** — assigning IP addresses to devices on a network

**An important clarification**

The application layer is _not_ the application itself — your browser isn't "the application layer." Rather, it's the set of protocols and services the application uses to talk over the network. Your browser implements HTTP to request pages; it isn't HTTP.

**How it fits with the layers below it**

When you type a URL, the application layer formats that into an HTTP request. That request then gets handed down to Presentation (which might handle TLS encryption for HTTPS), then Session, then Transport (which breaks it into TCP segments), and so on down to Physical, where it actually leaves your machine as electrical or optical signals.


### Presentation Layer
The presentation layer sits right below Application, and its job is translation — making sure data is in a format both sender and receiver can actually understand, regardless of what hardware or software each side is running.

**What it actually does**

Think of it as the "translator" of the stack. Two systems might represent data completely differently internally — different character encodings, different ways of structuring files, different byte orders. The presentation layer converts data into a common format for transmission, then translates it back into something the receiving application expects.

**Three main jobs**

- **Translation / formatting** — converting between data representations, like character encoding (ASCII to Unicode, EBCDIC to ASCII) or ensuring a JPEG, PNG, or MPEG file is structured in a way the receiving app can render.
- **Compression** — shrinking data before it's sent to save bandwidth, then decompressing it on arrival.
- **Encryption/decryption** — this is the layer most associated with TLS/SSL, which is why "HTTPS" involves this layer. It encrypts data before it heads down the stack and decrypts it once it arrives.

**Why it's easy to confuse with Application**

In practice, a lot of modern software (like a browser) blends what OSI calls Presentation and Application into a single implementation. TLS, for instance, is often described as "sitting on top of Transport" in real-world architecture diagrams — it doesn't map perfectly onto layer 6 the way OSI textbooks suggest. This is one of the reasons OSI is taught as a conceptual reference model rather than something you'll find implemented layer-by-layer in real code.

**A simple way to remember it:** if Application decides _what_ to send, Presentation decides _how it looks_ on the wire — encoding, compression, encryption.

### Session Layer
The session layer manages the conversation itself — establishing, maintaining, and tearing down the connection between two applications, separate from the actual data transfer or the network plumbing underneath.

**What it actually does**

If Transport is responsible for _how_ data physically gets from A to B, Session is responsible for _organizing the conversation_ — think of it like managing a phone call rather than the phone line itself. It keeps track of whose turn it is to "talk," where you left off if the connection drops, and when the conversation is actually over.

**Three main jobs**

- **Session establishment, maintenance, and termination** — opening a dialogue between two devices, keeping it alive while data flows back and forth, and cleanly closing it when done.
- **Dialogue control** — deciding whether communication is half-duplex (one side talks at a time) or full-duplex (both sides talk simultaneously), and managing turn-taking.
- **Synchronization** — inserting checkpoints into a data stream. If you're transferring a huge file and the connection drops, synchronization points let the session resume from the last checkpoint instead of starting over from scratch.

**A concrete example**

When you log into a remote server via a protocol that uses persistent sessions, the session layer is what keeps that "logged in" state alive across multiple requests, and knows when to end it — whether from a timeout, an explicit logout, or a dropped connection.

**Why it's the most abstract layer**

Session is the layer most people struggle to point to in real-world code, because a lot of what OSI calls "session management" today happens either in the application itself (like a web app tracking login state with cookies/tokens) or gets folded into Transport-layer behavior (like TCP maintaining an open connection). It's rarely implemented as a distinct, separate layer the way OSI describes it — which is part of why the simpler 4-layer TCP/IP model doesn't bother giving it its own layer at all.

### Transport Layer
The transport layer is where reliability (or the deliberate lack of it) gets decided — it takes data from the upper layers, breaks it into manageable chunks, and makes sure those chunks get to the right application on the right device.

**What it actually does**

Network layer (below it) gets data from one machine to another. Transport layer's job is to get data from one _specific application_ on the sending machine to the correct _specific application_ on the receiving machine — and depending on the protocol, guarantee it arrives intact and in order.

**The two main protocols**

- **TCP (Transmission Control Protocol)** — connection-oriented and reliable. It establishes a handshake before sending data, numbers each segment, waits for acknowledgments, retransmits lost segments, and reassembles everything in the correct order. Used when accuracy matters more than speed: web browsing, email, file transfers.
- **UDP (User Datagram Protocol)** — connectionless and fast, with no guarantees. It just fires data off without handshakes, acknowledgments, or retransmission. Used when speed matters more than perfection: video calls, live streaming, online gaming, DNS lookups.

**Key jobs at this layer**

- **Segmentation** — breaking large chunks of data into smaller segments that fit network limits, then reassembling them at the destination.
- **Ports** — this is the layer where port numbers come in (port 80 for HTTP, 443 for HTTPS, 53 for DNS, etc.), which is how a device knows _which application_ on the receiving end should get the data.
- **Flow control** — preventing a fast sender from overwhelming a slow receiver.
- **Error checking** — verifying segments arrived undamaged, and triggering retransmission when they didn't (TCP only).

**Why this is the layer people actually reference most**

Unlike Session or Presentation, Transport shows up constantly in real conversations — "is this over TCP or UDP," "what port is that service on" — because it maps directly onto decisions developers make all the time.


### Network Layer 
The network layer is responsible for getting data from your device to a device on a _completely different network_ — this is the layer that makes the internet possible as a network of networks, rather than just a single local network.

**What it actually does**

While the Data link layer (below it) only knows how to move frames within a single local network, the network layer figures out the best path across multiple interconnected networks — potentially hopping through dozens of routers — to reach a device that could be on the other side of the world.

**Key jobs at this layer**

- **Logical addressing** — this is where IP addresses live (IPv4 or IPv6). Every device gets a unique address that identifies both what network it's on and where it sits within that network.
- **Routing** — determining the best path for data to travel across multiple networks. Routers operate at this layer, examining the destination IP address and deciding which direction to forward the packet.
- **Packetization** — data from the Transport layer gets wrapped into packets, each with a header containing source and destination IP addresses.
- **Fragmentation** — if a packet is too large for a network segment it needs to cross, the network layer can split it into smaller fragments and reassemble them at the destination.

**Routers vs switches**

This is the layer where the distinction between routers and switches becomes clear: switches (Data link layer) move frames around _within_ one network using MAC addresses; routers (Network layer) move packets _between_ different networks using IP addresses. Every time your data leaves your home network to reach the wider internet, it's a router making that decision.

**A useful mental model**

If IP addresses are like a postal address (city, street, house number) that gets a letter to the right neighborhood, MAC addresses (Data link layer, one level down) are more like a driver's name — they only matter for the very last leg, handing the letter to the exact right hand within that neighborhood.


### Data Link Layer
The data link layer takes the raw bits from the physical layer and organizes them into structured units called frames, while also handling how devices on the _same_ local network find and talk to each other.

**What it actually does**

Physical layer just pushes raw bits onto a wire with no structure or meaning. Data link layer wraps those bits into frames — discrete, addressed units — and manages access to the shared physical medium so multiple devices don't talk over each other and corrupt each other's data.

**Two sub-layers (a detail worth knowing)**

- **LLC (Logical Link Control)** — handles flow control and error checking for the frame, and identifies which network layer protocol (like IPv4 vs IPv6) the data belongs to.
- **MAC (Media Access Control)** — handles physical addressing and controls how devices access the shared medium (deciding who gets to transmit and when, to avoid collisions).

**Key jobs at this layer**

- **Physical addressing** — this is where MAC addresses live, a unique hardware identifier burned into every network interface card. Unlike IP addresses (which can change), a MAC address is tied to the physical hardware.
- **Framing** — organizing bits into frames with headers (source/destination MAC) and trailers (error-checking info).
- **Error detection** — using a checksum (like CRC) to detect if a frame got corrupted in transit. Note: it detects errors, it doesn't fix them — that's handled by retransmission at a higher layer if needed.
- **Media access control** — managing which device gets to transmit on a shared medium at any given moment, to prevent collisions.

**Devices that live here**

Switches and bridges are the classic Data link layer devices. A switch reads the destination MAC address in each frame and forwards it only to the specific port that device is connected to — much smarter than a hub, which blasts every signal to every port regardless.

**Tying it back to the whole stack**

### Physical Layer
The physical layer is the bottom of the stack — it's where digital data actually becomes something physical that can travel: electrical voltage on a copper wire, light pulses in fiber optic cable, or radio waves through the air.

**What it actually does**

It doesn't know or care what the data means. No addresses, no packets, no "messages" — just a raw stream of bits (1s and 0s) that it converts into signals and pushes onto the medium. Think of it as the layer responsible for the question "how do I represent a 1 versus a 0 physically?"

**What it defines**

- **Voltage levels** — e.g., in Ethernet, what voltage counts as a 1 vs a 0
- **Cable and connector specs** — Cat5e/Cat6 twisted-pair, coaxial, fiber optic, the pinout of an RJ45 connector
- **Data rates** — how many bits per second the medium can carry
- **Bit timing/synchronization** — how the sender and receiver agree on when one bit ends and the next begins
- **Physical topology** — how devices are literally wired together (bus, star, mesh, etc.)

**Devices that live here**

Hubs, repeaters, cables, network interface card (NIC) hardware, and connectors. A hub is a good example of a "pure" physical layer device — it just repeats electrical signals to every port without looking at any addressing info (which is why hubs have mostly been replaced by switches, which operate one layer up).

**Why it matters in practice**

Most day-to-day networking problems that seem mysterious are actually physical layer issues — a loose cable, a bad NIC, electromagnetic interference, or a cable run that's too long and the signal degrades. When someone says "have you tried unplugging and replugging it," that's a physical layer fix.




# References

