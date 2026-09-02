### 3 Introduction

Why should I take this module?
You know the basic components of a simple network, as well as initial configuration. But after you have configured and connected these components, how do you know they will work together? Protocols! Protocols are sets of agreed upon rules that have been created by standards organizations. But, because you cannot pick up a rule and look closely at it, how do you truly understand why there is such a rule and what it is supposed to do? Models! Models give you a way to visualize the rules and their place in your network. This module gives you an overview of network protocols and models. You are about to have a much deeper understanding of how networks actually work!

What will I learn to do in this module?
Topic Title| Topic Objective
The Rules | Describe the types of rules that are necessary to successfully communicate.
Protocols | Explain why protocols are necessary in network communication.
Protocol Suites | Explain the purpose of adhering to a protocol suite.
Standards Organizations | Explain the role of standards organizations in establishing protocols for network interoperability.
Reference Models |  Explain how the TCP/IP model and the OSI model are used to facilitate standardization in the communication process.
Data Encapsulation | Explain how data encapsulation allows data to be transported across the network.
Data Access | Explain how local hosts access local resources on a network.


### 3.1 The Rules

#### 3.1.2 Communication fundamentals 
Networks vary in size, shape, and function. They can be as complex as devices connected across the internet, or as simple as two computers directly connected to one another with a single cable, and anything in-between. However, simply having a wired or wireless physical connection between end devices is not enough to enable communication. For communication to occur, devices must know "how" to communicate.
People exchange ideas using many different communication methods. However, all communication methods have the following three elements in common:
• Message source (sender) - Message sources are people, or electronic devices, that need to send a message to other individuals or devices.
• Message Destination (receiver) - The destination receives the message and interprets it.
• Channel - This consists of the media that provides the pathway over which the message travels from source to destination.

#### 3.1.3 Communication Protocols 
Sending a message, whether by face-to-face communication or over a network, is governed by rules called protocols. These protocols are specific to the type of communication method being used. In our day-to-day personal communication, the rules we use to communicate over one medium, like a telephone call, are not necessarily the same as the rules for using another medium, such as sending a letter.
The process of sending a letter is similar to communication that occurs in computer networks.


#### 3.1.4 Rule Establishment 
Before communicating with one another, individuals must use established rules or agreements to govern the conversation. 

Protocols must account for the following requirements to successfully deliver a message that is understood by the receiver:
• An identified sender and receiver
• Common language and grammar
• Speed and timing of delivery
• Confirmation or acknowledgment requirements

#### 3.1.5 Network Protocol Requirements
The protocols that are used in network communications share many of these fundamental traits. In addition to identifying the source and destination, computer and network protocols define the details of how a message is transmitted across a network.
Common computer protocols include the following requirements:
• Message encoding
• Message formatting and encapsulation
• Message size
• Message timing
• Message delivery options

#### 3.1.6 Message Encoding
One of the first steps to sending a message is encoding. Encoding is the process of onverting information into another acceptable form, for transmission. Decoding reverses this process to interpret the information.

#### 3.1.7 Message Formatting and Encapsulation

When a message is sent from source to destination, it must use a specific format or structure. Message formats depend on the type of message and the channel that is used to deliver the message.

#### 3.1.8 Message Size

ANother rule of communication is message sieze

#### 3.1.9 Message Timing

Message timing is also very important in network communications. Message timing includes the following:
• Flow Control - This is the process of managing the rate of data transmission.
Flow control defines how much information can be sent and the speed at which it can be delivered. For example, if one person speaks too quickly, it may be difficult for the receiver to hear and understand the message. In network communication, there are network protocols used by the source and destination devices to negotiate and manage the flow of information.
• Response Timeout - If a person asks a question and does not hear a response within an acceptable amount of time, the person assumes that no answer is coming and reacts accordingly. The person may repeat the question or instead, may go on with the conversation. Hosts on the network use network protocols that specify how long to wait for responses and what action to take if a response timeout occurs.
• Access method - This determines when someone can send a message. Click Play in the figure to see an animation of two people talking at the same time, then a "collision of information" occurs, and it is necessary for the two to back off and start again. Likewise, when a device wants to transmit on a wireless LAN, it is necessary for the WLAN network interface card (NIC) to determine whether the wireless medium is available.


#### 3.1.10 Message Delivery Options

A message can be delivered in different ways.

#### 3.1.11 A note about the node icon
Networking documents and topologies often represent networking and end devices using a node icon. Nodes are typically represented as a circle. The figure shows a comparison of the three different delivery options using node icons instead of computer icons.

###### Quiz: 
What is the process of converting information into the proper form for transmission?
Formatting
Encoding
Encapsulation




Which step of the communication process is concerned with properly identifying the address of the sender and receiver?
Formatting
Course content
Encoding
Encapsulation


Which three are components of message timing? (Choose three.)
Flow control
Sequence numbers
Access method
Retransmit time
Response timeout


Which delivery method is used to transmit information to one or more end devices, but not all devices on the network?
Unicast
Multicast
Broadcast



### 3.2 Protocols

