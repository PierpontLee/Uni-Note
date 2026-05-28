 # Chapter1
## Algorithm Design
- Recursive method
	- Recursive algorithm: Solved problem by calling themselves
	- Divide and Conquer: Divide into smaller problem, solve and combine
- Optimization methods:
	- Dynamic Programming: solve overlapping subproblem by storing result
	- Greedy Approach: build solution step by step, always choosing the best local option
- Search method:
	- Backtracking : Explore all possibilities, undoing choice when needing
	- Branch and bound 
	- Brute force
- Randomized method:
	- Randomized algorithm
## Algorithm Phases
- Design: Identify and undertsand the problem
- Analysis: compare algorithm
- Inplementation: code
- Experiment: test with diff input
## Types of Algorithm Efficiency
- Time Efficiency
- Space Efficiency
## Asymptotic Notation
- Big-O: worst time complexity
- Big-$\Omega$ (Omega): Best time complexity
- Big-$\Theta$ (Theta): Tight bound

## Knowing Big O
| Pattern                                                              | Big O        | Example                       |
| -------------------------------------------------------------------- | ------------ | ----------------------------- |
| `for (i=1; i<n; i*=2)`                                               | O(log n)     | Binary search                 |
| Divide problem in half each time<br>`for (int i = n; i > 1; i /= 2)` | O(log n)     | Recursive halving             |
| Two loops both log                                                   | O((log n)^2) | Nested halving                |
| n * log n                                                            | O(n log n)   | Merge sort, Heap sort         |
| log(log n)                                                           | O(log log n) | Some advanced data structures |

| Pattern                          | Big O        |
| -------------------------------- | ------------ |
| No loop                          | O(1)         |
| One loop                         | O(n)         |
| Loop with `i*=2` or `i/=2`       | O(log n)     |
| Loop with `i * i < n`            | O(√n)        |
| Nested loops                     | O(n²)        |
| Loop + log loop                  | O(n log n)   |
| Recursion dividing n by 2        | O(log n)     |
| Divide + combine all subproblems | O(n log n)   |
| Permutations or subsets          | O(2ⁿ), O(n!) |
# Chapter 2
## 2.1 Indicator Random Variables (IRV)
	Used to simplify expected-value calculation in probabilistic analysis.
An IRV represents whether an event occurs:
$$
X_i =
\begin{cases}
1 & \text{if event occurs} \\
0 & \text{otherwise}
\end{cases}
$$
Example: Coin Flip
- X = 1 if heads
- X = 0 if tails
- E[X] = $(1 \times 1/2) + (0 \times 1/2) = 1/2$ 
	-> Expected number of heads = $1/2$
