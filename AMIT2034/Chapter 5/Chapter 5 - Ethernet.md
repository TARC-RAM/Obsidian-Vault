## 5.1 Ethernet Protocol 
### Ethernet Encapsulation
- Ethernet operates in the data link layer and the physical layer. 
- It is a family of networking technologies defined in the IEEE 802.2 and 802.3 standards.
![[Pasted image 20260302131023.png]]
### Data Link Sublayers
The 802 LAN/MAN standards, including Ethernet, use two separate sublayers of the data link layer to operate:
- LLC Sublayer: (IEEE 802.2) Places information in the frame to identify which network layer protocol is used for the frame.
- MAC Sublayer: (IEEE 802.3, 802.11, or 802.15) Responsible for data encapsulation and media access control, and provides data link layer addressing.
  ![[Pasted image 20260310235114.png]]
### MAC Sublayer
The MAC sublayer is responsible for data encapsulation and accessing the media.
#### **Data Encapsulation**
IEEE 802.3 data encapsulation includes the following:
1) Ethernet frame - This is the internal structure of the Ethernet frame.
2) Ethernet Addressing - The Ethernet frame includes both a source and destination MAC address to deliver the Ethernet frame from Ethernet NIC to Ethernet NIC on the same LAN.
3) Ethernet Error detection - The Ethernet frame includes a frame check sequence (FCS) trailer used for error detection.
#### **Media access control**
(i) responsible for the placement of frames on the media and the removal of frames from the media, and (ii) media recovery. This sublayer communicates directly with the physical layer.
#### Media Access
- The IEEE 802.3 MAC sublayer includes the specifications for different Ethernet communications standards over various types of media including copper and fiber.
- Legacy Ethernet using a bus topology or hubs, is a shared, half-duplex medium. Ethernet over a half-duplex medium uses a contention-based access method, carrier sense multiple access/collision detection (CSMA/CD).
- Ethernet LANs of today use switches that operate in full-duplex. Full-duplex communications with Ethernet switches do not require access control through CSMA/CD.
### Ethernet Frame Fields
- The minimum Ethernet frame size is 64 bytes and the maximum is 1518 bytes. The preamble field is not included when describing the size of the frame.
- Any frame less than 64 bytes in length is considered a “collision fragment” or “runt frame” and is automatically discarded. Frames with more than 1500 bytes of data are considered “jumbo” or “baby giant frames”.
- If the size of a transmitted frame is less than the minimum, or greater than the maximum, the receiving device drops the frame. Dropped frames are likely to be the result of collisions or other unwanted signals. They are considered invalid. Jumbo frames are usually supported by most Fast Ethernet and Gigabit Ethernet switches and NICs.
  ![[Pasted image 20260310235814.png]]
### Introduction to the Ethernet Frame
![[Pasted image 20260310235842.png]]
![[Pasted image 20260310235859.png]]
#### Frame Check Sequence Field
Used to detect errors in a frame with cyclic redundancy check (4 bytes), if calculations match at source and receiver, no error occured.
## 5.1.2 Ethernet MAC Address
### MAC Addresses and Hexadecimal
- An Ethernet MAC address is a 48-bit binary value expressed as 12 hexadecimal digits (4 bits per hexadecimal digit).
- Hexadecimal is used to represent Ethernet MAC addresses and IP Version 6 addresses.
- Hexadecimal is a base sixteen system using the numbers 0 to 9 and the letters A to F.
- It is easier to express a value as a single hexadecimal digit than as four binary bits.
- Hexadecimal is usually represented in text by the value preceded by 0x (E.g. 0x73).
  ![[Pasted image 20260311000224.png]]
