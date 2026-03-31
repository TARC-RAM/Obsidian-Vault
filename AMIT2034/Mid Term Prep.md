# LAN and WAN
Provide TWO (2) differences between

| LAN                                                                                                              | WAN                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LAN is a computer network covering a small geographic area, like a home, office, school or a group of buildings. | WAN is a computer network that covers a broad area or any network whose communications links cross metropolitan, regional, or national boundaries over a long distance |
| LANs have a high data transfer rate                                                                              | WANs have a lower data transfer rate compared to LANs                                                                                                                  |
| Typically owned, controlled and managed by a single person or organization                                       | WANs are not owned by any one organization but rather exist under collective or distributed ownership and management over long distances.                              |
| Tend to use certain connectivity technologies, primarily Ethernet and Token Ring                                 | WANs tend to use technologies like MPLS, ATM, Frame Relay and X.25 for connectivity over longer distances                                                              |
# Intermediary devices
An intermediary device interconnects end devices. Examples include:
- Wireless Router
- LAN Switch
- Router
- Multilayer Switch
- Firewall Appliance
The roles of Intermediary devices are:
- Management of data as it flows through a network.
- Regenerate and retransmit data signals.
- Maintain information about what pathways exist in the network.
- Notify other devices of errors and communication failures.
# Network Media

| Media Types                                                | Description                                                       |
| ---------------------------------------------------------- | ----------------------------------------------------------------- |
| Metal wires within<br>cables                               | Uses electrical impulses                                          |
| Glass or plastic fibers within cables (fiber- optic cable) | Uses pulses of light.                                             |
| Wireless transmission                                      | Uses modulation of specific frequencies of electromagnetic waves. |
## 1) Copper Cabling
#### Characteristics
- Inexpensive
- Easy to install
- Low resistance to electrical current flow
#### Limitations
- Attenuation - The longer the electrical signals have to travel, the weaker they get.
- The electrical signal is susceptible to interference from two sources (Electromagnetic Interference (EMI) and Radio Frequency Interference (RFI) and Crosstalk) which can distort and corrupt the data signals.
#### Mitigation (Methods to Reduce Signal Interference)
- Strict adherence to cable length limits will **mitigate attenuation**.
- Some kinds of copper cable mi**tigate EMI and RFI** by using m**etallic shielding and grounding.**	
- Some kinds of copper cable **mitigate crosstalk** by twisting opposing circuit pair wires together.
  ![[Pasted image 20260223131644.png]]
#### Types of Copper Cabling
- Unshielded Twister-Pair (UTP) Cable
	- Terminated with RJ-45 connectors
	- Interconnects host with intermediary network devices
- Shielded Twister-Pair (STP) Cable
	- Better noise protection than UTP
	- More expensive 
	- Harder to install
	- Terminated with RJ-45 connectors
	- Interconnects host with intermediary network devices
- Coaxial Cable
- Coaxial cable has thick shielding which reduces electromagnetic interference much more effectively than UTP.
- Signals can travel further in coaxial cable before becoming weak compared to standard UTP Ethernet runs.
- Its single central conductor and layered shielding design naturally prevents signals from disturbing each other.
- Coaxial provides more consistent performance in environments with heavy electrical noise. 
#### Characteristics of the Copper Cables
- - Unshielded Twister-Pair (UTP) 
	- The outer jacket protects the copper wires from physical damage.
	- Twisted pairs protect the signal from interference
	- Color-coded plastic insulation electrically isolates the wire from each other and identifies each pair.
- Shielded Twister-Pair (STP)
	- The outer jacket protects the copper wires from physical damage
	- Braided and Foil shield provides EMI/RFI protection
	- Color-coded plastic insulation electrically isolates the wire from each other and identifies each pair.
- Coaxial
	- Outer cable jacket to prevent minor physical damage
	- A woven copper braid, or metallic foil, acts as the second wire in the circuit and as a shield for the inner conductor.
	- A layer of flexible plastic insulation
	- A copper conductor is used to transmit the electronic signals

# 3.2.3 Fiber-Optic Cabling
### Properties of Fiber-Optic Cabling
- Not as common as UTP because of the expense involved
- Ideal for some networking scenarios
- Transmits data over longer distances at higher bandwidth than any other networking media
- Less susceptible to attenuation, and completely immune to EMI/RFI
- Made of flexible, extremely thin strands of very pure glass
- Uses a laser or LED to encode bits as pulses of light
- The fiber-optic cable acts as a wave guide to transmit light between the two ends with minimal signal loss.
### Types of Fiber Media
![[Pasted image 20260223134809.png]]
Dispersion refers to the spreading out of a light pulse over time. Increased dispersion means increased loss of signal strength. MMF has greater dispersion that SMF, with the maximum cable distance for MMF is 550 meters.
### Fiber-Optic Cabling Usage
1) Enterprise Networks - Used for backbone cabling applications and interconnecting infrastructure devices
2) Fiber-to-the-Home (FTTH) - Used to provide always-on broadband services to homes and small businesses
3) Long-Haul Networks - Used by service providers to connect countries and cities
4) Submarine Cable Networks - Used to provide reliable high-speed, high-capacity solutions capable of surviving in harsh undersea environments at up to transoceanic distances.
![[Pasted image 20260223141546.png]]
![[Pasted image 20260223141559.png]]
### Fiber vs Copper
Optical-Fiber is primarily used as backbone cabling for high traffic, point-to-point connections between data distribution facilities and for the interconnection of buildings in multi-building campuses.

