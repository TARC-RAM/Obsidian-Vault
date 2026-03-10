## 5.1 Ethernet Protocol 
### Ethernet Encapsulation
Ethernet operates in the data link layer and the physical layer. It is a family of networking technologies defined in the IEEE 802.2 and 802.3 standards.
![[Pasted image 20260302131023.png]]
### Data Link Sublayers
The 802 LAN/MAN standards, including Ethernet, use two separate sublayers of the data link layer to operate:
- LLC Sublayer: (IEEE 802.2) Places information in the frame to identify which network layer protocol is used for the frame.
- MAC Sublayer: (IEEE 802.3, 802.11, or 802.15) Responsible for data encapsulation and media access control, and provides data link layer addressing.

# 5.2 LAN Switches
## 5.2.1 The MAC Address Table
### Switch Fundamentals
- A Layer 2 Ethernet switch makes it forwarding decisions based only on the Layer 2 Ethernet MAC addresses.
- A switch that is powered on, will have an empty MAC address table as it has not yet learned the MAC addresses for the four attached PCs.
- Note: The MAC address table is sometimes referred to as a content addressable memory (CAM) table.
### Learning MAC Addresses
- The switch dynamically builds the MAC address table. The process to learn the Source MAC Address is:
	- Switches examine all incoming frames for new source MAC address information to learn.
	- If the source MAC address is unknown, it is added to the table along the port number.
	- If the source MAC address does exist, the switch updates the refresh timer for that entry.
	- By default, most Ethernet switches keep an entry in the table for 5 minutes.
- The process to forward the Destination MAC Address is:
	- If the destination MAC address is a broadcast or a multicast, the frame is also flooded out all ports except the incoming port.
	- If the destination MAC address is a unicast address, the switch will look for a match in its MAC address table.
	- If the destination MAC address is in the table, it will forward the frame out the specified port.
	- If the destination MAC address is not in the table (i.e an unknown unicast) the switch will forward the frame out all ports except the incoming port.
### Switching Process
**Learn** - Examining the Source MAC Address
- Switches examine all incoming frames for new source MAC address information to learn.
- If the source MAC address is unknown, it is added to the table along with the port number.
- If the source MAC address does not exist, the switch updates the refresh timer for that entry.
- By default, most Ethernet switches keep an entry in the table for 5 minutes.
**Forward** - Examining the Destination MAC Address
- If the destination MAC address is a broadcast or a multicast, the frame is also flooded out all ports except the incoming port.
- If the destination MAC address is a unicast address, the switch will look for a match in its MAC address table.
	- If the destination MAC address is in the table, it will forward the frame out the specified port.
	- If the destination MAC address is not in the table (i.e an unknown unicast) the switch will forward the frame out all ports except the incoming port.
# 5.2 LAN Switches
## 5.2.2 Switch Speeds and Forwarding Methods
### Memory Buffering on Switches
- An Ethernet switch may use a memory buffering technique to store frames before forwarding them. Buffering may also be used when the destination port is busy due to congestion and the switch stores the frame until it can be transmitted.
- There are two types of memory buffering techniques:
	- Port-based memory
		- Frames are stored in queues that are linked to specific incoming and outgoing ports.
		- A frame is transmitted when all the frames ahead of it have been transmitted.
	- Shared memory
		- All frames are deposited into a common buffer which is shared by all ports on the switch.
### Duplex Settings
**Half Duplex (CSMA/CD)**
- Unidirectional data flow
- Higher potential for collision 
- Hub connectivity
![[Pasted image 20260302134353.png]]
### Full Duplex
- Point-to-point only
- Attached to dedicated switched port
- Requires full-duplex support on both ends
- Collision-free
- Collision detect circuit disabled
### Duplex and Speed Settings
- There are two types of duplex settings used for communications on an Ethernet network:
	- Full Duplex - Both ends of the connection can send and receive simultaneously.
	- Half Duplex - Only one end of the connection can send at a time.