### Ethernet MAC Address
- In an Ethernet LAN, every network device is connected to the same, shared media. MAC addressing provides a method for device identification at the data link layer of the OSI model.
- An Ethernet MAC address is a 48-bit address expressed using 12 hexadecimal digits. Because a byte equals 8 bits, we can also say that a MAC address is 6 bytes in length.
- All MAC addresses must be unique to the Ethernet device or Ethernet interface. To ensure this, all vendors that sell Ethernet devices must register with the IEEE to obtain a unique 6 hexadecimal (i.e., 24-bit or 3-byte) code called the organizationally unique identifier (OUI).
- An Ethernet MAC address consists of a 6 hexadecimal vendor OUI code followed by a 6 hexadecimal vendor-assigned value.
### MAC Addresses: Ethernet Identity
- IEEE requires a vendor to follow two simple rules:
	- All MAC addresses assigned to a NIC or other Ethernet device must use that vendor's assigned OUI as the first 3 bytes.
	- All MAC addresses with the same OUI must be assigned a unique value in the last 3 bytes.
	  ![[Pasted image 20260311000329.png]]
	  ![[Pasted image 20260311000343.png]]
### Frame Processing
- The MAC address is often referred to as a burned-in address (BIA) meaning the address is encoded into the ROM chip permanently. When the computer starts up, the first thing the NIC does is copy the MAC address from ROM into RAM.
- When a device is forwarding a message to an Ethernet network, it attaches header information to the frame.
- The header information contains the source and destination MAC address.
  ![[Pasted image 20260311000507.png]]
### MAC Address Representations
- Use the ipconfig /all command on a Windows host to identify the MAC address of an Ethernet adapter. On a MAC or Linux host, the ifconfig command is used.
- Depending on the device and the operating system, you will see various representations of MAC addresses.
  ![[Pasted image 20260311000602.png]]
### Frame Processing 
- MAC addresses assigned to workstations, servers, printers, switches, and routers
- Example MACs: 00-05-9A-3C-78-00, 00:05:9A:3C:78:00, or 0005.9A3C.7800.
- Forwarded message to an Ethernet network, attaches header information to the packet, contains the source and destination MAC address
- Each NIC views information to see if the destination MAC address in the frame matches the device’s physical MAC address stored in RAM
- No match, the device discards the frame
- Matches the destination MAC of the frame, the NIC passes the frame up the OSI layers, where the decapsulation process takes place
### Unicast MAC Address
- A unicast MAC address is the unique address used when a frame is sent from a single transmitting device to a single destination device.
- For a unicast packet to be sent and received,a destination IP address must be in the IP packet header and a corresponding destination MAC address must also be present in the Ethernet frame header. 
  ![[Pasted image 20260311000949.png]]
### Broadcast MAC Address
- Many network protocols, such as DHCP and ARP, use broadcasts.
- A broadcast packet contains a destination IPv4 address that has all ones (1s) in the host portion indicating that all hosts on that local network will receive and process the packet.
- When the IPv4 broadcast packet is encapsulated in the Ethernet frame, the destination MAC address is the broadcast MAC address of FF-FF-FF-FF-FF-FF in hexadecimal (48 ones in binary).
  ![[Pasted image 20260311001434.png]]
### Multicast MAC Address
- Multicast addresses allow a source device to send a packet to a group of devices.
- Devices in a multicast group are assigned a multicast group IP address in the range of 224.0.0.0 to 239.255.255.255 (IPv6 multicast addresses begin with FF00::/8).
- The multicast IP address requires a corresponding multicast MAC address that begins with 01-00-5E in hexadecimal.
  ![[Pasted image 20260311001906.png]]

# 5.2 LAN Switches
## 5.2.1 The MAC Address Table
### Switch Fundamentals
- A Layer 2 Ethernet switch makes it forwarding decisions based only on the Layer 2 Ethernet MAC addresses.
- A switch that is powered on, will have an empty MAC address table as it has not yet learned the MAC addresses for the four attached PCs.
- Note: The MAC address table is sometimes referred to as a content addressable memory (CAM) table.
  ![[Pasted image 20260311103154.png]]
### Learning MAC Addresses
- The switch dynamically builds the MAC address table. The process to learn the Source MAC Address is:
	- Switches examine all incoming frames for new source MAC address information to learn.
	- If the source MAC address is unknown, it is added to the table along the port number.
	- If the source MAC address does exist, the switch updates the refresh timer for that entry.
	- By default, most Ethernet switches keep an entry in the table for 5 minutes.
	  ![[Pasted image 20260311103221.png]]
