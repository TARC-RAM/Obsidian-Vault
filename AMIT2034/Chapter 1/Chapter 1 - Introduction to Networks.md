# 1.1 Network Components and Topologies
## 1.1.1 Network Components
### Host Roles
Every computer on a network is called a host or end device. Servers are computers that provide
information to end devices:
- Email servers
- Web servers
- File servers
Clients are computers that send
requests to the servers to retrieve
information:
- web page from a web server
- email from an email server
![[Pasted image 20260310200550.png]]

| Server Type | Description                                                                                |
| ----------- | ------------------------------------------------------------------------------------------ |
| Email       | Email server runs email server software.<br>Clients use client software to access email.   |
| Web         | Web server runs web server software.<br>Clients use browser software to access web pages.  |
| File        | File server stores corporate and user files.<br>The client devices access these files.<br> |
### Peer-to-Peer
It is possible to have a device be a client and a server in a Peer-to-Peer Network. This type of network design is only recommended for very small networks.
![[Pasted image 20260310200720.png]]

| Advantages                                                     | Disadvantages                                                                  |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Easy to set up                                                 | No centralized administration                                                  |
| Less complex                                                   | Not as secure                                                                  |
| Lower cost                                                     | Not scalable                                                                   |
| Used for simple tasks: transferring files and sharing printers | All devices may act as both clients & servers which can slow their performance |
### End Devices
An end device is where a message originates from or where it is received. Data originates with an end device, flows through the network, and arrives at an end device.
![[Pasted image 20260310200855.png]]
### Intermediary Network Devices
An intermediary device interconnects end devices. Examples include switches, wireless access points, routers, and firewalls.
Management of data as it flows through a network is also the role of an intermediary device, including:
- Regenerate and retransmit data signals.
- Maintain information about what pathways exist in the network.
- Notify other devices of errors and communication failures.
  ![[Pasted image 20260310200949.png]]
### Network Media
Communication across a network is carried through a medium which allows a message to travel from source to destination.

| Media Types                                                | Description                                                       |
| ---------------------------------------------------------- | ----------------------------------------------------------------- |
| Metal wires within<br>cables                               | Uses electrical impulses                                          |
| Glass or plastic fibers within cables (fiber- optic cable) | Uses pulses of light.                                             |
| Wireless transmission                                      | Uses modulation of specific frequencies of electromagnetic waves. |
## 1.1.2 Network Representations and Topologies
### Network Representations
Network diagrams, often called topology diagrams, use symbols to represent devices within the network.
Important terms to know include:
- Network Interface Card (NIC) - A NIC, or LAN adapter, provides the physical connection to the network at the PC or other end device. The media connecting the PC to the networking device plugs directly into the NIC.
- Physical Port - A connector or outlet on a networking device where the media is connected to a host or other networking device.
- Interface - Specialized ports on an internetworking device that connect to individual networks. Because routers are used to interconnect networks, the ports on a router are referred to network interfaces.
### Topology Diagrams
**Physical topology diagrams** illustrate the physical location of intermediary devices and cable installation.
![[Pasted image 20260310201422.png]]

**Logical topology diagrams** illustrate devices, ports, and the addressing scheme of the network.
![[Pasted image 20260310201505.png]]
# 1.2 Common Types of Networks
### Networks of Many Sizes
- Small Home Networks – connect a few computers to each other and the Internet
- Small Office/Home Office – enables computer within a home or remote office to connect to a corporate network
- Medium to Large Networks – many locations with hundreds or thousands of interconnected computers
- World Wide Networks – connects hundreds of millions of computers world-wide – such as the internet
  ![[Pasted image 20260310201629.png]]
### LANs and WANs
Network infrastructures vary greatly in terms
of:
- Size of the area covered
- Number of users connected
- Number and types of services available
- Area of responsibility
Two most common types of networks:
- Local Area Network (LAN)
- Wide Area Network (WAN).
  ![[Pasted image 20260310201734.png]]
A LAN is a network infrastructure that spans a small geographical area.
![[Pasted image 20260310201758.png]]

A WAN is a network infrastructure that
spans a wide geographical area.
![[Pasted image 20260310201810.png]]

| LAN                                                  | WAN                                                      |
| ---------------------------------------------------- | -------------------------------------------------------- |
| Interconnect end devices in a limited area.          | Interconnect LANs over wide geographical areas.          |
| Administered by a single organization or individual. | Typically administered by one or more service providers. |
| Provide high-speed bandwidth to internal devices.    | Typically provide slower speed links between LANs.       |
### The Internet
The internet is a worldwide collection of
interconnected LANs and WANs.
- LANs are connected to each other using WANs.
- WANs may use copper wires, fiber optic cables, and wireless transmissions.
The internet is not owned by any individual or group. The following groups were developed to help maintain structure on the internet:
- IETF
- ICANN
- IAB
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
# 1.4 Reliable Networks
### Network Architecture
Network Architecture refers to the technologies that support the infrastructure that moves data across the network.
There are four basic characteristics that the underlying architectures need to address to meet user expectations:
- Fault Tolerance
- Scalability
- Quality of Service (QoS)
- Quality of Service (QoS)
![[Pasted image 20260310211417.png]]
### Fault Tolerance
A fault tolerant network limits the impact of a failure by limiting the number of affected devices. Multiple paths are required for fault tolerance.
Reliable networks provide redundancy by implementing a packet switched network: 
- Packet switching splits traffic into packets that are routed over a network.
- Each packet could theoretically take a different path to the destination.
This is not possible with circuit-switched networks which establish dedicated circuits.
![[Pasted image 20260310211613.png]]
### Scalability
A scalable network can expand quickly and easily to support new users and applications without impacting the performance of services to existing users.
Network designers follow accepted standards and protocols in order to make the networks scalable.
![[Pasted image 20260310211654.png]]
### Quality of Service
Voice and live video transmissions require higher expectations for those services being delivered.

