# 3.0 Purpose of the Physical Layer
### The Physical Connection
- Before any network communications can occur, a physical connection to a local network must be established.
- This connection would be wired or wireless, depending on the setup of the network.
- This generally applies whether you are considering a corporate office or a home.
- A Network Interface Card (NIC) connects a device to the network.
- Some devices may have just one NIC, while others may have multiple NICs (Wired and/or Wireless, for example).
- Not all physical connections offer the same level of performance.
![[Pasted image 20260304110113.png]]

- Transports bits across the network media
- Accepts a complete frame from the Data Link Layer and encodes it as a series of signals that are transmitted to the local media
- This is the last step in the encapsulation process
- The next device in the path to the destination receives the bits and re-encapsulates the frame, then decides what to do with it.
# 3.1 Physical Layer Characteristics
### Physical Layer Standards
- International Organization for Standardization (ISO)
- Telecommunications Industry Association/Electronic Industries Association (TIA/EIA)
- International Telecommunication Union (ITU)
- American National Standards Institute (ANSI)
- Institute of Electrical and Electronics Engineers (IEEE)
### Physical Components
Physical Layer standards address three functional areas:
- Physical Components
- Encoding
- Signaling
The Physical Components are the hardware devices, media, and other connectors that transmit the signals that represent the bits.
- Hardware components like NICs, interfaces and connectors, cable materials, and cable designs are all specified in standards associated with the physical layer.
### Encoding
- Encoding converts the stream of bits into a format recognizable by the next device in the network path.
- This 'coding' provides predictable patterns that can be recognized by the next device.
- Examples of encoding methods include Manchester (shown in the figure), 4B/5B, and 8B/10B.
![[Pasted image 20260304110952.png]]
### Signaling 
- The signaling method is how the bit values, "1" and "0" are represented on the physical medium.
- The method of signaling will vary based on the type of medium being used.
![[Pasted image 20260304111115.png]]
![[Pasted image 20260304111130.png]]
![[Pasted image 20260304111145.png]]
### Bandwidth
- Bandwidth is the capacity at which a medium can carry data.
- Digital bandwidth measures the amount of data that can flow from one place to another in a given amount of time; how many bits can be transmitted in a second. 
- Physical media properties, current technologies, and the law of physics play a role in determining available bandwidth.

# 3.2 Network Media
## 3.2.1 Copper Cabling
Characteristics
- Copper cabling is the most common type of cabling used in networks today. It is inexpensive, easy to install, and has low resistance to electrical current flow.
- Limitations:
	- Attenuation - The longer the electrical signals have to travel, the weaker they get.
	- The electrical signal is susceptible to interference from two sources, which can distort and corrupt the data signals. (Electromagnetic Interference (EMI) and Radio Frequency Interference (RFI) and Crosstalk)
- Mitigation:
	- Strict adherence to cable length limits will mitigate attenuation.
	- Some kinds of copper cable mitigate EMI and RFI by using metallic shielding and grounding.
	- Some kinds of copper cable mitigate crosstalk by twisting opposing circuit pair wires together.
![[Pasted image 20260223131644.png]]
## Types of Copper Cabling
- Unshielded Twister-Pair (UTP) Cable
- Shielded Twister-Pair (STP) Cable
- Coaxial Cable
![[Pasted image 20260223131929.png]]
![[Pasted image 20260223131945.png]]
![[Pasted image 20260223131959.png]]
## 3.2.2 UTP Cabling
### Properties 
- UTP has four pairs of color-coded wires twisted together and encased in a flexible plastic sheath. No shielding is used. UTP relies on following properties to limit crosstalk:
	- Cancellation - Each wire in a pair of wires uses opposite polarity. One wire is negative, the other wire is positive. They are twisted together and the magnetic fields effectively cancel each other and outside EMI/RFI.
	- Variation in twists per foot in each wire - Each wire is twisted a different amount, which helps prevent crosstalk amongst the wires in cable.
### UTP Cabling Standards and Connectors
Standards for UTP are established by the TIA/EIA. TIA/EIA-568 standardizes elements like: 
- Cable Types
- Cable Lengths
- Cable Termination
- Testing Methods
Electrical standards for copper testing are established by the IEEE, which rates cable according to its performance.
Examples:
- Category 3
- Category 5 and 5e
- Category 6
![[Pasted image 20260223133304.png]]
![[Pasted image 20260223133331.png]]
## Straight-through and Crossover UTP Cables
![[Pasted image 20260223133509.png]]

| Cable Type                | Standard                       | Application                                                         |
| :------------------------ | :----------------------------- | :------------------------------------------------------------------ |
| Ethernet Straight-through | Both ends T568A or T568B       | Host to Network Device                                              |
| Ethernet Crossover        | One end T568A, other end T568B | Host-to-Host, Switch-to Switch, Router-to-Router                    |
| Rollover                  | Cisco Proprietary              | Host serial port to Router or Switch Console Port, using an adapter |
## 3.2.3 Fiber-Optic Cabling
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
## 3.2.4 Wireless Media
### Properties of Wireless Media
It carries electromagnetic signals representing binary digits using radio or microwave frequencies. This provides the greatest mobility option. Wireless connection numbers continue to increase.

| Limitations   | Explanation                                                                                                                                                                            |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Coverage area | Effective coverage can be significantly impacted by the physical characteristics of the deployment location.                                                                           |
| Interference  | Wireless is susceptible to interference and can be disrupted by many common devices                                                                                                    |
| Security      | Wireless communication coverage requires no access to physical strand of media, so anyone can gain access to the transmission                                                          |
| Shared medium | WLANs operate in half-duplex, which means only one can devices can send or receive at a time. Many users accessing the WLAN simultaneously results in reduced bandwidth for each user. |
### Types of Wireless Media
The IEEE and telecommunications industry standards for wireless data communications cover both the data link and physical layers. In each of these standards, physical layer specifications dictate:
- Data to radio signal encoding methods
- Frequency and power of transmission
- Signal reception and decoding requirements
- Antenna design and construction

#### Wireless Standards:
- Wi-Fi (IEEE 802.11) - Wireless LAN (WLAN) technology)
- Bluetooth (IEEE 802.15) Wireless Personal Area network (WPAN) standard
- WiMAX (IEEE 802.16) - Uses a point-to-multipoint topology to provide broadband wireless access
- Zigbee (IEEE 802.15.4) - Low data-rate, low power-consumption communications, primarily for internet of Things (IoT) applications
