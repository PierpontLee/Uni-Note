# C. Thermal-Aware CPU/GPU Design: Navigating Physical Limits and Thermal Throttling in HPC
The demands for computational process of Artificial Intelligence (AI) and High Performance Computing (HPC) has drove semiconductor scaling to its physical maximum. As data centers grows to accommodate LLM or large language models and neural network training, the primary limitation is not just density of transistors, but also its ability to dispel heat. At microarchitectural level, reducing power usage and controlling thermal release are essential for keeping the equipment working well meanwhile avoiding serious hardware failure.

## C.1 The Breakdown of Dennard Scaling and the "Dark Silicon" Problem
Historically, microprocessor development was constrained by Dennard Scaling, which stated that as transistor shrank, their power density would remain constant, granting a higher clock speeds without an increase in power draw. The breakdown of this scaling in the mid-2000s fundamentally shift to multicore part in CPU and GPU design. While transistor sizes still following to shrink according to Moore's Law, operating voltages was unable to be scaled down as forcefully due to leakage in electrical currents.

The total power consumption of a processor is calculated by three major sources of power dissipation: switching, short-circuit, and leakage currents, Expressed fundamentally by Chandrakasan, Sheng, and Brodersen (1992) as:
$$P_{total}=p_t(C_L \times V\times V_{dd} \times F_{fclk} )\:+\: I_{sc}\times V_{dd}\:+I_{leakage}\;\times V_{dd}$$
Where $p_t$ is the probability of power-consuming transition, $C_L$ is the loading capacitance, $f_{clk}$​ is the clock frequency, $V_{dd}$​ is the supply voltage, V is the voltage swing (which typically equals $V_{dd}$​), $I_{sc​}$ is the short-circuit current, and $I_{leakage}$​ is the leakage current.

While $V_{dd}$ scaling has stalled due to underlying physics, the dynamic switching cannot be offseted by dropping the voltage. As a result, the power density (watts per square millimeter) skyrocketed in modern AI accelerators.

This thermal density crisis created the "Dark Silicon" phenomenon. Dark silicon meaning that the fraction of chip circuitry which cannot be powered on simultaneously at maximum nominal voltage and frequency without exceeding  Thermal Design Power of the chip (Esmaeilzadeh et al., 2012). To prevent chips from melting, modern hardware architects must design thermal-aware layouts that leave large portions of the silicon unpowered or heavily throttled during operation.

## C.2 Thermal Hotspots and Dynamic Thermal Management (DTM)
In AI workload, especially matrices multiplication processed by the Tensor Cores, create immense localize heat known as thermal hotspots. If the junction temperature spike beyond its threshold !!! of 95 C to 105 C, the silicon deteoritate, and error in its logic's will occur. To prevent the damage, modern CPU's and GPU's deeply relying on Dynamic Thermal Management (DTM). DTM is a closed-loop control system that utilize on-die or built-in thermal sensors to monitor temperatures in real-time. When the temperature nearing its critical limit, the hardware automatically initiates power-mitigation phases.

![[Pasted image 20260531184708.png|343]]
**Figure !!!:** Timeline mechanisms for Dynamic Thermal Management initiation and response phases (Adapted from Brooks & Martonosi, 2001).

Any DTM configuration has certain built-in operational delays, as Figure X illustrates. Before the power-throttling feature begins to function, the system starts through a waiting period known as the Initiation Delay, which is the same as the amount of time an operating system has to stop its operations. This is followed by a Response Delay. Once the sensors verify that safe temperature levels have been reestablished, a Policy Delay and a final Shutoff Delay regulate the throttling window's duration.

Thermal throttling is an important safety measure, but it greatly reduce its computing power and efficiency of the HPC. In a large scale operation like data centers, the unexpected delays in the design of the hardware introduce significant tail-latency spikes and straggler nodes. A single thermal straggler has a chance to bottleneck an entire cluster in closely connected systems, directing to disrupted synchronization in distributed AI training workloads severely. Hence, rather than relying solely on reactive, performance-killing clock frequency scaling, current chip design targeted to postpone or entirely avoid these triggering threshold by proactive architectural and structural planning interventions (Brooks & Martonosi, 2001).

## C.3 Architectural Mitigation and Advanced Packaging
To mitigate this dark silicon and thermal throttling problem, hardware engineers utilizing several physical and micro architectural strategies at design phase:
- Thermal-Aware Floorplanning: Lowering activity blocks, such as L2/L3 caches, are intentionally positioned between high activity blocks, notably as floating-point units arithmetic logic units, within the processor's physical layout. 
![[Pasted image 20260601174842.png]]
**Figure !!!:** Microarchitectural block distribution comparison showing (a) unoptimized thermal clustering and (b) thermal-aware layout separation (Adapted from !!!).

