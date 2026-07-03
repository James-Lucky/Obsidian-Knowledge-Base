![[Screenshot 2026-06-30 161205.png]]

Here are detailed notes based on Shradha Ma'am's DSA lecture on **Time and Space Complexity**:

**Video Link:** [https://www.youtube.com/watch?v=PwKv8fOcriM](https://www.youtube.com/watch?v=PwKv8fOcriM)

### **1. Introduction to Time & Space Complexity**

- **What is Time Complexity?** [[03:21](http://www.youtube.com/watch?v=PwKv8fOcriM&t=201)] It is **not** the exact execution time (like 0.05 seconds) because execution time varies depending on the machine, operating system, and server load. Instead, it is the amount of time an algorithm takes to run _as a function of its input size ($n$)_. It measures how the number of operations grows as the input grows.
    
- **What is Space Complexity?** [[16:17](http://www.youtube.com/watch?v=PwKv8fOcriM&t=977)] It is the amount of extra memory an algorithm takes as a function of the input size. We primarily care about **Auxiliary Space** (the extra space we allocate, like new variables or temporary arrays), rather than the space taken by the initial input data itself.
    

### **2. Big O Notation (Worst-Case Scenario)**

- **Why Worst Case?** [[09:16](http://www.youtube.com/watch?v=PwKv8fOcriM&t=556)] We calculate complexity for the worst-case scenario (the upper bound) because it prepares us for when the algorithm performs its absolute worst, ensuring our systems don't crash under heavy loads.
    
- **Other Notations:** [[14:32](http://www.youtube.com/watch?v=PwKv8fOcriM&t=872)] While Big O ($O$) represents the worst-case/upper bound, Theta ($\Theta$) represents the average case, and Omega ($\Omega$) represents the best-case/lower bound. For interviews and coding platforms, Big O is the absolute standard.
    
- **How to Calculate Big O:** [[12:25](http://www.youtube.com/watch?v=PwKv8fOcriM&t=745)]
    
    1. **Ignore Constants:** Drop mathematical numbers ($O(2n)$ becomes $O(n)$).
        
    2. **Take the Largest Term:** In an equation like $O(n^2 + n + 1)$, $n^2$ grows the fastest for large inputs, so you drop the smaller terms and the complexity becomes $O(n^2)$.
        

### **3. Common Time Complexities (Best to Worst)**

- **$O(1)$ - Constant Time:** [[24:30](http://www.youtube.com/watch?v=PwKv8fOcriM&t=1470)] The number of operations stays exactly the same no matter how large the input gets.
    
    - _Examples:_ Math formulas (e.g., $n(n+1)/2$), accessing an array element via its index, operations in HashMaps/Sets.
        
- **$O(\log n)$ - Logarithmic Time:** [[34:42](http://www.youtube.com/watch?v=PwKv8fOcriM&t=2082)] Very highly optimized. The search space gets divided in half at every step.
    
    - _Examples:_ Binary Search, Binary Search Trees (BST).
        
- **$O(n)$ - Linear Time:** [[26:39](http://www.youtube.com/watch?v=PwKv8fOcriM&t=1599)] The number of operations grows directly in proportion to the input size.
    
    - _Examples:_ Traversing an array, calculating a factorial using a simple loop, Kadane’s algorithm.
        
- **$O(n \log n)$ - Linearithmic Time:** [[39:39](http://www.youtube.com/watch?v=PwKv8fOcriM&t=2379)] Better than quadratic but slower than linear.
    
    - _Examples:_ Optimized sorting algorithms (Merge Sort, Quick Sort's average case), Greedy algorithms.
        
- **$O(n^2)$ - Quadratic Time:** [[29:11](http://www.youtube.com/watch?v=PwKv8fOcriM&t=1751)] Typically happens when there is a loop nested inside another loop, and both run $n$ times.
    
    - _Examples:_ Bubble Sort, Selection Sort, Insertion Sort, printing 2D patterns.
        
- **$O(n^3)$ - Cubic Time:** [[33:58](http://www.youtube.com/watch?v=PwKv8fOcriM&t=2038)] Three nested loops.
    
    - _Examples:_ Printing all possible sub-arrays of an array (brute force).
        
- **$O(2^n)$ - Exponential Time:** [[40:45](http://www.youtube.com/watch?v=PwKv8fOcriM&t=2445)] Terrible performance, generally signaling an unoptimized brute-force approach.
    
    - _Examples:_ Standard recursive Fibonacci without Dynamic Programming.
        
- **$O(n!)$ - Factorial Time:** [[41:31](http://www.youtube.com/watch?v=PwKv8fOcriM&t=2491)] Even worse than exponential.
    
    - _Examples:_ N-Queens problem (brute force), finding all permutations of a string.
        

### **4. Complexity in Recursion**

Calculating complexity in recursive code is usually done by finding the **Total Number of Calls $\times$ Work Done in Each Call**. Space complexity mostly depends on the maximum depth of the **Call Stack** [[56:04](http://www.youtube.com/watch?v=PwKv8fOcriM&t=3364)].

- **Recursive Factorial:** [[54:39](http://www.youtube.com/watch?v=PwKv8fOcriM&t=3279)]
    
    - _Time:_ Makes roughly $n$ calls, with each call doing $O(1)$ constant work $\rightarrow$ **$O(n)$** Time.
        
    - _Space:_ The recursion tree goes $n$ levels deep, occupying $n$ frames in the call stack $\rightarrow$ **$O(n)$** Space.
        
- **Recursive Fibonacci:** [[01:00:11](http://www.youtube.com/watch?v=PwKv8fOcriM&t=3611)]
    
    - _Time:_ Every call spawns 2 more calls. The calls grow exponentially ($1, 2, 4, 8...$), leading to roughly $2^n$ total calls. $\rightarrow$ **$O(2^n)$** Time.
        
    - _Space:_ The maximum depth of the call stack at any point is $n$ $\rightarrow$ **$O(n)$** Space.
        
- **Merge Sort:** [[01:10:19](http://www.youtube.com/watch?v=PwKv8fOcriM&t=4219)]
    
    - _Time:_ The array is recursively split in half, resulting in a tree depth of $\log n$. At every level, $O(n)$ work is done to merge the arrays together $\rightarrow$ **$O(n \log n)$** Time.
        
    - _Space:_ Requires a temporary array for merging ($O(n)$) and takes up $O(\log n)$ call stack space $\rightarrow$ **$O(n)$** Space.
        

### **5. Practical Usage in Competitive Programming**

[[01:16:46](http://www.youtube.com/watch?v=PwKv8fOcriM&t=4606)] In platforms like LeetCode or Codeforces, execution time is generally capped at **1 second**. Modern servers can perform roughly **$10^8$ operations per second**. You can use the provided input size ($n$) limits to guess the expected time complexity and avoid "Time Limit Exceeded" (TLE) errors:

- If $n \le 10^8$: Expected complexity is **$O(n)$** or **$O(\log n)$**.
    
- If $n \le 10^6$: Expected complexity is **$O(n \log n)$** (Hint: Usually involves sorting).
    
- If $n \le 10^4$: Expected complexity is **$O(n^2)$** (Nested loops are okay).
    
- If $n \le 500$: Expected complexity is **$O(n^3)$**.
    
- If $n \le 25$: Expected complexity is **$O(2^n)$** (Hint: Think recursion).
    
- If $n \le 12$: Expected complexity is **$O(n!)$**.