- The process to forward the Destination MAC Address is:
	- If the destination MAC address is a broadcast or a multicast, the frame is also flooded out all ports except the incoming port.
	- If the destination MAC address is a unicast address, the switch will look for a match in its MAC address table.
	- If the destination MAC address is in the table, it will forward the frame out the specified port.
	- If the destination MAC address is not in the table (i.e an unknown unicast) the switch will forward the frame out all ports except the incoming port.
	  ![[Pasted image 20260311103248.png]]
### Learning MAC Address
#### Switching Process
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
### Filtering Frames
- As a switch receives frames from different devices, it is able to populate its MAC address table by examining the source MAC address of every frame.
- When the switch’s MAC address table contains the destination MAC address, it is able to filter the frame and forward out a single port.
  ![[Pasted image 20260311103620.png]]
# 5.2 LAN Switches
## 5.2.2 Switch Speeds and Forwarding Methods
### Frame Forwarding Methods on Cisco Switches
Switches use one of the following forwarding methods for switching data between network ports:
- Store-and-forward
	- A store-and-forward switch receives the entire frame, and computes the CRC. If the CRC is valid, the switch looks up the destination address, which determines the outgoing interface. The frame is then forwarded out the correct port.
- Cut-through
	- A cut-through switch forwards the frame before it is entirely received. At a minimum, the destination address of the frame must be read before the frame can be forwarded.
### Cut-Through Switching
- In cut-through switching, the switch buffers just enough of the frame to read the destination MAC address so that it can determine to which port to forward the data. The switch does not perform any error checking on the frame.
- There are two variants of cut-through switching:
	- Fast-forward switching offers the lowest level of latency. The switch immediately forwards a packet after reading the destination address. This is the most typical form of cut-through switching.
	- Fragment-free switching, in which the switch stores the first 64 bytes of the frame before forwarding. It is a compromise between store-and-forward and fast-forward switching.
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
![[Pasted image 20260311104203.png]]
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
### Destination on Same Network
- There are two primary addresses assigned to a device on an Ethernet LAN:
	- Layer 2 physical address (the MAC address) – Used for NIC to NIC communications on the same Ethernet network.
	- Layer 3 logical address (the IP address) – Used to send the packet from the source device to the destination device.
Layer 2 addresses are used to deliver frames from one NIC to another NIC on the same network. If a destination IP address is on the same network, the destination MAC address will be that of the destination device.
![[Pasted image 20260311104449.png]]
### Destination on Remote Network
- When the destination IP address is on a remote network, the destination MAC address will be the address of the host's default gateway.
- In this figure, PC-A is sending an IP packet to a web server on a remote network.
	- The destination IP address is that of the File Server.
	- The destination MAC address is that of Ethernet interface of R1.
	  ![[Pasted image 20260311104527.png]]
### Destination on Remote Network
When the destination IP address is on a remote network, the destination MAC address is that of the default gateway.
- ARP is used by IPv4 to associate the IPv4 address of a device with the MAC address of the device NIC.
- ICMPv6 is used by IPv6 to associate the IPv6 address of a device with the MAC address of the device NIC.
  ![[Pasted image 20260311104607.png]]
# 5.3 Address Resolution Protocol
## 5.3.2 ARP
### Introduction to ARP
- When a device sends an Ethernet frame, it contains these two addresses:
	- Destination MAC address
	- Source MAC address
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
  ![[Pasted image 20260311104746.png]]
### Video Demonstration - ARP Reply
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
### ARP Spoofing
- Attackers can respond to requests and pretend to be providers of services.
- One type of ARP spoofing attack used by attackers is to reply to an ARP request for the default gateway. In the figure, host A requests the MAC address of the default gateway. Host C replies to the ARP request. Host A receives the reply and updates its ARP table. It now sends packets destined to the default gateway to the attacker host C.
- Enterprise level switches include mitigation techniques known as dynamic ARP inspection (DAI).