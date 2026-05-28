# Chapter 5 Dynamic Programming
Algorithm design strategy used to solve **optimization** problem.
Provide an efficient solution by avoid redundant calculation through storing.
- Tabular Method: storing result in the table rather than computing again
## 5.1 Assembly Problem
#### Example 1:
![[Pasted image 20251231100209.png]]
	*Solving step*:
Station 1
Line 1: 9
Line 2: 12

Station 2
Line 1: Stay:	18
	Switch:	23	Stay
Line 2:	Stay:	17
	Switch:	16	Switch

Station 3
Line 1: Stay:	21
	Switch:	20	switch
Line 2:	Stay:	22
	Switch:	27	Stay

Station 4
Line 1: Stay:	24
	Switch:	28	Stay
Line 2:	Stay:	26
	Switch:	25	Switch

Station 5
Line 1: Stay:	32
	Switch:	35	Stay
Line 2:	Stay:	30
	Switch:	32	Stay

Station 6
Line 1: Stay:	36
	Switch:	35	Switch
Line 2:	Stay:	37
	Switch:	43	Stay

Exit
Line 1: 35+3 = 38
Line 2: 37+2 = 39
Optimal total time 38 Line 1. i* = 1

Construct Path:
2 < 2 < 1 < 2 < 1 < 1

#### Example 2
![[Pasted image 20251231100421.png]]
	*Solving step:*
Station 1
Line 1: Stay:	14
Line 2:	Stay:	14

Station 2
Line 1: Stay:	19
	Switch:	28	Stay
Line 2:	Stay:	24
	Switch:	31	Stay

Station 3
Line 1: Stay:	22
	Switch:	29	Stay	
Line 2:	Stay:	25
	Switch:	24	Switch

Station 4
Line 1: Stay:	24
	Switch:	34	Stay
Line 2:	Stay:	28
	Switch:	31	Stay

Exit
Line 1: 24+18 = 42
Line 2: 28+7 = 	35
i* = 2

2 < 2 < 1 < 1


## 5.2 Longest Common Subsequence
