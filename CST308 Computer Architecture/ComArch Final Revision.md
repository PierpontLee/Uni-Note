Chapter 1:   
- CPU Performance  
- parameters affecting the CPU performance   
    - Cycles Per Instruction-CPI  
    - Instruction Count-IC,   
    - Cycle Time-seconds per cycle,   
    - clock rate (Hz)-frequency, clock cycles per second   
- Amdahl's Law and speedup - how to measure the overall speedup when a portion or more is improved or parallelized.  
- Number system (binary/decimal/hexa)- 2's complement for negative numbers  
- revise [tutorial 1](https://l.xmu.edu.my/mod/resource/view.php?id=712344 "Tutorial 1")

Chapter 2   
- Instruction Set Architecture - revise tutorial 2  
    - zero operand address (stack)  
    - 1 operand address (accumulator)  
    - 2 operand address (Mem-Mem / Reg-Mem)  
    - 3 operand address (Mem-Reg / Reg-Reg)    
- MIPs instructions - evaluate arithmetic, branch, memory addressing,  register & memory data, etc.  
- CISC vs RISC

Chapter 3  
- memory hierarchy  
- Cache concepts, Cache Map function (direct/fully associative/set associative)  
- cache locality (temporal & spatial)   
- cache replacement policy (LRU/FIFO/LFU)  
- cache write policy  
- Cache performance - AMAT (Avg Memory Access Time) 

Chapter 4  
- Flynn taxonomy (SISD/SIMD/MIMD/etc..)   
- cache coherence problem and cache coherence protocol   
- Pipelining performance, pipeline diagram (stall & forwarding)  
- hazards - data hazards(data dependency)/resource hazard/control hazard



# Chapter 1
## 1.1 CPU performance
Unit things done per second
$$\huge Performance=\frac{1}{ExTime}$$
The bigger the better
X is n times faster than Y means:
$$\huge n = \frac{ExTime_Y}{ExTime_X}=\frac{Performance_X}{Performance_Y}$$
## 1.2 CPU execution time, CPI, IC, cycle time, clock rate (hz)
1. Execution time
	1. Elapse Time
		counts everything (disk and memory accesses, waiting for I/O, running other programs, etc.) from start to finish
		$$ ElapseTime = CPU\:time + wait\: time$$$$Elapsed Time = user CPU time + system CPU time + wait time$$
2. CPU time
	doesn't count waiting for I/O or time spent running other programs
	$$CPU time = user CPU time + system CPU time$$
3. CPU Clock
	relates to how fast the hardware can perform basic functions.\
	cycle time = seconds per cycle
	clock rate (frequency) = cycles per second  (==1 Hz = 1 cycle/sec==) = 1 / cycle time
	A 200 MHz clock has a  1/200Million = 5 x 10-9 s  cycle time.

4. CPU execution time:
	- interm of duration: CPU Time = CPU clock cycles for a program X Clock cycle time
	- interm of clock rate: $\huge CPUtime=\frac{Clock\:cycles\:per\:program}{clockRate}$
5. Cycle per Instruction (CPI): $\huge \frac{CPU\:clock\: cycles\: for\: a\: program}{no.\: of\: instruction}$
6. CPU clock cycles = $\sum^n_{i=1}CPI_i\times IC_i$
	- n: number of instruction classes
	- IC_i: is the count of the number of instructions of class i executed
7. $CPU\:Time = CPU\:clock\: cycles\: for\: a\: program \times Clock\: cycle\: time$

### Example 1
Given:
- Frequency of floating-point (FP) operations = 25%
- Average CPI of floating-point operations = 4.0
- Average CPI for other instructions = 1.33
- Frequency of floating-point square root (FPSQR) = 2%
- CPI for FPSQR = 20
- Note: FPSQR operations are a subset of FP operations
Assume that the two design alternatives: 
- reduce the CPI of FPSQR to 2, or
- reduce the average CPI of all FP operations to 2. 
Question: Compare these two design alternatives using the CPU performance equation.

Answer: 
1. Step 1: Analyze base system
Split into 2 main categories ==Floating Point (FP)== operation and ==other== instruction
Other Instruction:
- Frequency of other instruction: 100% - 25% = 75%
- Average CPI = 1.33
FP Instruction:
- Frequency of FP = 25%
- Average CPI = 4
	_Note:_ The problem mentions Floating-Point Square Root ($\text{FPSQR}$) is a subset ($2\%$) of the total instructions. For calculating the baseline, we can just use the overall FP average ($4.0$) because it already includes $\text{FPSQR}$. (later tanya vincent !!!)

Overall CPI Baseline:
$$\begin{align}
CPI_{baseline}&=(Freq_{FP} \times CPI_{FP})+(Freq_{Other}\times CPI_{Other})\\
&=(0.25\times 4)+(0.75\times 1.33)\\
&=1+0.9975\\
&=1.9975
\end{align}
$$
2. Step 2: Evaluate Alternative 1
reduce the CPI of FPSQR to 2
FPS

# Chapter 2
Instruction Set Architecture
Example:
$$Y=(A-B)/(C+(D*E))$$
## 2.1 zero operand address (stack)
	Step:
		- PUSH A
		- PUSH B
		- SUB
		- PUSH C
		- PUSH D
		- PUSH E
		- MUL
		- ADD
		- DIV
## 2.2 1 operand address (accumulator)
	Step:
		- LOAD A
		- SUB B
		- STORE F
		- LOAD D
		- MUL E
		- ADD C
		- STORE G
		- LOAD F 
		- DIV G
		- STORE Y

## 2.3 2 operand address (Mem-Mem / Reg-Mem)
#### MEM-MEM
Both operands are stored in **memory**.

	Step:
		- MOV T1, A
		- SUB T1, B
		- MOV T2, D
		- MUL T2, E
		- ADD T2, C
		- DIV T1, T2
		- MOV Y, T1

#### Reg-Mem
One operand is in a register and the other is in memory.

	Step:
		- LOAD R1, A
		- SUB R1, B
		- LOAD R2, D
		- MUL R2, E
		- ADD R2, C
		- DIV R1, R2
		- STORE Y, R1
## 2.4 3 operand address (Mem-Reg / Reg-Reg)
OP Destination, Source1, Source2
#### Mem-Reg
Registers hold the intermediate results, and the final result is stored in memory.

	Step:
		- SUB R1, A, B
		- MUL R2, D, E
		- ADD R3, R2, C
		- DIV R4, R1, R3
		- MOV Y, R4

#### Reg-Reg
	Step:
		- LOAD R1, A
		- LOAD R2, B
		- LOAD R3, C
		- LOAD R4, D
		- 	LOAD R5, E
		
		- SUB R6, R1, R2
		- MUL R7, R4, R5
		- ADD R8, R7, R3
		- DIV R9, R6, R8
		- MOV Y, R9
---
# Chapter 3
## 3.1 Memory hierarchy
The memory hierarchy exists because programmers want unlimited fast memory, but fast memory is expensive per bit

Structure: ==Registers $\rightarrow$ L1/L2/L3 Cache $\rightarrow$ Main Memory $\rightarrow$ Disk Storage==
	mobile devices only 2 cache

Trade-offs: As you move down the hierarchy (away from the CPU), the storage size increases, the cost per bit decreases, but the access speed becomes slower.

Primary Goal: To obtain the highest possible average access speed while minimizing the total cost of the memory system.
## 3.2 Cache concepts, Cache Map function (direct/fully associative/set associative)
### Direct Mapping
Each block of main memory maps to _only one_ possible cache line
- Formula: 
`(Block number) % (Number of lines)`
### Fully Associative Mapping
A main memory block can be loaded into _any_ line of the cache.
### Set Associative Mapping
The cache is divided into sets. A main memory block can be mapped into _any line within a specific set_. 
Formula: 
`(Block number) % (Number of sets)`
## 3.3 Cache locality (temporal & spatial)
Principle of locality: program access a relatively small portion of address space, we can
predict with reasonable accuracy what instruction and data a program will next moment
- Temporal Locality
	If something has been accesses it will most likely be accessed again
	Contoh: buku yg diletak di meja (cache) bukan di laci (RAM)
- Spatial Locality
	If one address is getting accessed, the near address might get accesed too
	Contoh: di perpus kalau ambil satu buku mungkin akan ambil buku yg dekat krna topiknya mirip dan mungkin dibutuhin
- WHY important?
	Kalau program ini jalan → hit ratio tinggi → AMAT(Average Memory Access Time) rendah → Fast program

## 3.4 Cache replacement policy (LRU/FIFO/LFU)
- When needed?
	ketika cache penuh atau ada block baru yg masuk
	- Direct ga butuh karena lgsg masuk, sedangkan full/set associative butuh.
- LRU (Least Recently Used)
	Keluarkan blok yg paling lama tidak diakses,
- FIFO (first in first out)
	Walau banyak kali dipakai tetap dikeluarin yg pertama akses
- LFU (Least Frequently USed)
	keluarin blok yang paling jarang diakses, tiap blok punya counter dan counter yg paling kecik dikeluarkan
## 3.5 Cache write policy
a. Write hit
- Write-through
	Tulis di cache dan RAM bersamaan
	(+) Cache dan ram selalu konsisten
	(-) Banyak write ke memori - lambat
- Write-Back
	Tulis ke cache dulu. RAM diupdate kalau ada blok yg mau diganti, dirty data = data yg udah di modif ke cache tpi blm ke ram
	(+) Lebih cepat krna ga ke ram
	(-) Bsa ga konsisten

b. Write miss
- Allocate on Write
	load blok dari RAM ke cache dulu baru tulis
	(+) Bagus untuk temporal loality
	(-) Cache bsa penuh dengan data yg cuma ditulis sekali
- Write around/ Write no Allocate
	(+) Cache tidak terisi data yg jarang pakai
	(-) Miss berikutnya ttp harus ambil dri ram

## 3.6 Cache performance - AMAT (Avg Memory Access Time)
3 metrics
- Hit time = waktu untuk deliver data dari cache ke prosesor termasuk cek apakah data ada di cache
- Miss Rate = fraction of memory reference yang tidak ditemukan di cache
	Miss rate = total misses/total accesses = 1- hit rate
- Miss penalty = additional time yang dibutuhkan karena cache miss waktu untuk ambil data dari level berikutnya

AMAT
`AMAT = Hit time + Miss Rate x Miss Penalty`

CONSO


# Chapter 4
## 4.1 Flynn taxonomy (SISD/SIMD/MIMD/etc..)