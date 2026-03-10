# 4.1 Data Link Layer Protocols
## 4.1.1 Purpose of the Data Link Layer
### The Data Link Layer
- The Data Link layer is responsible for communications between end-device network interface cards.
- It allows upper layer protocols to access the physical layer media and encapsulates Layer 3 packets (IPv4 and IPv6) into Layer 2 Frames.
- It also performs error detection and rejects corrupt frames.
  ![[Pasted image 20260309120247.png]]
### IEEE 802 LAN/MAN Data Link Sublayers
IEEE 802 LAN/MAN standards are specific to the type of network (Ethernet, WLAN, WPAN, etc).
![[Pasted image 20260309120513.png]]
The Data Link Layer consists of two sublayers. Logical Link Control (LLC) and Media Access Control (MAC).
- The LLC sublayer communicates between the networking software at the upper layers and the device hardware at the lower layers.
- The MAC sublayer is responsible for data encapsulation and media access control.
### Providing Access to Media
- Packets exchanged between nodes may experience numerous data link layers and media transitions.
- At each hop along the path, a router performs four basic Layer 2 functions:
	- Accepts a frame from the network medium
	- De-encapsulates the frame to expose the encapsulated packet.
	- Re-encapsulates the packet into a new frame.
	- Forwards the new frame on the medium of the next network segment.
### Data Link Layer Standards
Data link layer protocols are defined by engineering organizations:
- Institute for Electrical and Electronic Engineers (IEEE)
- International Telecommunications Union (ITU)
- International Organizations for Standardization (ISO)
- American National Standards Institute (ANSI)
  ![[Pasted image 20260309121044.png]]
- IEEE
	- 802.2 Logical Link Control (LLC)
	- 802.3 Ethernet
	- 802.4 Token bus
	- 802.5 Token passing
	- 802.11 Wireless LAN (WLAN) & Mesh (Wi-Fi certification)
	- 802.15 Bluetooth
	- 802.16 WiMax
- ITU-T 
	- G.992 ADSL
	- G.8100 - G.8199 MPLS over Transport aspects
	- Q.921 ISDN
	- Q.922 Frame Relay
- ISO
	- HDLC (High Level Data Link Control)
	- ISO 9314 FDDI Media Access Control (MAC)
- ANSI
	- X3T9.5 and X3T12 Fiber Distributed Data Interface (FDDI)
### Layer 2 Standards
![[Pasted image 20260309121900.png]]
# 4.2 Topologies and Media Access Control
### Physical and Logical Topologies
The topology of a network is the arrangement and relationship of the network devices and the interconnections between them.

There are two types of topologies used when describing networks:
- Physical topology - shows physical connections and how devices are interconnected.
- Logical topology - Identifies the virtual connections between devices using device interfaces and IP addressing schemes.
### WAN Topologies
There are three common physical WAN topologies:
- Point-to-point - The simplest and most common WAN topology. Consists of a permanent link between two endpoints.
- Hub and spoke - Similar to a start topology where a central site interconnects branch sites through point-to-point links.
- Mesh - Provides high availability but requires every end system to be connected to every other end system.
### Point-to-Point WAN Topology
- Physical point-to-point topologies directly connect two nodes.
- The nodes may not share the media with other hosts.
- Because all frames on the media can only travel to or from the two nodes, Point-to-Point WAN protocols can be very simple.
  ![[Pasted image 20260309122659.png]]
### Logical Point-to-Point Topology
![[Pasted image 20260309122739.png]]
- The media access method uses by the data link protocol is determined by the logical point-to-point topology, not the physical topology.
- This means that the logical point-to-point connection between two nodes may not necessarily be between two physical nodes at each end of a single physical link.
### LAN Topologies
End devices on LANs are typically interconnected using a start or extended star topology. Star and extended star topologies are easy to install, very scalable and easy to troubleshoot.

Early Ethernet and Legacy Token Ring technologies provide two additional topologies:
- Bus - All end systems chained together and terminated on each end.
- Ring - Each end system is connected to its respective neighbors to form a ring.
  ![[Pasted image 20260309123121.png]]