This fundamental design demonstrated in Figure !!!. Clustering heat producing nodes (H1 and H2) resulting in hazardous thermal junction due to heat trapping as shown in figure !!!(a). On  the other hand, the high activity blocks are divided by cooler modules (C1 to C5) by the use of thermal-aware layout, as shown in Figure !!!(b). This structural distribution of space disperses the thermal flow over a greater area, which prevent localized energy to accumulate, and allows smoother thermal dissipation throughout the silicon die (Sankaranarayanan et al., 2005).

- Workload and Activity Migration: Hardware schedulers dynamically moved  threads from hot core to cooler core. Modern multi-core systems use migration as a cooperative method instead of considering thermal management as an confined, single-core problem. According to Donald and Martonosi's (2006) classification and Kong et al.'s (2012) review, this thermal control strategy for multi-core systems can be categorized by their usage of task migration as well as controlling granularity (global vs . distributed). 
	![[Pasted image 20260602170847.png]]
**Table !!!:** Classification of Multi-Core Thermal Management Techniques (Adapted from Kong et al., 2012; originally categorized by Donald & Martonosi, 2006).

As illustrated in Table !!!, migration techniques are orthogonal to hardware throttling techniques, like Stop-Go or Dynamic Voltage and Frequency Scaling (DVFS), which are independent of the migration, and used in conjunction with throttling to balance the temperature chip.

This architecture creates optimal heat distribution throughout the die's body by continuously shifting thermally demanding workloads from overheated cores to cooler or to an unused cores. By using "dark silicon" to act as thermal buffer, idle or lower-clocked cores are used in order to maintain peak system speeds and delay the start of throttling. Additionally, these thermal aware schedulers can predict and split workload more swiftly when combined with performance metrics or variation maps that take structural within-die variations in processes into account. This reduces peak core temperature up to 4.5!!! C when compared to scheduler variation-unaware technique (Kursun and Cher, 2008, as cited in Kong et al., 2012)
- Challenges in 3D Stacking: Semiconductor manufacturer are moving from traditional planar layouts and towards 3D Integrated Circuits (3-D ICs) with the goal to improve memory bandwidth in high performance computing while getting around interconnect constraints. As detailed in a comprehensive microelectronics review by Salvi and Jain (2021), vertical integration is achieved by implementing HBM or High Bandwidth memory which can be positioned next or on top of logic processors in 3-D ICs  by stacking and linking multiple heterogeneous die layers. Figure!!! below shows a structural overview of this vertical integration

![[Pasted image 20260602170523.png]]
**Figure !!!:** Cross-sectional schematic of a bonded 3-D chip stack utilizing face-to-face and face-to-back tier configurations (Adapted from Salvi & Jain, 2021).

Vertically stacking creates multidimension heat management issues yet it significantly reduces transmission delay (Salvi & Jain, 2021, p. 802).  As shown in Figure !!! the multilayer structure of the stack are making restricted ways for heat dissipation. Only one outer surface is left exposed external heat sink since the other end of the stack is normally occupied by underlying package connections and substrates. High vertical thermal resistance complicates trapping of thermal energy within the lower and intermediate active silicon tiers caused by spatial limitation. The low thermal conductivity of interlayer dielectrics (ILDs) and the intrinsic thermal contact resistance at soldered interdie mating contacts are major physical causes of this resistance (p. 803).

Advanced architectures address these problem using such as highly conductive polymer underfills or advanced thermal interface materials (TIMs) deisgned to allow lateral heat spreading across wide plane of individual layers (Salvi & Jain, 2021, pp. 803, 809). It is placed next to copper Through-Silicon Vias (TSVs) in dense spatial clusters. These TSVs are increasingly co-engineered as structural "thermal micro-vias" to function as primary vertical heat dissipation networks from active logic hotspots (pp. 802-803).

In the end, architectural efficiency is no longer sufficient to solve the thermal challenge in both CPU and GPU designs. A detailed plan is required due to the physical limitations of heat dissipation at the silicon level, which completely bind chip-level thermal management to the macro-level cooling systems and energy trade-offs of the current data center.

REFERENCE
https://www.ece.ucdavis.edu/~bbaas/281/papers/ChandrakasanLowPower.pdf

https://research.cs.wisc.edu/vertical/papers/2011/isca11-darksilicon.pdf

https://mrmgroup.cs.princeton.edu/papers/dbrooks-hpca2001.pdf

https://engineering.usu.edu/ece/files/pdfs/student-papers/reports/2010/morab-gautam-ms-report-2010.pdf

https://www.cs.virginia.edu/~skadron/Papers/jilp-distribute.pdf

https://www.cs.virginia.edu/~skadron/Papers/kong_dtmsurvey_csur.pdf

https://www.researchgate.net/publication/349824339_A_Review_of_Recent_Research_on_Heat_Transfer_in_Three-Dimensional_Integrated_Circuits_3D_ICs


13-19