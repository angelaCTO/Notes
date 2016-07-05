##Fundamentals : Part One 

---

###Basic Networking Concepts

| **Terminology** |                                                                                                                      |
| :-----------: | :--------------------------------------------------------------------------------------------------------------------- | 
| **Entity** | Some *thing* that does some *function*.<ul><li>An entity on a *physical network* (eg., it can communicate with other nodes using the same network medium) is a **network node**. If that network is connected to other networks in an internet, that node is also an **internet node**.</ul></li><ul><li>Internet nodes interoperate with protocols that can pass across network boundaries.</ul></li><ul><li>Network nodes communicate with each other using protocols that format and package data for transmission on a shared network medium</ul></li> |
| **System ("Black Box")** | Any entity with observable and reproduceable behaviors. A system accepts input and produces a consistent output.<ul><li>**Autonomous System (AS)** - A network that can be seen to behave as if it is completely self-contained (eg. *black box*)</ul></li> |
| **Network** | Some set of systems that share a common communication medium. |
| **Media/medium** | The physical thing(s) over or through which network signals are carried.<ul><li>**Link** - A shared medium and the set of rules governing transmissions on that medium.</ul></li> | 
| **Internet** | Network of networks. An internet may use a single physical medium or span different physical media by using a virtual medium. |
| **Interface** | The point at which two entities make contact<ul><li>Network interfaces convert a node's data into electronic signals for transmission over a metal wire, or into signals for transmission appropriate for optical cable, or for wireless radio transmission, etc.<ul><li>Ex. A *Network Interface Card (NIC)* provides a point of contact between a PC and an Ethernet LAN. The node (PC) passes data intended for the network to the NIC, which then takes that data and after re-formatting it into a form appropriate for the network sends it out onto the cable.</ul></li></ul></li> |
| **Node** | Any entity connected to a network and capable of both creating and using network data. |
| **Host** | Any node that supports users and runs application software. (Host and node are often used interchangeably, but the two are distinct types of entity |
| **Client** | A network entity that requests some network service from a server. | 
| **Server** | A network entity that fulfills requests from clients. |
| **LAN (Local Area Network)** | Usually a network that connects nodes across a small distance using direct physical mechanisms with minimal use of infrastructure devices such as *routers* or *switches* to relay data. |
| **WAN (Wide Area Network)** | Usually a network that connects nodes across great distances.<ul><li>**MAN (Metropolis Area Network)** </ul></li><ul><li>*(loosely)* LAN < MAN < WAN</ul></li> |
| **SAN (Storage Area Network)** | A network of dedicated storage devices |
| **Router** | A system that applies intelligence to the movement of network data.<ul><li>*Intelligence* implies both knowledge of *the current state of the internet* and *the application of rules while processing network data* (ie. the router *knows* what/which connections are available and is also able to process data contained in packets to determine which connections should be used.</ul></li><ul><li>Usually operates only on network data, particularly the data's destination (without looking beyond that eg, unlike a router, a **Gateway** looks beyond that destination information and translates network data into a form useable at the destination)<ul><li>**Application Gateway** - A system that *translates* data from one application into a form that will make it accessible to another applpication.</ul></li></ul></li><ul><li>Routers and gateways are terms that describe systems that act as interfaces to other systems.</ul></li> |
| **Protocol** | A set of rules that define how systems interact<ul><li>A protocol must specify:<ul><li>How entities intitiate a protocol interaction</ul></li><ul><li>What kinds of interactions are permitted</ul></li><ul><li>Valid requests and responses from the entities interacting within the bounds of the protocol</ul></li><ul><li>What to do when an invalid protocol is recieved</ul></li><ul><li>Proper formats for packaging data and protocol messeges (requests/replies)</ul></li><ul><li>Rules about what behaviors and data are acceptable, unacceptable, and preferred (*may*, *should not*, *must*)</ul></li></ul></li> |
| **Protocol Data Unit (PDU)** | A unit of data which is specified in a protocol of a given layer and which consists of protocol control information and possibly user data of that layer (*packet*, *datagram*, *frame*, *segment*)<ul><li>**Datagram** - Term for describing a unit of data that contains just enough information to deliver it to its proper destination (along with whatever network data is being sent)</ul></li><ul><li>**Packet** - Term for describing data passing through internets</ul></li><ul><li>**Segment** - Term for describing data passed between processes</ul></li><ul><li>**Frame** - Term for describing data passed on withing a LAN</ul></li> |

The rules for handling internet communication must take into account the need for *interoperability* across various different network media as well as different network link protocols (eg. Ethernet, ATM, Fibre Channel, etc)
  - **Interoperability** - The ability for systems to communicate and work together with no information about each other beyond compliance with certain standards is a key component of any internetwork protocol.

One of the key goals of TCP/IP networking has always been to enable seamless interoperability across media as well as across computing harware platforms. Ideally, the internet should make it possible for users to share data or resources without concern about what OS, harware, network medium, or software is being used at the other end.

###Network Addressing + Naming
---
A **hostfile** contains the name and address of all nodes in the network. Each node has a local copy of the hostfile. When a new node is added in to the network, its name and address are added into the hostfile. 
  - A *Centralized Server* may manage/propagate hostfile/network updates and may even help translate network names into network addresses, but is difficult to do with large networks with 1000+ nodes and without consuming too much network bandwidth. Centralized systems capable of dynamically serving any significant percentage of the global internet are rare (works well for small populations, but performance degrades with population size increase)
    - Succeptible to dramatic failures, tend to generate a lot of network traffic potentially producing congestion and 
  - A *Distributed System* utilizes different systems distributed across the internet to manage different parts of the system. 

| **Terminology** |                                                                                                                       |
| :-------------: | :-------------------------------------------------------------------------------------------------------------------- |
| **Host Name** | Node name. A single hostname may be shared by more than one node in order to improve responsiveness: all requests to a particular hostname can be shared among several systems. A single node may respond to more than one name to improve efficiency: a single node may host many services, with many names |
| **Domain Name** | Identifies the system within which hostnames are administered. (ex. www.example.com) The domain name is used to manage access to the domain name holder's internet systems. |
| **Fully Qualified Domain Name (FQDN)** | Completely identifies the hostname across the entire naming domain by concatenating a hostname with a domain name (ex. dilbert.example.com, dilbert.example.net) |
| **Mail Address** | Points to some entity (individual, or group) by often incorporating host and domain names |
| **Domain Name System (DNS)** | System used in the internet for linking names with addresses. Submit a request to *resolve* a FQDN to the DNS and it will respond with a numerical address to which to send any data intended for that name |

