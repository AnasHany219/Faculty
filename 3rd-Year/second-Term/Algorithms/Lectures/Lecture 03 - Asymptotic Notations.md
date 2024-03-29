- A way to describe the behavior of functions as the input size grows to infinity. 📈
	- Indicate the running time of an algorithm. ⏱️
	- Describe the running time of the algorithm as 𝑛 grows to ∞.
	- ![[Asymptotic Notations.png]] 
## Different asymptotic notations are used to represent the complexity of the algorithm
### **Big Omega** ($\Omega$) - Notation

    - Best case or lower bound; you can't achieve better than it. 🔒
    - Because of the best case:

$$ f(n) \ge c_2 .g(n), \quad n \ge n_0 \qquad \rightarrow \qquad \text{Where } c_2 \gt 0, \quad n_0 \ge 1 $$
	![[Big-Omega.png | width=200]]
###  **Big Theta** ($\Theta$) - Notation  
    - Average case or tight bound, when the best case and worst case are the same. 🎯
    - Because of the average case:    

$$ c_2.g(n) \le f(n) \le c_1.g(n), \quad \Omega \le \Theta \le O \qquad \rightarrow \qquad \text{Where } c_1, c_2 \gt 0 \text{ for all } n \ge n_0 \gt 1 $$
	![[Big-Theta.png | width=200]]
### **Big Oh** ($O$) - Notation
    - Worst case time and upper bound; your time won't exceed it. ⏰
    - Because of the worst case:    

$$ f(n) \le c_1 .g(n), \quad n \ge n_0 \qquad \rightarrow \qquad \text{Where } c_1 \gt 0, \quad n_0 \ge 1 $$
	![[o-notation.png| width=200]]
	