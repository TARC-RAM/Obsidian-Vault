# 6.1 IPv4 Address Structure
### Network and Host Portions
- An IPv4 address is a 32-bit hierarchical address that is made up of a network portion and a host portion.
- When determining the network portion versus the host portion, you must look at the 32-bit stream.
- All devices on the same network must have the identical network portion.
- A subnet mask is used to determine the network and host portions.
![[Pasted image 20260309131851.png]]
### The Subnet Mask
- The IPv4 address is compared to the subnet mask bit by bit, from left to right.
- A 1 in the subnet mask indicates that the corresponding bit in the IPv4 address is a network bit.
![[Pasted image 20260309131953.png]]
- To identify the network and host portions of an IPv4 address, the subnet mask is compared to the IPv4 address bit for bit, from left to right.
- The actual process used to identify the network and host portions is called ANDing.
![[Pasted image 20260309132047.png]]
### The Prefix Length
- A prefix length is a less cumbersome method used to identify a subnet mask address.
- The prefix length is the number of bits set to 1 in the subnet mask.
- It is written in "slash notation" therefore, count the number of bits in the subnet mask and prepend it with a slash. "/x"

| Subnet Mask     | 32 bit Address                      | Prefix Length |
| --------------- | ----------------------------------- | ------------- |
| 255.0.0.0       | 11111111.00000000.00000000.00000000 | /8            |
| 255.255.0.0     | 11111111.11111111.00000000.00000000 | /16           |
| 255.255.255.0   | 11111111.11111111.11111111.00000000 | /24           |
| 255.255.255.128 | 11111111.11111111.11111111.10000000 | /25           |
| 255.255.255.192 | 11111111.11111111.11111111.11000000 | /26           |
| 255.255.255.224 | 11111111.11111111.11111111.11100000 | /27           |
| 255.255.255.240 | 11111111.11111111.11111111.11110000 | /28           |
| 255.255.255.248 | 11111111.11111111.11111111.11111000 | /29           |
| 255.255.255.252 | 11111111.11111111.11111111.11111100 | /30           |
### Determining the Network: Logical AND
- A logical AND Boolean operation is used in determining the network address.
- Logical AND is the comparison of two bits where only a 1 AND 1 produces a 1 and any other combination produces a 0.
- To identify the network address, the host IPv4 address is logically ANDed, bit by bit, with the subnet mask to identify the network address
![[Pasted image 20260309133432.png]]
### Network, Host and Broadcast Addresses
- Within each network are three types of IP addresses:
- Network Address
- Host Address
- Broadcast Address
![[Pasted image 20260309133518.png]]
![[Pasted image 20260309133530.png]]
- Three IPv4 addresses must be configured on a host
	- Unique IPv4 address of the host.
	- Subnet mask - identifies the network/host portion of the IPv4 Address.
	- Default gateway - IP address of the local router interface
	  ![[Pasted image 20260309133640.png]]
# 6.2 IPv4 Unicast, Broadcast and Multicast
### Static IPv4 Address Assignment to a host
- Some devices like printers, servers and network devices require a fixed IP address.
- Hosts in a small network can also be configured with static addresses.
  ![[Pasted image 20260309135021.png]]
### Dynamic IPv4 Address Assigment to a Host
- Most networks use Dynamic Host Configuration Protocol (DHCP) to assign IPv4 addresses dynamically.
- The DHCP server provides an IPv4 address, subnet mask, default gateway, and other configuration information.
- DHCP leases the addresses to hosts for a certain length of time.
- If the host is powered down or taken off the network, the address is returned to the pool for reuse.
  ![[Pasted image 20260309135403.png]]
### Unicast
- Unicast transmission is sending a packet to one destination IP address.
- For example, the PC at 172.16.4.1 sends a unicast packet to the printer at 172.16.4.253
  ![[Pasted image 20260309135553.png]]
### Broadcast
- Broadcast transmission is sending a packet to all other destination IP addresses
- For example, the PC at 172.16.4.1 sends a broadcast packet to all IPv4 hosts
  ![[Pasted image 20260309135640.png]]
### Multicast
- Multicast transmission is sending a packet to a multicast address group.
- For example, the PC at 172.16.4.1 sends a multicast packet to the multicast group address 224.10.10.5
# 6.3 Types of IPv4 Addresses
### Public and Private IPv4 Addresses
- As defined in RFC 1918, public IPv4 addresses are globally routed between internet service provider (ISP) routers.
- Private addresses are common blocks of addresses used by most organizations to assign IPv4 addresses to internal hosts.
- Private IPv4 addresses are not unique and can be used internally within any network.
- However, private addresses are not globally routable.
### Routing to the Internet
- Network Address Translation (NAT) translates private IPv4 addresses to public IPv4 addresses.
- NAT is typically enabled on the edge router connecting to the internet.
- It translates the internal private address to a public global IP address.
### Special Use IPv4 Addresses
#### Loopback addresses
- 127.0.0.0 /8 (127.0.0.1 to 127.255.255.254)
- Commonly identified as only 127.0.0.1
- Used on a host to test if TCP/IP is operational
#### Link-Local Addresses
- 192.254.0.0 /16 (169.254.0.1 to 169.254.255.254)
- Commonly known as Automatic Private IP Addresssing (APIPA) addresses or self-assigned addresses
- Used by Windows DHCP clients to self-configure when no DHCP servers are available
### Legacy Classful Addressing
RFC 790 (1981) allocated IPv4 addresses in classes
- Class A (0.0.0.0/8 - 127.0.0/8)
- Class B (128.0.0.0/16 - 191.255.0.0/16)
- Class C (192.0.0.0/24 - 223.255.255.0/24)
- Class D (224.0.0.0 to 239.0.0.0)
- Class E (240.0.0.0 - 255.0.0.0)
### Legacy Classful Addressing
![[Pasted image 20260309144147.png]]
- In 1981, Internet IPv4 addresses were assigned using classful addressing (RFC 790)
- Network addresses were based on 3 classes:
	- Class A (0.0.0.0/8 - 127.0.0.0/8) - Designed to support extremely large networks with more than 16 million host addresses.
	  ![[Pasted image 20260309144330.png]]
- Class B (128.0.0.0 /16 - 191.255.0.0/16) - Designed to support the needs of moderate to large size networks up to approximately 65,000 host addresses.
  ![[Pasted image 20260309171340.png]]
- Class C (192.0.0.0 /24 - 223.255.255.0 /24) - Designed to support small networks with a maximum of 254 hosts
  ![[Pasted image 20260309171439.png]]
#### Assignment of IP Addresses
- The Internet Assigned Numbers Authority (ANA) manages and allocates blocks of IPv4 and IPv6 addresses to five Regional Internet Registries (RIRs)
- RIRs are responsible for allocating IP addresses to ISPs who provide IPv4 address blocks to smaller ISPs and organizations