- Most devices use auto negotiation which enables two devices to automatically exchange information about speed and duplex capabilities and choose the highest performance mode.
- **Duplex mismatch** is a common cause of performance issues with Ethernet links. It occurs when one port on the link operates at half-duplex while the other port operates at full-duplex.
### Auto-MDIX
- Connections between specific devices such as switch-to-switch, switch-to-router, switch-to-host, and router-to-host devices. once required the use of specific cable types (crossover or straight-through).
- Most switch devices now support the automatic medium-dependent interface crossover (auto-MDIX) feature. This is enabled by default on switches since IOS 12.2(18)SE.
- When enabled using the MDIX auto interface configuration command, the switch detects the type of cable attached to the port, and configures the interface accordingly.
# 5.3 Address Resolution Protocol
## 5.3.1 MAC and IP
### Destination on Remote Network
- When the destination IP address is on a remote network, the destination MAC address will be the address of the host's default gateway.
- In this figure, PC-A is sending an IP packet to a web server on a remote network.
	- The destination IP address is that of the File Server.
	- The destination MAC address is that of Ethernet interface of R1.
### Destination on Remote Network
When the destination IP address is on a remote network, the destination MAC address is that of the default gateway.
- ARP is used by IPv4 to associate the IPv4 address of a device with the MAC address of the device NIC.
- ICMPv6 is used by IPv6 to associate the IPv6 address of a device with the MAC address of the device NIC.
## 5.3.2 ARP
### Introduction to ARP
- When a device sends an Ethernet frame, it contains these two addresses:
	- Destination MAC address
	- Source MAC address
- ARP Purpose
	- Sending node needs a way to find the MAC address of the destination for a given Ethernet link
	- To determine the destination MAC address, the device uses ARP
- ARP Purpose
	- Sending node needs a way to find the MAC address of the destination for a given Ethernet link
	- To determine the destination MAC address, the device uses ARP
- ARP provides two basic functions:
	- Resolving IPv4 addresses to MAC addresses
	- Maintaining an ARP table of IPv4 to MAC address mappings
### ARP Functions
- Ethernet devices refer to an ARP table (or the ARP cache) in its memory (i.e RAM) to find the MAC address that is mapped to the IPv4 address.
- A device will search its ARP table for a destination IPv4 address and a corresponding MAC address.
	- If the packets destination IPv4 address is on the same network as the source IPv4 address, the device will search the ARP table for the destination IPv4 address.
	- If the destination IPv4 address is on a different network than the source IPv4 address, the device will search the ARP table for the IPv4 address of the default gateway.
### Video Demonstration - ARP Request
- An ARP request is a broadcast frame sent when a device needs a MAC address associated with an IPv4 address, and it does not have an entry for the IPv4 address in its ARP table.
- ARP messages are encapsulated directly within an Ethernet frame. There is no IPv4 header.
- The ARP request message includes:
	- Target IPv4 address
	- Target MAC address
### ARP Broadcasts
- As a broadcast frame, an ARP request is received and processed by every device on the local network.
- ARP requests can flood the local segment if a large number of devices were to be powered up and all start accessing network services at the same time.
### ARP Reply
- Only the device with an IPv4 address associated with the target IPv4 address in the ARP request will respond with an ARP reply.
- The ARP reply message includes:
	- Sender's IPv4 address
	- Sender's MAC address
- Entries in the ARP table are time stamped if a device does not receive a frame from a particular device by the time the timestamp expires, the entry for this device is removed from the ARP table.
### ARP Role in Remote Communication
- If the destination IPv4 host is on the local network, the frame will use the MAC address of this device as the destination MAC address.
- if the destination IPv4 host is not on the local network, the source uses the ARP process to determine a MAC address for the router interface serving as the gateway.
- In the event that the gateway entry is not in the table, an ARP request is used to retrieve the MAC address associated with the IP address of the router interface.
- When a host creates a packet for a destination, it compares the destination IPv4 address and its own IPv4 address to determine if the two IPv4 addresses are located on the same Layer 3 network.
- If the destination IPv4 host is on the local network, the frame will use the MAC address of this device as the destination MAC address
- If the destination IPv4 host is not on the local network, the source uses the ARP process to determine a MAC address for the router interface serving as the gateway
- In the event that the gateway entry is not in the table, an ARP request is used to retrieve the MAC address associated with the IP address of the router interface
### Removing Entries from an ARP Table
- Entries in the ARP table are not permanent and are removed when an ARP cache timer expires after a specified period of time.
- The duration of the ARP cache timer differs depending on the operating system.
- ARP table entries can also be removed manually by the administrator.
### ARP Tables on Networking Devices
- The show ip arp command displays the ARP table on a Cisco router.
- The arp -a command displays the ARP table on a Windows 10 PC.
### ARP Issues - ARP Broadcasting and ARP Spoofing
- ARP request are received and processed by every device on the local network.
- Excessive ARP broadcasts can cause some reduction in performance.
- For example, if a large number of devices were to be powered up and all start accessing network services at the same time.