---
description: >-
  Network fundamentals including the 4-layer model, TCP/IP, and a high level
  overview of the Internet including World Wide Web, and HTTP.
---

# Week 1: Introduction

Suppose we want to build a network of computers, what would we need at a minimum?

* Computers
* A way of communication between them

Network 4-Layer Model

1. Application Layer: HTTP, FTP, SSH, SMTP, POP3
   * Provides applications with standardized protocols to exchange data
2. Transport Layer: TCP
   * Provides host-to-host communication services
   * Where at least two nodes communicating with each other
   * Connection-oriented
   * Sends segments of data from the application layer \(packets\)
3. Internet Layer: IP
   * Provides protocols for sending packets across a network or through multiple networks
   * The IP handles routing of data across networks using IP addresses
   * IP is connection-less because we don't need a prearranged connection to send data over the network. There is no assurance that they will be delivered or if they were, and nothing to let the destination know to expect a packet
   * IP packets are easy to spoof \(e.g., simply change the source IP\) and defense against this come from higher network layers and network monitoring
4. Link Layer: Ethernet, WiFi, DSL
   * Protocols of the physical link between the nodes of the network

TCP \(Transport Control Protocol\)

* Connection-oriented
* Bi-directional
* Reliable and reacts to losing packets by slowing connection
* On the other hand, UDP is unreliable and doesn't react to packet loss
* Both client and server should acknowledge when they get data

3-Way Handshake

![](.gitbook/assets/image%20%281%29.png)

1. Client: Send a SYN packet
2. Server: Replies with a SYN-ACK
3. Client: Replies with ACK to signal server to be able to start sending data

An important part of TCP because...

* Can check packet is from correct host
* Losing packets is a real problem
* If no acknowledgement that packet was received, packet is sent again

Client-Server

* Client initiates request to server
* Server accepts or rejects connection
* If a connection is established, data can flow until connection terminates

World Wide Web: a global collection of resources which are identifiable and linked together

Note: the world wide web is not the internet, but it happens to use the internet as a framework; works over the internet

* A global collection of resources
  * Web resources: any data we can send through the internet
  * Global: we can access these resources no matter where they are in the world
* ...which are identifiable, i.e., getting resources from their web servers
  * Necessary that we can **locate** where they are in the entire web
  * Need a **consistent** way to identify and access each resource
  * URL - uniformed resource locator
    * Provides us with a way of specifying the location of a web resource
* ...and linked together
  * Resources link to other resources; allows us to easily discover the web

HTTP \(HyperText Transfer Protocol\)

* Protocol of the web
* Gives the client and server a mutual language at the application level
* Global reach: All machines can use HTTP through applications
* Identified through URLs, where each URL gives us one resource: a web page
  * Host names are translated to IP addresses by the Domain Naming System \(DNS\)
  * IP addresses can change and the name can stay the same
* Works by **request-response**, which originate from application layer of both the client and server side
* Linking: we want our resources to be linked together somehow
  * Hyperlinks links to other resources

How do we use HTTP?

* Think about how we use the web day-to-day: Upload, Download, Modify, Delete
* HTTP Method: tell the server what we want to do with that resource
  * Verbs that are used to label the actions we expect a server to take
    * GET - retrieve a resource

      GET /~csc148h/winter/index.html HTTP/1.1

      Host: www.teach.cs.toronto.edu

    * POST - create a resource
    * PATCH - update a resource
    * DELETE - delete a resource
* Request Headers and Body

So the response has.. 

* Response Code
* Headers
* Body

Important: the web server decides what the URL does

Just because it looks like a path to some file in a file system, doesn't mean it actually looks like that on the server.

Ports

* Every process on a computer that uses the internet is assigned a port \(e.g., a TCP or UDP port\)
* Server process that listens for HTTP requests usually uses port 80

![](.gitbook/assets/image%20%282%29.png)

HTTP: "Stateless" Protocol

* Each request is independent of previous request
  * Server doesn't keep track of previous request and doesn't care how many are sent at once
* This simplifies the protocol
* Illusion of state \(e.g., knowing which pages the user browsed\) can still occur, but is not part of the protocol