### Half and Full Duplex Communications
- Half-Duplex communication
	- Only allows one device to send or receive at a time on a shared medium.
	- Used on WLANs and legacy bus topologies with Ethernet hubs.
- Full-duplex communication
	- Allows both devices to simultaneously transmit and receive on a shared medium.
	- Ethernet switches operate in full-duplex mode.
  ![[Pasted image 20260309123345.png]]
### Access Control Methods
- Contention-based access - All nodes operating in half-duplex, competing for use of the medium.
	- Carrier sense multiple access with collision detection (CSMA/CD) as used on legacy bus-topology Ethernet.
	- Carrier sense multiple access with collision avoidance (CSMA/CA) as used on Wireless LANs.
- Controlled access
	- Deterministic access where each node has its own time on the medium.
	- Used on legacy networks such as a Token Ring and ARCNET.
### Contention-Based Access
![[Pasted image 20260309123848.png]]
#### Characteristics
- Stations can transmit at any time
- Collision exist
- There are mechanism to resolve contention for the media
#### Contention-Based Technologies
- CSMA/CD for 802.3 Ethernet networks WITH HUB,
- If you wrongly configure your switch from full duplex to become half duplex, then use contention based access method
- CSMA/CA for 802.11 wireless networks
### Contention-Based Access - CSMA/CD
#### CSMA/CD
- Used by legacy Ethernet LANs
- Operates in half-duplex mode where only one device sends or receives at a time
- Uses a collision detection process to govern when a device can send and what happens if multiple devices send at the same time.
#### CSMA/CD collision detection process
- Devices transmitting simultaneously will result in a signal collision on the shared media
- Devices detect the collision.
- Devices wait a random period of time and retransmit data.
### Contention-Based Access - CSMA/CA
CSMA/CA
- Used by IEEE 802.11 WLANs
- Operates in half-duplex mode where only one device sends or receives at a time. 
- Uses a collision avoidance process to govern when a device can send and what happens if multiple devices send at the same time.
CSMA/CA collision avoidance process
- When transmitting, devices also include the time duration needed for the transmission.
- Other devices on the shared medium receive the time duration information and know how long the medium will be unavailable
### Controlled Access
![[Pasted image 20260309124612.png]]
#### Characteristics
- Only one station can transmit at a time
- Devices wishing to transmit must wait their turn
- No collisions
- May use a token passing method
#### Controlled Access Technologies
- Token Ring (IEEE 802.5)
- Fiber Distributed Data Interface (FDDI)
### Media Access Control Methods
![[Pasted image 20260309125237.png]]
- Controlled Access
	- Each node has its own time to use the medium.
	- Legacy Token Ring LANs are an example
## 4.3 Data Link Frame
### The Frame
Data is encapsulated by the data link layer with a header and a trailer to form a frame.
A data link frame has three parts:
- Header
- Data
- Trailer
The fields of the header and trailer vary according to data link layer protocol.
The amount of control information carried with in the frames varies according to access control information and logical topology.
#### Frame Fields
![[Pasted image 20260309125942.png]]


| Field                | Description                              |
| -------------------- | ---------------------------------------- |
| Frame Start and Stop | Identifies beginning and end of frame    |
| Addressing           | Indicates source and destination nodes   |
| Type                 | Identifies encapsulated Layer 3 protocol |
| Control              | Identifies flow control services         |
| Data                 | Contains the frame payload               |
| Error Detection      | Used for determine transmission errors   |
#### Layer 2 Addresses
- Also referred to as a physical address
- Contained in the frame header
- Used only for local delivery of a frame on the link
- Updated by each device that forwards the frame
![[Pasted image 20260309130207.png]]
#### LAN and WAN Frames
The logical topology and physical media determine the data link protocol used:
- Ethernet
- 802.11 Wireless
- Point-to-Point (PPP)
- High-Level Data Link Control (HDLC)
- Frame-Relay
Each protocol performs media access control for specified logical topologies.
![[Pasted image 20260309130419.png]]
#### The Frame
![[Pasted image 20260309130536.png]]![[Pasted image 20260309130547.png]]
- Header - Contains control information, such as addressing, and is located at the beginning of the PDU.
- Data - Contains the IP header, transport layer header and application data
- Trailer - Contains control information for error detection added to the end of the PDU.