Have you ever watched a live video with constant breaks and pauses? This is caused when there is a higher demand for bandwidth than available – and QoS isn’t configured.
- Quality of Service (QoS) is the primary mechanism used to ensure reliable delivery of content for all users.
- With a QoS policy in place, the router can more easily manage the flow of data and voice traffic.
![[Pasted image 20260310211930.png]]
### Network Security
There are two main types of network security that must be addressed:
- Network infrastructure security
	- Physical security of network devices
	- Preventing unauthorized access to the devices
- Information Security
	- Protection of the information or data transmitted over the network
Three goals of network security:
- Confidentiality – only intended recipients can read the data
- Integrity – assurance that the data has not be altered with during transmission
- Availability – assurance of timely and reliable access to data for authorized users
# 1.5 Networks Treads
### New Trends
- The role of the network must adjust and continually transform in order to be able to keep up with new technologies and end user devices as they constantly come to the market.
- Several new networking trends that effect organizations and consumers:
	- Bring Your Own Device (BYOD)
	- Online collaboration
	- Video communications
	- Cloud computing
### Bring Your Own Device
Bring Your Own Device (BYOD) allows users to use their own devices giving them more opportunities and greater flexibility.

BYOD allows end users to have the freedom to use personal tools to access information and communicate using their:
- Laptops
- Netbooks
- Tablets
- Smartphones
- E-readers
BYOD means any device, with any ownership, used anywhere.
### Online Collaboration
- Collaborate and work with others over the network on joint projects.
- Collaboration tools including Cisco WebEx (shown in the figure) gives users a way to instantly connect and interact.
- Collaboration is a very high priority for businesses and in education.
- Cisco Webex Teams is a multifunctional collaboration tool.
	- send instant messages
	- post images
	- post videos and links
### Video Communication
- Video calls are made to anyone, regardless of where they are located.
- Video conferencing is a powerful tool for communicating with others.
- Video is becoming a critical requirement for effective collaboration.
- Cisco TelePresence powers is one way of working where everyone, everywhere.
### Cloud Computing
Cloud computing allows us to store personal files or backup our data on servers over the internet.
- Applications can also be accessed using the Cloud.
- Allows businesses to deliver to any device anywhere in the world.
Cloud computing is made possible by data centers.
- Smaller companies that can’t afford their own data centers, lease server and storage services from larger data center organizations in the Cloud.
Four types of Clouds:
- Public Clouds
	- Available to the general public through a pay per-use model or for free.
- Private Clouds
	- Intended for a specific organization or entity such as the government.
- Hybrid Clouds
	- Made up of two or more Cloud types – for example, part custom and part public.
	- Each part remains a distinctive object but both are connected using the same architecture.
- Custom Clouds
	- Built to meet the needs of a specific industry, such as healthcare or media.
	- Can be private or public.
### Technology Trends in the Home
- Smart home technology is a growing trend that allows technology to be integrated into every-day appliances which allows them to interconnect with other devices.
- Ovens might know what time to cook a meal for you by communicating with your calendar on what time you are scheduled to be home.
- Smart home technology is currently being developed for all rooms within a house.
### Powerline Networking
- Powerline networking can allow devices to connect to a LAN where data network cables or wireless communications are not a viable option.
- Using a standard powerline adapter, devices can connect to the LAN wherever there is an electrical
- Powerline networking is especially useful when wireless access points cannot reach all the devices in the home.
### Wireless Broadband
In addition to DSL and cable, wireless is another option used to connect homes and small businesses to the internet.
- More commonly found in rural environments, a Wireless Internet Service Provider (WISP) is an ISP that connects subscribers to designated access points or hotspots.
- Wireless broadband is another solution for the home and small businesses.
	- Uses the same cellular technology used by a smart phone.
	- An antenna is installed outside the house providing wireless or wired connectivity for devices in the home.
# 1.6 Issues of Network Management
- Network administrator and engineer need to be aware of several common issues related to network management to effectively maintain and troubleshoot networks. Here are some of the key issues:
1) Network Performance
	1) Bandwidth Congestion: Overutilization of network bandwidth can lead to slow performance.
	2) High Latency: Delays in data transmission can affect the performance of real-time applications.
	3) Packet Loss: Data packets not reaching their destination can cause disruptions and data corruption.
	4) Jitter: Variability in packet arrival times can affect voice and video quality.
2) Network Security
	1) Unauthorized Access: Protecting the network from unauthorized users.
	2) Malware and Viruses: Protecting the network from malicious software.
	3) Data Breaches: Preventing unauthorized access to sensitive data.
	4) Denial of Service (DoS) Attacks: Ensuring the network is resilient against DoS attacks.
3) Network Reliability
	1) Hardware Failures: Handling failures of network hardware components like routers, switches, and cables.
	2) Redundancy and Failover: Implementing redundant systems to ensure continuous operation.
	3) Network Downtime: Minimizing and managing planned and unplanned network outages.
4) Configuration Management
	1) Configuration Errors: Ensuring network devices are correctly configured to avoid misconfigurations that can cause issues.
	2) Documentation: Keeping accurate records of network configurations, changes, and updates.
	3) Change Management: Carefully planning and documenting changes to the network to prevent disruptions.
5) Network Scalability
	1) Capacity Planning: Planning for future growth to ensure the network can handle increased load.
	2) Upgrading Infrastructure: Updating hardware and software to support new demands and technologies.
	3) Load Balancing: Distributing network traffic efficiently to avoid overloading any single component.