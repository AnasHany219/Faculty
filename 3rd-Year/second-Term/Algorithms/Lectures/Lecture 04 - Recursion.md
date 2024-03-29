## Recursive Functions

- **Definition:** A routine that calls itself directly or indirectly.
- Must eventually terminate.
- Must have at least one base or stopping recursive case.
  - Base case does not execute a recursive call.
  - Stops the recursion.
- Each successive call to itself must be a "smaller version of itself":
  - Argument describes a smaller problem.
  - Eventually, a base case is reached.
### Example: Factorial Function

```cpp
int Fact(int n) {
    if (n == 0) // Base case
        return 1;
    else // Recursive case
        return Fact(n-1) * n;
}
```
## How to Compute Running Time?
- $T(n) = \text{time of recursive base} + \text{time of base case}$
- Example:
  - $T(n) = T(n-1) + 1$
  - $T(n) = T(n-1) + n$
  - $T(n) = 2T(n/2) + n$
## How to Compute Asymptotic Notations of Recursion?
### Solving Recurrences

- Equation or inequality describing a function in terms of its value on smaller inputs.
- Need to solve the recurrence to find the actual running time of the algorithm.
### Methods for Solving Recurrences
1. **Substitution Method**
2. **Tree Method**
3. **Master Method**

#### Tree Method
- Convert the recurrence into a tree:
  - Each node represents the cost at various levels of recursion.
  - Sum up the costs of all levels.
- Example:
  - $T(n) = 2T(n/2) + n$

1. Draw the tree.
2. Compute the height of the tree:
   - If the recursion part contains division: $height = \log_2 n$
   - If the recursion part contains subtraction: $height = n$
3. Compute the value of each level (non-recursive part).
4. Compute the whole value of the tree.

#### Example: $T(n) = 2T(n/2) + n$
- Tree: $1 + 2 + 4 + ...$
- $T(n) = n \log_2 n$

#### Methods for Computing Tree Value
##### 1. Summation
- If all values of levels are equal:
  $$T(n) = \sum_{height}(i=1)levelvalue$$
  - $L_0 = n$
  - $L_1 = n$
  - $L_2 = n$
  $$T(n) = \sum_{\text{log}_2 n}(i=1)n$$
  $$T(n) = n \log_2 n$$
  This equation doesn’t contain recursion.
  **Result:** $O(n \log n)$

##### 2. Arithmetic
- If the difference between levels values is a sum or subtraction:
  $$T(n) = \frac{height \times (L_1 + L_{n})}{2}$$
  - Tree: $1 + 3 + 5 + 7 + \ldots$
  - $L_1 = \text{value of level } 1$
  - $L_{n} = \text{value of last level}$
  - $height = \text{height of the tree}$
  
##### 3. Geometric
- If the difference between levels values is a multiplication or division:
  - **Division:**
    $$T_{tree} = \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \ldots$$
    $$L_1 = \text{value of level } 1$$
    $$r = \text{multiplied value}$$
    $$T(n) = \frac{L_1}{1 - r}$$
  - **Multiplication:**
    - Tree: $1 + 2 + 4 + 8 + \ldots$
    $$L_1 = \text{value of level } 1$$
    $$r = \text{multiplied value}$$
    $$T(n) = \frac{L_1 \left(1 - r^{height}\right)}{1 - r}$$
