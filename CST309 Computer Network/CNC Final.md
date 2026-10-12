# Chapter 1 & 2
## 1.1 What is a protocol?
Protocols define the format, order of messages sent and received among network
entities, and actions taken on message transmission receipt
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
## 1.6 Multiplexing (Frequency vs Time)
1. FDM:
	- Optical electromagnetic divide into frequency band
	- Each call allocate its own band, can transmit at max rate of the narrow band
	- Used in broadcast radio and cable tv
2. TDM:
	- time divided into slots
	- Each call allocated periodic slot at maximum rate of frequency band during its time slot
	- Sender take turns transmitting
## 1.7 Simplex vs Full Duplex vs Half Duplex
1. ==Simplex==: Only 1 direction data transfer, broadcast radio or tv
2. ==Full== duplex: Transmission in two direction continuously,. Example: phone call
3. ==Half== duplex: Walkie talkie. (==one direction at the time==)

# Chapter 3
## 3.1 IP VS MAC
a. 32 bit = IP
Network layer address and used to get packet to destination IP subnet
b. MAC = portability, IP hierarchical not portable
c. MAC = 48 bit
-burned in NIC ROM
-Used to get frame from one interface to another physically-connected
interface in same subnet
## 3.2 ARP: Address Resolution Protocol
![[Pasted image 20260718183718.png]]
- A wanted to send to B but didn't know the address(not in the table). So A broadcasted, and wait for B to unicast back to A.
- ARP is plug n play, they make their own table
## 3.3 Addressing: routing to another LAN
- A wanted to Datagram to B
	- Only know:
		- IP of B
		- IP and MAC of R
- Create IP source A, IP source B and send link layer of R address
- R create a link layer of B and know MAC address of B

## 3.4 Switches vs Routers
- Both store then send
- Bedanya ==Routers = network== layer, ==switches = link== layer
- Routers: compute tables using ==routing algorithm==, IP address
- Switches: Learn table forward uses ==flooding==, MAC address

## 3.5 LAN vs VLAN
![[Pasted image 20260718203226.png]]
## 3.6 Random Access Protocol : CSMA, CSMA/CD CSMA/CA
1. CSMA:
	- listen before transmit
	- Collision terjadi ketika dua node gabisa dengar jdi asal send
2. CSMA CD (Collision Detection):
	- NIC terima datagram
	- NIC sense channel idle lgsg kirim, kalau sibuk tunggu idle bru kirim
	- NIC kirim frame tanpa sense transmission lain
	- Jika nabrak langsung abort dan kirim jam signal
- After abort, binary exponential backoff yaitu tunggu mth collision baru nanti balik lgi ke step 2
3. CSMA CA (collision avoidance):
	- Intinya sebelum kirim sender kirim (request to send) RTS yang kecil banget buat testing lah
	- Setelah di reply dengan call to send (CTS) baru dikirim
	- Nnti ad gambar
## 3.7 802.11 frame : ADDRESSING
