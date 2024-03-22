#### 1. Is $\log(n): \ O(n)$ or $\Omega(n)$?

- **Answer**: $\log(n) \ is \ O(n)$.  
- **Explanation**: 
	- $\log(n)$ grows slower than linearly, making it belong to $O(n)$.
#### 2. Prove or disprove: $n^2 + n = O(n^2)$.

- **Answer**: $n^2 + n = O(n^2)$.
- **Explanation**: 
	- By finding suitable constants $c$ and $n_0$, we can prove that $n^2 + n$ is bounded by $n^2$ for all $n \geq n_0$.
#### 3. Investigate whether $2^n = O(3^n)$.

- **Answer**: Yes, $2^n = O(3^n)$.
- **Explanation**:
	- As $2^n$ grows slower than $3^n$, it falls within the $O(3^n)$ notation.
#### 4. Can $f(n) = 3n^2 + 2n + 1$ be expressed in $O(n)$ notation?

- **Answer**: No, $f(n) = 3n^2 + 2n + 1$ cannot be expressed in $O(n)$ notation.
- **Explanation**:
	- Since $f(n)$ grows faster than linear time, it is more suitably expressed in $O(n^2)$ notation.
#### 5. Determine if $n^2 + 3n + 1$ is in $\Theta(n^2)$ notation.

- **Answer**: Yes, $n^2 + 3n + 1$ is in $\Theta(n^2)$ notation.
- **Explanation**:
	- As $n^2 + 3n + 1$ grows at most quadratically with respect to $n$, it belongs to $\Theta(n^2)$.
#### 6. Analyze if 
$$a) \ h(n) + k(n) = \Theta(\max(h(n), k(n)))$$
$$b) \ h(n) + k(n) = \Theta(\min(h(n), k(n)))$$
- **Answer**:
   - a) True. 
     - **Explanation**:
	     - The sum $h(n) + k(n)$ is bounded both above and below by the maximum of $h(n)$ and $k(n)$, confirming $\Theta(\max(h(n), k(n)))$.
   - b) False.
     - **Explanation**: 
	     - A counterexample disproves the statement: $h(n) + k(n) = \Theta(\min(h(n), k(n)))$ because the sum of $h(n)$ and $k(n)$ may not be bounded by the minimum of $h(n)$ and $k(n)$.
#### 7. Write the Big-$\Theta$ expression to describe the number of operations required for the given algorithm:

```python
z = 0;
for (w = 0; w < K; w++) 
    for (x = 0; x < N; x++) 
        z = z + x;
    end 
    for (y = 0; y < M; y++) 
        z = z + y;
    end 
end
```

- **Answer**: 
	- The Big Theta expression is $\Theta(KN + KM)$.
- **Explanation**:
	- The algorithm consists of nested loops with iterations $K$, $N$, and $M$, leading to a total of $KN + KM$ operations, which is a tight bound represented by $\Theta$.