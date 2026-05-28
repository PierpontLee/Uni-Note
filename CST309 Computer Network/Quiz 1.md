# 1. Why layering?
- **Explicit Structure**: Enables the ==Identification== and ==Relationship== of system piece through a reference model
- **Modularization**: Simplifies ==Maintenance== and ==Updating== the system
- **Transparency**: Change in layer ==Implementation== are ==transparent==, meaning they don't affect the rest of the system.
---

# 2. 5 layer Vs 7 layer?
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
---

# 3. Encapsulation and Decapsulation
## 3.1 Encapsulation (**MS. DUFF-B**)
- **Application Layer:** Creates the raw **Message**.
- **Transport Layer:** Adds a header (Ht​) to create a **Segment**.
- **Network Layer:** Adds a header (Hn​) to create a **Datagram**.
- **Link Layer:** Adds a header (Hl​) to create a **Frame**.
- **Physical Layer:** Converts the Frame into **Bits** (1s and 0s) to send over the wire.
## 3.2 Decapsulation
- **Physical Layer:** Receives bits and passes them up.
- **Link Layer:** Reads and removes the Link header (Hl​).
- **Network Layer:** Reads and removes the Network header (Hn​).
- **Transport Layer:** Reads and removes the Transport header (Ht​).
- **Application Layer:** Finally receives the original **Message**.

---

# 4. Multiplexing
## 4.1 Multiplexing Techniques
- Frequency Division Multiplexing (FDM)
	The frequency spectrum is divided among connections. This is commonly used in broadcast radio and cable TV
- Time Division Multiplexing (TDM)
	Senders take turns transmitting in assigned time slots, typically using a round-robin approach

---

## ~~4.2 Switching Techniques~~
- ~~**Circuit Switching:** Establishes a dedicated physical path between endpoints before data flows (e.g., PSTN). It offers performance equivalent to an isolated path but can waste bandwidth if the line is idle~~
- ~~**Packet Switching:** The basis for the Internet. Data is divided into packets that share the medium. No pre-setup is required, and bandwidth is used dynamically, though it may experience variable queuing delays.~~

| **Item**              | **Circuit Switched** |        Packet Switched |
| :-------------------- | -------------------: | ---------------------: |
| **Dedicated Path**    |                  Yes |                     No |
| **Bandwidth**         |                Fixed |                Dynamic |
| **Store-and-Forward** |                   No |                    Yes |
| **Switch Crash**      |  Fatal to connection | Not necessearily fatal |

---

# 5. 