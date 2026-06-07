  Chapter 1:
- CPU performance
- CPU execution time, CPI, IC, cycle time, clock rate (hz)
- Speed up - Amdhal's law
- Calculation & Theory
- Number system (binary, 2's complement)
Chapter 2:
- ISA
	- 0 address (symek??)etc
	- 1 address (accumulator)
	- 2 address (MM, R-M)
	- 3 address (R-M, RR)
- MIPS
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
8. 