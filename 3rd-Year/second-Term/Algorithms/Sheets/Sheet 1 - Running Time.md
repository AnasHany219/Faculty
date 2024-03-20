
## A) Rank the following time complexities:
### Time Complexity Questions:

1. **Ranking Time Complexities:**
   - **Question:** Rank the following time complexities from slowest to fastest growth. $O(1), \ O(\log n), \ O(n), \ O(n\log n), \ O(n^2)$
   - **Answer:** Slowest to fastest growth: $O(1)$, $O(\log n)$, $O(n)$, $O(n\log n)$, $O(n^2)$.

2. **Ascending Order of Growth Rates:**
   - **Question:** Arrange the following time complexities in ascending order of growth rates. $O(\log n), \ O(n^2), \ O(2^n), \ O(n!), \ O(n)$
   - **Answer:** Ascending order of growth rates: $O(\log n)$, $O(n)$, $O(n^2)$, $O(n^2)$, $O(n!)$.

3. **Comparing Growth Rates:**
   - **Question:** Compare the time complexities of $O(\log n)$ and $O(n^2)$ in terms of growth rate.
   - **Answer:** $O(\log n)$ grows slower than $O(n^2)$.

4. **Comparing Growth Rates II:**
   - **Question:** Which has a faster growth rate: $O(n\log n)$ or $O(n^3)$?
   - **Answer:** $O(n^3)$ has a faster growth rate than $O(n\log n)$.

5. **Arranging Time Complexities:**
   - **Question:** Arrange the following time complexities in ascending order. $O(n^3), \ O(n^{2.5}), \ O(n^{2.1}), \ O(n^2 \log n)$
   - **Answer:** Ascending order: $O(n^2 \log n)$, $O(n^{2.1})$, $O(n^{2.5})$, $O(n^3)$.

6. **Comparing Growth Rates III:**
   - **Question:** Compare the growth rates of $O(2^n)$ and $O(n!)$.
   - **Answer:** $O(n!)$ grows faster than $O(2^n)$.

7. **Arranging Time Complexities II:**
   - **Question:** Arrange the following time complexities in ascending order. $O(n^{\frac{1}{2}}), \ O(n^3), \ O(n\log n), \ O(2^n)$
   - **Answer:** Ascending order: $O(n^{\frac{1}{2}})$, $O(n\log n)$, $O(n^3)$, $O(2^n)$.

8. **Comparing Growth Rates IV:**
   - **Question:** Which has a slower growth rate: $O(\log n)$ or $O(n^{0.001})$?
   - **Answer:** $O(\log n)$ has a slower growth rate than $O(n^{0.001})$.

9. **Comparing Growth Rates V:**
   - **Question:** Compare the growth rates of $O(n^3)$ and $O(3^n)$.
   - **Answer:** $O(n^3)$ grows faster than $O(3^n)$.

10. **Arranging Time Complexities III:**
    - **Question:** Arrange the following time complexities in ascending order. $O(n^{\log n}), \ O(\log n!), \ O(n!), \ O(2^n)$
    - **Answer:** Ascending order: $O(\log n!)$, $O(n^{\log n})$, $O(2^n)$, $O(n!)$.

---
## B) Compute the Running Time for the Following Algorithms:
### Running Time Computations:

1. **For Loop Iterating Through an Array:**
   - **Algorithm:** 
     ```python
     for x in arr:
         print(x)
     ```
   - **Running Time:** $O(n)$ where $n$ is the length of the array.

2. **Nested For Loop Iterating Through a 2D Array:**
   - **Algorithm:** 
     ```python
     for x in range(n):
         for y in range(n):
             print(arr[x][y])
     ```
   - **Running Time:** $O(n^2)$ where $n$ is the size of the array.

3. **Single For Loop with Constant Operations Inside:**
   - **Algorithm:** 
     ```python
     for i in range(n):
         result = i * 2 + 3
         print(result)
     ```
   - **Running Time:** $O(n)$.

4. **Nested For Loop Iterating Through a 2D Array (Partial Upper Triangular Matrix):**
   - **Algorithm:** 
     ```python
     for i=1:n:
         for j=i:n:
             print arr[i,j]
     ```
   - **Running Time:** $O(n^2)$ where $n$ is the size of the array.

5. **For Loop with a Conditional Statement:**
   - **Algorithm:** 
     ```python
     for num in range(1, n+1):
         if num % 2 == 0:
             print("Even")
         else:
             print("Odd")
     ```
   - **Running Time:** $O(n)$.

6. **For Loop Iterating Through an Array with Constant Time Operations Inside:**
   - **Algorithm:** 
     ```python
     sum = 0
     for element in arr:
         sum = sum + element
     ```
   - **Running Time:** $O(n)$.

7. **For Loop Finding the Maximum Element in an Array:**
   - **Algorithm:** 
     ```python
     max_element = arr[0]
     for element in arr:
         if element > max_element:
             max_element = element
     ```
   - **Running Time:** $O(n)$.

8. **Nested For Loop Multiplying Two Matrices:**
   - **Algorithm:** 
     ```python
     result = []
     for i in range(n):
         row = []
         for j in range(n):
             value = 0
             for k in range(n):
                 value = value + (matrix1[i][k] * matrix2[k][j])
             row.append(value)
         result.append(row)
     ```
   - **Running Time:** $O(n^3)$.

9. **For Loop Calculating the Factorial of $n$:**
   - **Algorithm:** 
     ```python
     result = 1
     for i in range(1, n+1):
         result = result * i
     ```
   - **Running Time:** $O(n)$.

10. **For Loop Calculating Fibonacci Series:**
    - **Algorithm:** 
      ```python
      fib = [0, 1]
      for i in range(2, n):
          fib.append(fib[i - 1] + fib[i - 2])
      ```
    - **Running Time:** $O(n)$.