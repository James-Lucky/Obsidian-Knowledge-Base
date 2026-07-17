
| Term                       | Meaning                                                          | Example                                                            |
| -------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Literal**                | A fixed value written directly in code.                          | `int age = 21;` → `21` is a literal.                               |
| **Redundancy**             | Unnecessary repetition in code.                                  | Writing the same logic multiple times instead of using a function. |
| **Variable**               | A named storage location that can change its value.              | `int count = 10;`                                                  |
| **Constant**               | A value that cannot be changed after initialization.             | `const double PI = 3.14159;`                                       |
| **Identifier**             | The name given to variables, functions, classes, etc.            | `studentName`, `calculateSum()`                                    |
| **Keyword**                | Reserved words in a programming language.                        | `if`, `while`, `return`, `class`                                   |
| **Expression**             | A combination of values and operators that produces a result.    | `a + b * 2`                                                        |
| **Statement**              | A complete instruction in a program.                             | `cout << "Hello";`                                                 |
| **Syntax**                 | Rules for writing code correctly.                                | Missing `;` causes a syntax error in C++.                          |
| **Semantics**              | The meaning or behavior of code.                                 | Code may have correct syntax but incorrect logic.                  |
| **Compilation**            | Converting source code into machine code.                        | `g++ main.cpp -o app`                                              |
| **Runtime**                | The period when a program is executing.                          | Division by zero causes a runtime error.                           |
| **Debugging**              | Finding and fixing errors in code.                               | Using breakpoints in VS Code.                                      |
| **Refactoring**            | Improving code without changing its behavior.                    | Replacing duplicate code with a function.                          |
| **Optimization**           | Making code faster or use less memory.                           | Using Binary Search instead of Linear Search.                      |
| **Scalability**            | Ability of a system to handle growth.                            | A website serving 100 users vs. 1 million users.                   |
| **Abstraction**            | Hiding unnecessary details and showing only essentials.          | Using `car.start()` without knowing the engine's internals.        |
| **Encapsulation**          | Wrapping data and methods into a single unit.                    | A class containing private data members.                           |
| **Inheritance**            | Creating a new class from an existing one.                       | `class Dog : public Animal`                                        |
| **Polymorphism**           | One interface, multiple implementations.                         | Function overriding in C++.                                        |
| **Coupling**               | Degree of dependency between modules.                            | High coupling makes code difficult to maintain.                    |
| **Cohesion**               | How closely related the responsibilities of a module are.        | A `UserService` handling only user-related tasks.                  |
| **Technical Debt**         | Future problems caused by quick or poor decisions.               | Hardcoding values to meet a deadline.                              |
| **Boilerplate Code**       | Repetitive code required by a framework or language.             | Setting up an Express server repeatedly.                           |
| **Code Smell**             | Signs that code may need improvement.                            | Very long functions or excessive nesting.                          |
| **Dead Code**              | Code that is never executed.                                     | An unused function in a project.                                   |
| **Magic Number**           | Hardcoded numbers without explanation.                           | `if(score > 42)` instead of `const PASS_MARK = 42;`                |
| **Memory Leak**            | Memory that is allocated but never released.                     | Forgetting `delete` in C++.                                        |
| **Immutable**              | Cannot be changed after creation.                                | Strings in Java are immutable.                                     |
| **Mutable**                | Can be changed after creation.                                   | Arrays in JavaScript are mutable.                                  |
| **Thread Safe**            | Safe to use by multiple threads simultaneously.                  | Mutex-protected code.                                              |
| **Race Condition**         | Multiple threads accessing shared data unexpectedly.             | Two threads updating a bank balance at once.                       |
| **Deadlock**               | Two or more processes waiting forever on each other.             | Thread A waits for B; B waits for A.                               |
| **Latency**                | Time taken to complete an operation.                             | API response time of 100 ms.                                       |
| **Throughput**             | Amount of work completed in a given time.                        | Server handling 10,000 requests per second.                        |
| **Fault Tolerance**        | Ability to continue operating after failures.                    | Cloud servers with automatic failover.                             |
| **Idempotent**             | Produces the same result no matter how many times it's executed. | `GET /users` API requests.                                         |
| **API**                    | A way for software systems to communicate.                       | React app calling a Node.js backend.                               |
| **Middleware**             | Code executed between request and response.                      | Authentication middleware in Express.js.                           |
| **Authentication**         | Verifying who a user is.                                         | Login with email and password.                                     |
| **Authorization**          | Checking what a user is allowed to do.                           | Admin can delete users; regular users cannot.                      |
| **Caching**                | Storing frequently used data for faster access.                  | Browser cache.                                                     |
| **Database Normalization** | Organizing database tables efficiently.                          | Separating users and orders into different tables.                 |
| **Big O Notation**         | Measures algorithm efficiency.                                   | Binary Search = `O(log n)`.                                        |
| **Recursion**              | A function calling itself.                                       | Calculating factorial.                                             |
| **Memoization**            | Storing previous results to avoid recomputation.                 | Dynamic Programming problems.                                      |

### The Two Terms You Asked About

1. **Literal**
    - A value directly written in code.
    - Examples:
        
        ```
        int x = 100;      // 100 is an integer literal
        char c = 'A';     // 'A' is a character literal
        string s = "Hi";  // "Hi" is a string literal
        ```
        
2. **Redundancy**
    - Unnecessary duplication of code or data.
    - Bad:
        
        ```
        cout << "Hello";
        cout << "Hello";
        cout << "Hello";
        ```
        
    - Better:
        
        ```
        for(int i = 0; i < 3; i++) {
            cout << "Hello";
        }
        ```
        
    - Redundancy makes code harder to maintain and increases the chances of bugs.