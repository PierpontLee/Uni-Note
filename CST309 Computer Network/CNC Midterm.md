
# Chapter 1
## 1.1 What is a protocol?
## 1.2. Why layering?
- **Explicit Structure**: Enables the ==Identification== and ==Relationship== of system piece through a reference model
- **Modularization**: Simplifies ==Maintenance== and ==Updating== the system
- **Transparency**: Change in layer ==Implementation== are ==transparent==, meaning they don't affect the rest of the system.
## 1.3 Encapsulation & Decapsulation
Encapsulation (**==MS. DUFF-B==**)
- **Application Layer:** Creates the raw **Message**.
- **Transport Layer:** Adds a header (Ht​) to create a **Segment**.
- **Network Layer:** Adds a header (Hn​) to create a **Datagram**.
- **Link Layer:** Adds a header (Hl​) to create a **Frame**.
- **Physical Layer:** Converts the Frame into **Bits** (1s and 0s) to send over the wire.
Decapsulation: reverse

# 1.4 5 Layer & 7 Layer
**The 5-Layer Internet Stack (Top to Bottom)**

> **A**ll **T**igers **N**eed **L**ittle **P**ats
- **A**pplication
- **T**ransport
- **N**etwork
- **L**ink
- **P**hysical

**The 7-Layer OSI Model (Bottom to Top)**

> **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

- **P**hysical
- **D**ata Link
- **N**etwork
- **T**ransport
- **S**ession
- **P**resentation
- **A**pplication

## 1.5 Packet/circuit switching
- **Circuit Switching:** Establishes a dedicated physical path between endpoints before data flows (e.g., PSTN). It offers ==performance equivalent to an isolated path but can waste bandwidth if the line is idle.==
- **Packet Switching:** The basis for the Internet. Data is divided into packets that share the medium. ==No pre-setup is required, and bandwidth is used dynamically==, though it may experience variable queuing delays.
## 1.6 Network Performance calculation: loss, delay, throughput

# Chapter 2 (SAID MS LEE SUI PING NO NEED🙏)
##  2.1 Simplex, half-duplex, full-duplex transmissions
- Simplex: ==single direction== transfer data
- Full-duplex: ==two directions simultaneously==
- Half-duplex each direction, but cannot proceed simultaneously (==walkie-talkies==)
## 2.2 Signal propagation
LOS (line-of-sight):
	Signal travels in straight line directly from transmitter to receiver
When obstacles:
- Pass
- Absorbed
- Three phenomena:
	- Reflection
	- Diffraction
	- Scattering

Multipath signals:
- Caused by reflection, diffraction, scattering
- Advantage
	- Better chance of reaching destination
- Disadvantage
	- Signal delay will result in data errors

# Chapter 3
## 3.1 Link layer addressing
Host and router = ==Nodes==
Path = ==links==
Layer 2 protocol data unit = ==Frame==
Two Sublayers =
	- Logical Link Control (LLC)
		- multiplexing and demultiplexing
	- Media Access Control (MAC)
		- Access to shared media
Services:
- Framing: encapsulate datagram into frame, adding ==Header==, and ==Trailer==
- Link Access: MAC used in frame ==header== to identify ==source==
- Reliable delivery between adjacent nodes: Rarely used on low bit-error link, ==wireless== links: ==high error rates==
- Error Detection:
	- errors caused by ==noise==
	- receiver detects error, signals sender for ==retransmission== or ==drops== frame
- Error Correction: 
	- Receiver identifies and corrects bit error(s) 

Example of datalink protocol:
- LAN
	- Ethernet 
	- Wireless LAN
- WAN
	- Point-to-Point Protocol (PPP)
	- High-Level Data Link Control (HDLC)
	- Frame Relay

