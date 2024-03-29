## Recursive Functions 🔁
- ![[Recursive Functions.png]]

- **Definition:** A routine that `calls itself directly` or `indirectly`.
- Must eventually terminate.
- Must have `at least one base` or stopping recursive case.
	- Base case does not execute a `recursive call`.
	- `Stops` the recursion.
- Each successive call to itself must be a `smaller version of itself`:
	- Argument describes a `smaller problem`.
	- Eventually, a base case is `reached`.
## How to Compute Running Time?

- $T(n) = \text{time of recursive base} + \text{time of base case}$
### Example: Factorial Function

 - $T(n) = 1 + T(n - 1)$
```cpp
int Fact(int n) {
    if (n == 0) // Base case
        return 1;
    else // Recursive case
        return Fact(n-1) * n;
}
```
## How to Compute Asymptotic Notations of Recursion?
### Solving Recurrences

- `Equation` or `inequality` describing a function in terms of its value on smaller inputs.
- Need to solve the recurrence to find the actual running time of the algorithm.
### Methods for Solving Recurrences

1. **Substitution Method**
2. **Tree Method**
3. **Master Method**
#### Tree Method
- Convert the `recurrence` into a `tree`:
	- Each node represents the `cost at various levels` of recursion.
	- `Sum` up the `costs` of all levels.
- Example:
	- $T(n) = 2T(\frac{n}{2}) + n$
1. Draw the tree.
2. Compute the height of the tree:
	- If the recursion part `contains division`: $height = \log_2 n$
	- If the recursion part `contains subtraction`: $height = n$
1. Compute the value of each level `non-recursive part`.
2. Compute the whole value of the tree.
#### Example: $T(n) = 2T(n/2) + n$
- Tree: $1 + 2 + 4 + ...$
- $T(n) = n \log_2 n$

#### Methods for Computing Tree Value
##### 1. Summation
- If `all` values of levels are `equal`:
  $$T(n) = \sum_{i=1}^{height}\text{level value}$$
  - $L_0 = n,\ L_1 = n,\ L_2 = n$
  $$T(n) = \sum_{i=1}^{log_2 \ n}n = n \log_2 n = O(n\ logn)$$
##### 2. Arithmetic
- If the `difference` between levels values is a `sum` or `subtraction`:
  $$T(n) = h(\frac{(L_1 + L_{n})}{2})$$
  - Tree: $1 + 3 + 5 + 7 + \ldots$
  - $L_1 = \text{value of level } 1$
  - $L_{n} = \text{value of last level}$
  - $h = \text{height of the tree}$
##### 3. Geometric
- If the `difference` between levels values is a `multiplication` or `division`:
	- **Division:** $\large T_{tree} = \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \ldots$
	- $L_1 = \text{value of level } 1$
	- $r = \text{multiplied value}$
$$\large T(n) = \frac{L_1}{1 - r}$$
  - **Multiplication:**
    - Tree: $1 + 2 + 4 + 8 + \ldots$
    - $L_1 = \text{value of level } 1$
    - $r = \text{multiplied value}$
    - $h = \text{height}$
$$\large T(n) = L_1(\frac{1 - r^{h}}{1 - r})$$