#### 3.2.1 Network Protocol Overview 
You know that for end devices to be able to communicate over a network, each device must abide by the same set of rules. These rules are called protocols and they have many functions in a network. This topic gives you a overview of network protocols.
Network protocols define a common format and set of rules for exchanging messages between devices. Protocols are implemented by end devices and intermediary devices in software, hardware, or both. Each network protocol has its own function, format, and rules for communications.
The table lists the various types of protocols that are needed to enable communications across one or more networks.


Network Communications Protocols :Protocols enable two or more devices to communicate over one or more networks. The Ethernet family of technologies involves a variety of protocols such as IP, Transmission Control Protocol (TCP), HyperText Transfer Protocol (HTTP), and many more.


Network Security Protocols :Protocols secure data to provide authentication, data integrity, and data encryption. Examples of secure protocols include Secure Shell (SSH), Secure Sockets Layer (SSL), and Transport Layer Security (TLS).

Routing Protocols: Protocols enable routers to exchange route information, compare path information, and then to select the best path to the destination network. Examples of routing protocols include Open Shortest Path First (OSPF) and Border Gateway Protocol (BGP).


Service Discovery Protocols: Protocols are used for the automatic detection of devices or services. Examples of service discovery protocols include Dynamic Host Configuration Protocol (DHCP) which discovers services for IP address allocation, and Domain Name System (DNS) which is used to perform name-to-IP address translation.

#### 3.2.2 Network Protocol Functions

Network communication protocols are responsible for a variety of functions necessary for network communications between end devices. For example, in the figure how does the computer send a message, across several network devices, to the server?

Addressing
This identifies the sender and the intended receiver of the message using a defined addressing scheme. Examples of protocols that provide addressing include Ethernet, IPv4, and IPv6.
Reliability
This function provides guaranteed delivery mechanisms in case messages are lost or corrupted in transit. TCP provides guaranteed delivery.
Flow control
This function ensures that data flows at an efficient rate between two communicating devices. TCP provides flow control services.
Sequencing
This function uniquely labels each transmitted segment of data.
The receiving device uses the sequencing information to reassemble the information correctly. This is useful if the data segments are lost, delayed or received out-of-order. TCP provides sequencing services.
Error Detection
This function is used to determine if data became corrupted during transmission. Various protocols that provide error detection include Ethernet, IPv4, IPv6, and TCP.
Application Interface
This function contains information used for process-to-process communications between network applications. For example, when accessing a web page, HTTP or HTTPS protocols are used to communicate between the client and server web processes.

#### 3.2.3 Protocol Interaction

A message sent over a computer network typically requires the use of several protocols, each one with its own functions and format. The figure shows some common network protocols that are used when a device sends a request to a web server for its web page.

Hypertext Transfer Protocol (HTTP) - This protocol governs the way a web server and a web client interact. HT TP defines the content and formatting of the requests and responses that are exchanged between the client and server. Both the client and the web server software implement HTTP as part of the application. HTTP relies on other protocols to govern how the messages are transported between the client and server.
• Transmission Control Protocol (TCP) - This protocol manages the individual conversations. TCP is responsible for guaranteeing the reliable delivery of the information and managing flow control between the end devices.
• Internet Protocol (IP) - This protocol is responsible for delivering messages from the sender to the receiver. IP is used by routers to forward the messages across multiple networks.
• Ethernet- This protocol is responsible for the delivery of messages from one NIC to another NIC on the same Ethernet local area network (LAN).

###### Quiz: 
BGP and OSPF are examples of which type of protocol?
Network communication
Network security
Routing
Service discovery


which two protocols are service discovery protocols? (Choose two.)
DNS
TCP
SSH
DHCP

What is the purpose of the sequencing function in network communication?
To uniquely label transmitted segments of data for proper reassembly by the receiver
To determine if data is corrupted during transmission
To ensure data flows at an efficient rate between sender and receiver
To guarantee delivery of data


This protocol is responsible for guaranteeing the reliable delivery of information.
TCP
HTTP
Ethernet


### 3.3 Protocols Suits
#### 3.3.1 Network Protocol Suites 
#### 3.3.2 Evolution of Protocol Suites 
#### 3.3.3 TCP/IP Protocol Example
#### 3.3.4 TCP/IP Protocol Suite
#### 3.3.5 NTCP/IP Communication Process







### 3.4 Standards Organisations 
#### 3.4.1 Open Standards 
#### 3.4.2 Internet Standards
#### 3.4.3 Electronic and communications Standards 







### 3.5 Reference Models
#### 3.5.1 The benefits of using a layered model
#### 3.5.2 The OSI reference model
#### 3.5.3 TCP/IP Protocol Model
#### 3.5.4 OSI and TCP/IP model comparison



### 3.6 Data Encapsulation
#### 3.6.1 Segmenting Messages
#### 3.6.2 Sequencing
#### 3.6.3 Protocol data units
#### 3.6.4 Encapsulation 
#### 3.6.5 De-capsulation






### 3.7 Data Access
#### 3.7.1 Addresses
#### 3.7.2 Layer 3 Logical Address
#### 3.7.3 Devices on the same network
#### 3.7.4 Role of the datalink layer addresses - same IP network
#### 3.7.5 Devices on a remote network
#### 3.7.6 Role of the network layer addresses 
#### 3.7.7 Role of the sata link layer addreses- different IP Network
#### 3.7.8 Data link Addresses  