| Implementation Issues          | UTP Cabling                       | Fiber-Optic Cabling                  |
| ------------------------------ | --------------------------------- | ------------------------------------ |
| Bandwidth supported            | 10 Mb/s - 10 Gb/s                 | 10 Mb/s - 100 Gb/s                   |
| Distance                       | Relatively short (1 - 100 meters) | Relatively long (1 - 100,000 meters) |
| Immunity to EMI and RFI        | Low                               | High (Immune)                        |
| Immunity to electrical hazards | Low                               | High (Immune)                        |
| Media and connector costs      | Lowest                            | Highest                              |
| Installation skills required   | Lowest                            | Highest                              |
| Safety precautions             | Lowest                            | Highest                              |
# Switch Forwarding & Learning
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
# ARP Process 
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
# OSI Layers 

| OSI Model              Layer | Description                                                                                    |
| ---------------------------- | ---------------------------------------------------------------------------------------------- |
| 7 - Application              | Contains protocols used for process-to-process communications.                                 |
| 6 - Presentation             | Provides for common representation of the data transferred between application layer services. |
| 5 - Session                  | Provides services to the presentation layer and to manage data exchange.                       |
| 4 - Transport                | Defines services to segment, transfer, and reassemble the data for individual communications.  |
| 3 - Network                  | Provides services to exchange the individual pieces of data over the network.                  |
| 2 - Data Link                | Describes methods for exchanging data frames over a common media.                              |
| 1 - Physical                 | Describes the means to activate, maintain, and de-activate physical connections.               |
# Switch Access Methods and Technologies 
#  Internet, Intranet and Extranet
### Intranets and Extranets
An intranet is a private collection of LANs and WANs internal to an organization that is meant to be accessible only to the organizations members or others with authorization.

An organization might use an extranet to provide secure access to their network for individuals who work for a different organization that need access to their data on their network.
![[Pasted image 20260310202121.png]]
# 1.3 Internet Connections
### Internet Access Technologies
There are many ways to connect users and organizations to the internet:
- Popular services for home users and small offices include broadband cable, broadband digital subscriber line (DSL), wireless WANs, and mobile services.
- Organizations need faster connections to support IP phones, video conferencing and data center storage.
- Business-class interconnections are usually provided by service providers (SP) and may include: business DSL, leased lines, and Metro Ethernet.
### Home and Small Office Internet Connections

| Connection           | Description                                                                              |
| -------------------- | ---------------------------------------------------------------------------------------- |
| Cable                | high bandwidth, always on, internet<br>offered by cable television service<br>providers. |
| DSL                  | high bandwidth, always on, internet<br>connection that runs over a<br>telephone line.    |
| Cellular             | uses a cell phone network to<br>connect to the internet.                                 |
| Satellite            | major benefit to rural areas without<br>Internet Service Providers.                      |
| Dial-up<br>telephone | an inexpensive, low bandwidth<br>option using a modem.                                   |
![[Pasted image 20260310210638.png]]
### Businesses Internet Connections
Corporate business connections may require:
- higher bandwidth
- dedicated connections
- managed services

| Type of Connection    | Description                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Dedicated Leased Line | These are reserved circuits within the service provider’s network that connect distant offices with private voice and/or data networking. |
| Ethernet WAN          | This extends LAN access technology into the WAN.                                                                                          |
| DSL                   | Business DSL is available in various formats including Symmetric Digital Subscriber Lines (SDSL).                                         |
| Satellite             | This can provide a connection when a wired solution is not available.                                                                     |
![[Pasted image 20260310211033.png]]
### Traditional Separate Networks
- Before converged networks, an organization would have been separately cabled for telephone, video, and data.
- Each of these networks used different technologies to carry the signals.
- Each of these technologies would use a different set of rules and standards.
![[Pasted image 20260310211123.png]]
### The Converging Network
- Converged data networks carry multiple services on one link including:
	- Data
	- Voice
	- Video
- Converged networks can deliver data, voice, and video over the same network infrastructure.
- The network infrastructure uses the same set of rules and standards.

# Ethernet Frame
**Data Encapsulation**
IEEE 802.3 data encapsulation includes the following:
1) Ethernet frame - This is the internal structure of the Ethernet frame.
2) Ethernet Addressing - The Ethernet frame includes both a source and destination MAC address to deliver the Ethernet frame from Ethernet NIC to Ethernet NIC on the same LAN.
3) Ethernet Error detection - The Ethernet frame includes a frame check sequence (FCS) trailer used for error detection.
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

#  Protocol Data Units (PDU)
Encapsulation is the process where protocols add their information to the data.
- At each stage of the process, a PDU has a different name to reflect its new functions.
- There is no universal naming convention for PDUs, in this course, the PDUs are named according to the protocols of the TCP/IP suite.
- PDUs passing down the stack are as follows:
	1) Data (Data Stream)
	2) Segment
	3) Packet
	4) Frame
	5) Bits (Bit Stream)
![[Pasted image 20260313101400.png]]
# Bandwidth Throughput & Goodput 
### Bandwidth
- Bandwidth is the capacity at which a medium can carry data.
- Digital bandwidth measures the amount of data that can flow from one place to another in a given amount of time; how many bits can be transmitted in a second. 
- Physical media properties, current technologies, and the law of physics play a role in determining available bandwidth.
  ![[Pasted image 20260311112605.png]]
#### Latency
- Amount of time, including delays, for data to travel from one given point to another
#### Throughput
- The measure of the transfer of bits across the media over a given period of time
- Usually does not match the specified bandwidth in physical layer implementations due to many factors.
- Amount of traffic, Type of traffic, Latency created by network devices encountered between source and destination
#### Goodput
- The measure of usable data transferred over a given period of time
- Goodput = Throughput- traffic overhead
- traffic overhead for establishing sessions, acknowledgments, and encapsulation.