Link Layer implemented on:
- every host
- ==Adaptor== or Network Interface Card (NIC)
## 3.2 Ethernet, ARP, VLAN, switch
### 3.2.1 LAN Addresses
- Each adapter on LAN has ==unique MAC== address
- Each frame specifies a destination MAC
### 3.2.2 MAC VS IP
32-bit IP :
- Network layer address
- used to get packet to destination IP
48-bit MAC:
- Burned in NIC ROM (sometimes software setables)
- **used to get ==frame== from one interface to another ==physically-connected interface in same subnet==**
Divided into subfields:
- 3-byte ==Organizationally Unique ID== (OUI)
	- manufacturer buys portion of MAC address space (to assure uniqueness.
- 3-byte ==Network Interface Controller== (NIC)

MAC Address Type:
- Unicast
- Broadcast
- Multicast

### 3.2.3 ARP
ARP: Address Resolution Protocol
- Each node (host, router) on LAN has ==ARP table== (IP and MAC address mapping)
- TTL (==Time To Live==): time after which address mapping will be forgotten (typically ==20 min==)

Protocol:
![[Pasted image 20260604135436.png]]
### 3.2.4 Ethernet
IEEE 802.3
Simpler, cheap
Kept up with speed race: 10 Mbps – 10 Gbps
Physical
![[Pasted image 20260604151341.png]]
- Bus: can collide with each
- Star: active switch in middle, 
![[Pasted image 20260604154807.png]]
Preamble and Start Frame Delimiter (SFD) (8 bytes)
- 7 bytes preamble with pattern 10101010
- one byte SFD with pattern 10101011
Structure:
- Destination Address (6 bytes)
- Source Address (6 bytes)
	- ==host copy the frame if destination address match==
- otherwise adapter discards frame
- ==Promiscuous mode== allows a host to receive all frames regardless of address (Wireshark)
Type (2 bytes)
- Higher layer protocol
Frame Check Sequence (FCS) (4 bytes)
- Cyclic redundancy check (CRC)

Switch:
- link-layer device
	- Store, forward Ethernet frames
	- Frame’s MAC address
![[Pasted image 20260604161414.png]]
==Frame Forwarding==: 
	When frame received at switch:
		1. record incoming link (interface), MAC address of sending host
		2. index switch table using MAC destination address
		3. if entry found for destination
			then {
				if destination on segment from which frame arrived
					then ==drop== frame
				else ==forward== frame on interface indicated by entry
			}
			else ==flood== forward on all interfaces except arriving interface

### 3.2.4 Switches vs. Routers
routers: network-layer
switches: link-layer


### 3.2.5 VLAN
switch(es) supporting VLAN capabilities can be configured to define ==multiple virtual LANS== over ==single physical LAN== infrastructure.

Port-based VLAN
- ==traffic isolation==
- ==dynamic membership==
- ==forwarding== between VLANS

Spanning Multiple Switches
![[Pasted image 20260604164004.png]]
- ==trunk port==: carries ==frames between VLANs== defined over ==multiple physical switches==
- frames must carry ==VLAN ID==
- ==802.1q protocol adds/removed additional header== 

==Access== Ports (The Endpoints): **exactly one VLAN**, handle **==untagged== frames**
==Trunk== Ports (The Highway): **multiple VLANs**, handle ==tagged== frames

![[Pasted image 20260604164413.png]]

### 3.2.6 Multiple Access Protocols
Determine ==when node can transmit==. Without Multiple Access Protocol, if node receives two or more signals at the same time it will do ==collision==

Ideal Multiple Access Protocol:
	Example: Given: broadcast channel of rate R bps
	• Desired characteristics:
	1. when one node wants to transmit, it can send at rate R.
	2. when M nodes want to transmit, each can send at average rate R/M
	3. fully decentralized:
	• no special node to coordinate transmissions
	• no synchronization of clocks, slots
	4. simple

Three classes:
- channel partitioning
	- ==divide channel== into smaller “pieces”
- random access
	- channel ==not divided, allow collisions, “recover” from collisions==
- “taking turns”
	- nodes ==take turns==, but nodes with more to send can take longer turns

TDMA: Time Division Multiple Access
FDMA: Frequency Division Multiple Access

## 3.2.7 Random Access Protocols
- how to detect collisions
- how to recover from collisions 
![[Pasted image 20260604173404.png]]
- Pure ALOHA: used in Hawaii, no sync, frame first arrives transmit immediately
## 3.3 CSMA/CD Vs CSMA/CA
### 3.3.1 CSMA (Carrier Sense Multiple Access):
- Listen before transmit
- If ==idle => transmit==
- If ==busy => defer== then ==retransmit== after ==random interval==
- Can still collide 
	- CSMA/CD (Collide Detection)
		- Easy in wired LAN
		- Difficult in wireless LAN
		- Algorithm:
			- NIC Create frame
			- NIC senses idle > transfer, busy > wait until idle
			- if NIC transmit without detecting another transmission, done
			- if NIC detect another transmission while transmit, abort and sends jam signal
"Taking turns" MAC Protocol:
- channel partitioning MAC protocols
	- inefficient at low load
- random access MAC protocols
	- high load: collision overhead
- “taking turns” protocols
	- master node “invites” slave nodes to transmit in turn
	- Token passing:
		- control token passed from one node to next sequentially

## 3.4 Passive & Active Scanning
![[Pasted image 20260604231524.png]]
## 3.5 Frame addressing
==REMEMBER THE TABLE==
![[Pasted image 20260604231604.png]]
Example:
![[Pasted image 20260604231615.png]]