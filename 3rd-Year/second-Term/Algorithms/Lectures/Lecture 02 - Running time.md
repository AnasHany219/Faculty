## The Running Time
- It is the number of steps executed.
### Example: Sorting Numbers
- Array size: $10^6$
#### Ahmed’s Computer
- Performs $10^9$ operations per second
- Ahmed’s Algorithm: $2𝑛^2$ operations
- Time taken by Ahmed’s computer: 
  $$Time = \large\frac{Algorithm \ complexity}{device \ speed} = \frac{2 × (10^6)^2}{10^9} = 200s$$
#### Mohamed’s Computer
- Performs $10^7$ operations per second
- Mohamed’s Algorithm: $50𝑛log𝑛$ operations
- Time taken by Mohamed’s computer: 
  $$Time = \large\frac{Algorithm \ complexity}{device \ speed} = \frac{50 × 10^6 log 10^6}{10^7} = 100s$$
### Typical Running Time
- 1 (constant) 🕰️
- $\log{n}$ (logarithmic) 🔍
- $𝑛^𝑘$ (polynomial)
  - $𝑛$ linear 📈
  - $𝑛^2$ quadratic 📉
  - $𝑛^3$ cubic 📉
- $2^𝑛$ (exponential) 💥
![[run-time-1.png]]
![[run-time-2.png]]
## Loop
  - **Nested loop:**
    ```python
    for i = 1 to n
      for j = 1 to n
        print 'Hi'
	```
$$\large\sum_{i=1}^{n} n$$
  - **Dependent nested loop:**
    ```python
    for i = 1 to n
      for j = 1 to i
        print 'Hi'
    ```
$$\large\sum_{i=1}^{n} i$$
## Sum Equations
### Why Study Summations?

1. The running time of a loop can be expressed as the sum of the running time of each iteration.
2. Summations come up in solving recurrences.

	- $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$
	
	- $\sum_{i=1}^{n} constant \; or \; n = n^2$
	
	- $\sum_{i = 1}^{\log_2{n}} 2^i = 2n - 1$

![[Sum-Equations.png]]
## Insertion Sort

**Input:**  The program accepts a sequence of numbers denoted by `a1, a2, ..., an`.
**Output:** The program outputs a permutation (reordering) of the input sequence such that` a1 ≤ a2 ≤ ... ≤ an`. In other words, the output should be the original sequence `in increasing order`.

```c++
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) { // Outer loop runs (n-1) times
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) { // Inner loop may iterate up to j times
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

// Time Complexity Analysis:
// Outer loop runs (n-1) times.
// In the worst-case scenario, each element may need to be moved to the beginning of the array,
// resulting in j iterations of the inner while loop for each iteration of the outer loop,
// where j is the current value of the outer loop index.
// The sum of 1 + 2 + 3 + ... + (n-1) is proportional to n^2.
// Therefore, the time complexity of this Insertion Sort implementation is O(n^2) in the worst-case scenario.
```

![[Insertion Sort.png]]

[[Lecture 03 - Asymptotic Notations]]