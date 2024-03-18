## Definitions
- **What is an Algorithm?** 🤔  
  It is a series of steps to solve a problem. 🛠️  
- **What is a program?** 💻  
  It is an algorithm implemented in a programming language. 🚀  

## Algorithm Analysis
**Before algorithm**: Write code to solve a problem 📝  
**After algorithm**: Write `EFFICIENT` code to solve problem to Save resources, Save time, Save money 💰⏳  

### Analysis & Design of Algorithms
#### Analysis
- Statements, Conditions & Loops 🔄  
- Recursion 🔄  
#### Design
- Divide & Conquer 🗡️  
- Dynamic Programming 🔄  
- Greedy Method 💡  

## The Running Time
- It is the number of steps executed. ⏱️  
### Consecutive Statements
```cpp
int main(){
  // 1. some code with running time n
  // 2. some code with running time n^2
  return 0;
}
```
- The total running time is $𝑇(𝑛) = 𝑛 + 𝑛^2$
/break
### For Loop
```cpp
for(int i = 0; i < n; i++){
  // body
}
```
- If the loop iterates `n` times and the body requires `m` operations to run, the total number of operations is $𝑛 × 𝑚 = 𝑛𝑚$.  

### Nested For Loop
```cpp
for(int i = 0; i < n; i++){
  for(int j = 0; j < n; j++){
    // body with running time n
  }
}
```
- There are` two for loops`, each iterating `n` times. So the total cost is $𝑇(𝑛) = 𝑛×𝑛×𝑛 =𝑛^3$

### While Loops
```cpp
while (i > 0){
  // running time n
  i = i / 2;
}
```
 * While loops are usually harder to analyze than for loops.

**How many times the loop repeats?**  
* In every iteration, the value of i gets halved. **In each iteration, it does the work. Therefore the total cost is** $𝑇(𝑛) = n \log_2{i}$

[[Lecture 02 - Running time]]