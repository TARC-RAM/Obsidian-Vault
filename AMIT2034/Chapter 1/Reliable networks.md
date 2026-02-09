# Network Architecture
Network Architecture refers to the technologies that support the infrastructure that moves data across the network.

There are four basic characteristics that the underlying architectures need to address to meet user expectations:
- Fault Tolerance
- Scalability
- Quality of Service (QoS)
- Security
## Fault Tolerance
A fault tolerant network limits the impact of a failure by limiting the number of affected devices. Multiple paths are required for fault tolerance.
Reliable networks provide redundancy by implementing a packet switched network:
- Packet switching splits traffic into packets that are routed over a network
- Each packet could theoretically take a different path to the destination.
This is not possible with circuit-switched networks which establish dedicated circuits.
![[Pasted image 20260209194852.png]]
## Scalability
A scalable network can expand quickly and easily to support new users and applications without impacting the performance of services to existing users.
Network designers follow accepted standards and protocols in order to make the networks scalable.
![[Pasted image 20260209195150.png]]
## Quality of Service
Voice and live video transmissions require higher expectations for those services being delivered.
Have you ever watched a live video with constant breaks and pauses? This is caused when there is a higher demand for bandwidth than available - and QoS isn't configured.
- QoS is the primary mechanism used to ensure reliable delivery of content for all users.
- With a QoS policy in place, the router can more easily manage the flow of data and voice traffic.
![[Pasted image 20260209195406.png]]
## Network Security
There are two main types of network security that must be addressed:
- Network infrastructure security
	- Physical security of network devices
	- Preventing unauthorized access to the devices
- Information Security
	- Protection of the information or data transmitted over the netowork
Three goals of network security:
1) Confidentiality - Only intended recipients can read the data
2) Integrity - Assurance that the data has not been altered with during transmission
3) Availability - Assurance of timely and reliable access to data for authorized users