![[Pasted image 20251103112436.png#screen]]
## 2.2 Amortized Analysis
Technique to analyze a **sequence of operations** to show that the **average cost per operation is small**, even if some operation are expensive.
- Computes average running time per operation in the worst case
- No Probabilities 
- Focused on **sequence** of operation
- Expensive operation are amortized(spread) over many cheap ones.
Example:
- Dynamic array insertion: occasional resizing is costly , but amortized cost = O(1)
### 2.2.1 Technique
- Aggregate Method:
	Compute total cost of operations and divide by n to get average.
	Example: Dynamic Table
	- When table is full > allocate double sized table > copy content > insert new item
	- Balance space and time efficiently
- Accounting method:
	Assign amortized cost to each operation
	Some operations are overcharged and stores as "credit"
	Credit is used to pay for future expensive operation
	Example: Dynamic table insertion
	- Charge 1 per insertion > insufficient
	- Charge 2> still not enough
	- Charge 3 > works (covers all cost and maintains non negative credits)
- Potential method:
	measuring stored "energy" or credit in the system
	Amortized cost = actual cost + change in potential
	If potential (up): Overcharged (store energy)
	If potential (down): Undercharged (use stored energy)

---
# Chapter 3
## 3.1 Recurrences
### 3.1.1 Recursion
A function that calls itself until a condition is reached
**Examples:**
- **Factorial:**  
    $n!=n×(n−1)!$, with base case $1!=1$
```
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n-1)
```
	Stack expansion for n = 5
	5 x 4 x 3 x 2 x 1 = 120
- Fibonacci:
		$F(n)= F(n-1) + F(n-2),\:F(0) = 0,\:F(1) = 1$ 
### 3.1.2 Recurrences in Algorithm Analysis
When analyzing **recursive algorithms**, their **time complexity** can be expressed as a **recurrence relation**.
##### Common Form
$$
\large {T(n) = aT(\frac{n}{b}) + f(n)}
$$

	Where:
		- a = number of recursive calls
		- n/b = size of each subproblem
		- f(n) = extra (non-recursive) work per call
### 3.1.3 Method to solve recurrence
| Method                       | Description                         | Typical Use                                     |
| ---------------------------- | ----------------------------------- | ----------------------------------------------- |
| **Iteration (Expansion)**    | Expand recurrence step-by-step      | Simple forms, like T(n)=T(n-1)+k                |
| **Substitution (Induction)** | Guess the solution and prove it     | General-purpose; often used with Master Theorem |
| **Master Theorem**           | Direct formula for divide & conquer | Algorithms like MergeSort, QuickSort            |
### 3.1.4 Iteration method (Expansion method)
Keep expanding $T(n)$ until reaching the best case, then sum the terms
Example 1:
$$
\begin{align*}
&T(n) = T(n-2) + 1 + 1 = \:...\:=T(1)+(n-1)\\
\\
&expand:\\
&T(n) = T(n\\
\\
&Result:\\
&T(n) = T(1) +(n-1) = O(n)
\end{align*}
$$
Example 2:
```
void Test(int n) {
    if (n > 0) {
        print(n);      // cost = 1
        Test(n-1);     // recurrence: T(n) = T(n-1) + 1
    }
}
```
same as example 1

Example 3:
$$T(n) = c + T(n/2)$$
Expand:
$$T(n) = c +c + c+...+T(1)$$
	number of times = $\log_2{n}$
Result:
$$T(n) = O\log n$$
##### **Iteration Method Summary**
| Recurrence               | Solution        | Order            |
| ------------------------ | --------------- | ---------------- |
| $T(n) = T(n-1) + 1$      | $(O(n))$        | Linear           |
| $T(n) = T(n/2) + c$      | $(O(\log n))$   | Logarithmic      |
| $T(n) = 2T(n/2) + n$     | $(O(n \log n))$ | Divide & Conquer |
| $T(n) = T(n-1) + n$      | $(O(n^2))$      | Quadratic        |
| $T(n) = T(n-1) + \log n$ | $(O(n \log n))$ | Superlinear      |
### 3.1.5 Substitution Method
##### **Idea**
1. Guess the solution form (using experience or pattern).
2. Use **mathematical induction** to prove your guess correct.
##### **Steps**
1. Make a **good initial guess** (e.g., T(n) = O(n log n)).
2. **Substitute** into the recurrence.
3. **Verify** both base and inductive cases.
4. Adjust constants if inequality doesn’t hold.

### 3.1.6 Master Theorem
For recurrence of the form:
$$\large {T(n) = aT(\frac{n}{b}) + f(n)}$$

| Case | Condition                                         | Result                          |
| ---- | ------------------------------------------------- | ------------------------------- |
| 1    | $f(n) = O(n^{\log_b a - ε})$                      | $T(n) = Θ(n^{\log_b a})$        |
| 2    | $f(n) = Θ(n^{\log_b{a}})$                         | $T(n) = Θ(n^{\log_b a} \log n)$ |
| 3    | $f(n) = Ω(n^{\log_b a + ε})$ and regularity holds | $T(n) = Θ(f(n))$                |
##### REFERENCE TABLE
| Recurrence         | Solution      | Complexity       | Example             |
| ------------------ | ------------- | ---------------- | ------------------- |
| $T(n)=T(n-1)+1$    | $O(n)$        | Linear           | Simple recursion    |
| $T(n)=T(n/2)+1$    | $O(\log n)$   | Logarithmic      | Binary search       |
| $T(n)=2T(n/2)+n$   | $O(n \log n)$ | Divide & Conquer | MergeSort           |
| $T(n)=2T(n/2)+n^2$ | $O(n^2)$      | Quadratic        | Divide-heavy        |
| $T(n)=T(n-1)+n$    | $O(n^2)$      | Quadratic        | Simple loop         |
| $T(n)=2T(n-1)+1$   | $O(2^n)$      | Exponential      | Fibonacci recursion |
## 3.2 Recursion Tree
A recursion tree visually represent how a recurrence expands as recursive calls are made.
- Each node > a subproblem
- Node Label > cost
- Tree depth > level of recursion until base case
- Help to estimate total cost by adding work done at every level.
_Rule of thumb:_ ignore constants, floors/ceilings while sketching; clean them later if proving formally.

##### **Steps to Use a Recursion Tree**
1. **Draw the tree** for the recurrence T(n).
2. **Label each node** with the work per call f(n).
3. **Compute cost per level.**
4. **Count number of levels** (until subproblem size = 1).
5. **Sum costs of all levels** → total T(n).
6. **Simplify (often geometric series).**

###### Example 1
$$T(n)=T(n/3)+T(2n/3)+O(n)$$
Step 1 Interpret:
Each problem splits into two subproblem: sizes $n/3$ and $2n/3$, plus O(n) work to combine.

Step 2 Tree levels:
- Level 0: Cost = n
- Level 1: Cost from sub problems $\approx$ ($n/3 + 2 n/3$) = $n$
- Level 2: Each sub problem again adds up to n, etc.
thus each level costs roughly n, until subproblem size = 1

Depth: $\approx \log_(3/2n)n = O(\log n)$  
**Total Cost:**
$$T(n) = n \times O(\log n) = O(n \log n)$$
###### Example 2
$$T(n) =3T(n/4) + cn^2$$
- level 0: cost $n^2$
- level 1: $3 \times (n/4)^2 = (3/16) n^2$
- level 2: $9 \times (n/16)^2 = (9/256)n^2$
- ...
Total cost $\approx$ geometric series:
$$\large{n^2(1+\frac{3}{16}+\frac{9}{256})}$$
ratio: r =3/16 < 1 $\implies$ converges
T(n) = $O(n^2)$

### 3.2.1 Master Theorem
##### Form
$$T(n) = aT(\frac nb) + f(n)$$
where
- _a_ = # of subproblems,
- _b_ = factor each subproblem reduces size by,
- _f(n)_ = extra work outside recursion.

Compute the critical exponent:
$$\huge{n^{\log_ba}}$$
and compare $f(n)$ to that

##### Case 1 - Subproblem work dominates
If
$$\huge{f(n) = O(n^{\log_ba-\epsilon})}$$
for some $\epsilon>0$ 
then
$$\huge{T(n) = \theta(n^{\log_ba})}$$
	**Intuition:** cost grows mainly from leaves
Example:
	$T(n) = 4T(\frac{n}{2})+n$
	a = 4
	b =2
	$\implies n^{\log_24}$
	$\implies n^2$
	since $f(n)=n=O(n^{2-1})$
	T(n) = $\theta(n^2)$ 

##### Case 2 - Balanced work
If
$$\huge{f(n) = O(n^{\log_ba})}$$
then
$$\huge{T(n) = \Theta(n^{\log_ba}\log n)}$$
Example: $T(n) = 2T(n/2) +n$
a = b = 2, f(n) = n = $\theta (n^{log_22})\implies T(n)=\theta(n\log n)$

##### Case 3 - Combination work dominates
If
$$f(n)=\Omega(n^{\log_ba+\omega})$$
and a $f(n/b) \leq k\:f(n)$  for some $k <1$ (regularity condition)
then $$T(n) = \Theta (f(n))$$
	example: $T(n) = 2T(n/2)+ n ^2$ 
		$n^{\log_22} = n,\: f(n)=n^2 >n$, regularity holds $\implies T(n) = \Theta(n^2)$
##### Summary table
| Case | Condition on _f(n)_                    | Result                       |
| ---- | -------------------------------------- | ---------------------------- |
| 1    | $\Huge(f(n)=O(n^{log_b a−ε})$          | $\huge Θ(n^{log_b a})$       |
| 2    | $\Huge f(n)=Θ(n^{log_b a})$            | $\huge Θ(n^{log_b a} log n)$ |
| 3    | $\Huge f(n)=Ω(n^{log_b a+ε})$, regular | $\huge Θ(f(n))$              |
##### Example Application
| Recurrence      | a   | b   | f(n) | Case | Result                   |
| --------------- | --- | --- | ---- | ---- | ------------------------ |
| T(n)=2T(n/2)+n  | 2   | 2   | n    | 2    | Θ(n log n) (MergeSort)   |
| T(n)=T(n/2)+1   | 1   | 2   | 1    | 1    | Θ(log n) (Binary Search) |
| T(n)=3T(n/4)+n  | 3   | 4   | n    | 2    | Θ(n log n)               |
| T(n)=2T(n/2)+n² | 2   | 2   | n²   | 3    | Θ(n²)                    |
| T(n)=4T(n/2)+n  | 4   | 2   | n    | 1    | Θ(n²)                    |
![[Pasted image 20251112094847.png#screen]]
##### Common Patterns
| Algorithm                | Typical Recurrence | Complexity  |
| ------------------------ | ------------------ | ----------- |
| MergeSort                | T(n)=2T(n/2)+O(n)  | O(n log n)  |
| QuickSort (avg.)         | T(n)=2T(n/2)+O(n)  | O(n log n)  |
| Binary Search            | T(n)=T(n/2)+O(1)   | O(log n)    |
| Strassen Matrix Multiply | T(n)=7T(n/2)+O(n²) | O(n^{2.81}) |
| DFS/BFS                  | T(V+E)             | Linear      |

---
# Chap 4 Divide and Conquer
Problem-solving strategy that breaks a large problem into smaller sub-problems, solves each one individually, and combines the results to form the final solution.

## 4.1 Binary Search
Compare the search key `x` with the middle element of the array.
- If `x` = mid  $\implies$ found
- If `x` < mid  $\implies$ Search in the left half
- If `x` > mid  $\implies$ Search in the right half
repeat until found or range becomes empty

```
lower = 0
upper = N - 1
while (lower ≤ upper):
   mid = (lower + upper) / 2
   if X == K[mid]:
        return mid
   else if X < K[mid]:
        upper = mid - 1
   else:
        lower = mid + 1
return "Not Found"
```
Recursive version
```
BinarySearch(A, low, high, key):
   if low > high:
       return -1
   mid = (low + high) / 2
   if A[mid] == key:
       return mid
   if key < A[mid]:
       return BinarySearch(A, low, mid-1, key)
   else:
       return BinarySearch(A, mid+1, high, key)
```
##### **Example**

Search key = 42 in sorted array `[1, 5, 8, 11, 13, 20, 25, 42, 50, 63]`

1. mid = 5 → A[5]=20 → 42 > 20 → search right half
2. mid = 8 → A[8]=42 → found ✅  
    Took 2 comparisons.
##### Complexity
| Case    | Steps                   | Complexity |
| ------- | ----------------------- | ---------- |
| Best    | Found at mid            | O(1)       |
| Worst   | Recurse until 1 element | O(log₂ n)  |
| Average | Half comparisons        | O(log₂ n)  |
## 4.2 Merge Sort
1. Find middle index `mid = (left + right)/2`
2. Divide array into:
    - Left half: A`left … mid`
    - Right half: A`mid+1 … right`
3. Recursively apply MergeSort to both halves.
4. Merge the two sorted halves into one sorted array.
##### Pseudocode
```
MergeSort(A, left, right):
   if left < right:
       mid = (left + right) / 2
       MergeSort(A, left, mid)
       MergeSort(A, mid+1, right)
       Merge(A, left, mid, right)
```
##### Merging two sorted sub-arrays
```
Merge(A, left, mid, right):
   i = left, j = mid+1, k = left
   while i ≤ mid and j ≤ right:
        if A[i] ≤ A[j]:
            Temp[k++] = A[i++]
        else:
            Temp[k++] = A[j++]
   while i ≤ mid:
        Temp[k++] = A[i++]
   while j ≤ right:
        Temp[k++] = A[j++]
   Copy Temp[left…right] → A[left…right]
```
Time complexity
$$O(m+n)$$
where m and n are the sizes of the subarrays

##### **Example**
Sort `[15, 7, 4, 11, 2, 20, 8, 1, 5]`
1. Divide → `[15,7,4,11]` and `[2,20,8,1,5]`
2. Keep dividing until single elements.
3. Merge step-by-step:
    - Merge [7,15] → [4,11,7,15] → [2,5,8,20,1] → Final sorted array.
##### **Visualization**
Recursive calls form a **binary tree**:
- Top: full array
- Bottom: single elements (base cases)
- Merge upward level by level
Recursion traversal:
- **Call order:** Preorder (Root → Left → Right)
- **Merge order:** Postorder (Left → Right → Root)
##### **Time Complexity**

| Phase  | Cost per Level | Levels | Total      |
| ------ | -------------- | ------ | ---------- |
| Divide | O(1)           | log₂ n | O(log n)   |
| Merge  | O(n)           | log₂ n | O(n log n) |
## 4.3 Quick Sort
Divide the array into **two subarrays** using a pivot:
- **Left subarray:** all elements ≤ pivot
- **Right subarray:** all elements > pivot
- Pivot is then in its **final sorted position**
- Recursively sort both subarrays
##### Steps in Quicksort

| Step                  | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| **1. Choose a Pivot** | Common choices: first, last, middle, or random element                   |
| **2. Partition**      | Rearrange array so all elements ≤ pivot are left, > pivot are right      |
| **3. Recursion**      | Recursively apply QuickSort to left and right partitions                 |
| **4. Combine**        | The array is sorted when recursion finishes (no explicit merging needed) |
##### Pseudocode
```
int Partition(int A[], int low, int high) {
    int pivot = A[low];   // or A[high]
    int i = low + 1;
    for (int j = low + 1; j <= high; j++) {
        if (A[j] <= pivot) {
            swap(A[i], A[j]);
            i++;
        }
    }
    swap(A[low], A[i - 1]);
    return (i - 1);   // new pivot position
}
```
![[Pasted image 20251113125452.png]]
![[Pasted image 20251113125509.png]]
![[Pasted image 20251113125948.png]]

Array: `[10, 3, 5, 16, 9, 15, 6, 12]`
1. Pivot = 12  
    → After partition: `[10, 3, 5, 9, 6 | 12 | 15, 16]`
2. Recursively apply QuickSort to left `[10, 3, 5, 9, 6]` and right `[15, 16]`
3. Sorted result: `[3, 5, 6, 9, 10, 12, 15, 16]`

| Case             | Description                                        | Recurrence              | Time Complexity |
| ---------------- | -------------------------------------------------- | ----------------------- | --------------- |
| **Best Case**    | Pivot divides array equally                        | (T(n) = 2T(n/2) + O(n)) | **O(n log n)**  |
| **Average Case** | Random pivots (expected balanced)                  | (T(n) = 2T(n/2) + O(n)) | **O(n log n)**  |
| **Worst Case**   | Pivot divides array unevenly (already sorted data) | (T(n) = T(n-1) + O(n))  | **O(n²)**       |
### 4.3.1 Strassen's Matric Multiplication
Matrix multiplication is fundamental in data processing, computer graphics, and scientific computation
For two matrices **A** and **B** of size n×n:
$$C=A \times B$$
Each element $C_{ij}$​ = sum of products of corresponding elements in row i of A and column j of B
#### *Standard Matrix Multiplication*

For n×n matrices:
$$T(n)=8T(n/2)+O(n2)$$
→ **O(n³)** operations (since each multiplication is recursive).
- Standard algorithm requires 8 recursive multiplications per level.
- Strassen reduced it to **7 multiplications** with extra additions/subtractions.
- First faster-than-O(n³) matrix multiplication algorithm.
![[Pasted image 20251114165412.png]]
Time Complexity
$$T(n)=7T(n/2)+O(n2)$$
By **Master Theorem**:
$$T(n)=O(n^{\log_2 7})≈O(n^{2.81})$$
**Faster** than O(n³) classical method.

##### **Limitations**
- Works only when n is a **power of 2** (e.g., 2, 4, 8, 16, …).  
    → Pad with zeros if needed.
- For small matrices, normal method may be faster (less overhead).
- Not numerically stable for floating-point arithmetic.




# Exercise Only
## Chap 1 BIG-O

| Pattern                          | Big O        |
| -------------------------------- | ------------ |
| No loop                          | O(1)         |
| One loop                         | O(n)         |
| Loop with `i*=2` or `i/=2`       | O(log n)     |
| Loop with `i * i < n`            | O(√n)        |
| Nested loops                     | O(n²)        |
| Loop + log loop                  | O(n log n)   |
| Recursion dividing n by 2        | O(log n)     |
| Divide + combine all subproblems | O(n log n)   |
| Permutations or subsets          | O(2ⁿ), O(n!) |

## Chap 2 AMORTIZED ANALYSIS
### 2.1 AGGREGATE METHOD
$$Amortized\:cost=\frac{Total\:cost\: for\: n\: operations}{n}​$$
### **Example:** 
Dynamic Array Doubling:

TOTAL COST CALCULATION
Resizing happens at sizes:
- 1 → cost 1
    
- 2 → cost 2
    
- 4 → cost 4
    
- 8 → cost 8  
    Total resizing cost = 1 + 2 + 4 + 8 + … = **O(n)**
Total cost of normal insertions = **n**
Total cost = n (inserts) + (n − 1) (copies)  
= **2n**
 **Amortized cost:**
 $$\frac{2n}{n}=2=O(1)$$
 
### 2.2 ACCOUNTING METHOD
#### EXAMPLE 2 — Same Dynamic Array Example
Let’s assign:
- Actual normal insert cost = 1
- Actual resize cost = n
- **We charge each insert = 3 units**

Why 3?
- 1 unit for actual insert
- 2 units saved to pay for copying during resize
#### Does it work?
For an array of size n:
- Each item is copied **once**
- Saved 2 credits for each insert
- Enough to cover its future copying

Hence total credit is enough → amortized cost = 3 = **O(1)**.

# Chapter 3
## 3.1 Iteration method
T(n) = T(n – 1) + 1
Let’s solve an easy pattern.
Step 1: Write out first few values
Let n = 5:
T(5) = T(4) + 1
T(4) = T(3) + 1
T(3) = T(2) + 1
T(2) = T(1) + 1
Stop here.

Now add them together:
T(5)
= T(1) + 1 + 1 + 1 + 1
= T(1) + 4

So for general n:
T(n)=T(1)+(n−1)

This is linear growth, meaning:
T(n)=O(n)

## 3.2 Recursion Tree

## 3.3 Master Theorem
Use this when the recurrence looks like:
$$T(n)=aT(n/b)+f(n)$$

Where:
- **a** = number of subproblems
- **b** = shrink factor
- **f(n)** = work outside (combining cost)
compute:
$$\Huge{n^{\log_b a}}$$
Then compare it to f(n).
#### If (Subproblem Dominate):

$$\Huge f(n) < n^{\log_b a}$$

Then:
$$\Huge T(n) = Θ(n^{\log_b a})$$
### If (Equal):
$$\huge f(n) = n^{\log_b a}$$
Then:
$$\huge T(n) = Θ(n^{\log_b a} \log n)$$
### If (f(n) Dominate):
$$\huge f(n) > n^{\log_b a}$$
Then:
$$T(n) = Θ(f(n))$$
