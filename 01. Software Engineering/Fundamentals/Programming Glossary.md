  
## 1. CSR (Client-Side Rendering)  
  
**Definition**  
A rendering technique where JavaScript running in the browser generates the HTML and UI after the page loads.  
  
### Advantages  
- Rich interactivity  
- Less server workload  
- Smooth navigation after initial load  
  
### Disadvantages  
- Slower first page load  
- Poorer SEO compared to SSR  
  
---  
  
## 2. SSR (Server-Side Rendering)  
  
**Definition**  
A rendering technique where the server generates the HTML for every request before sending it to the browser.  
  
### Advantages  
- Faster initial page load  
- Better SEO  
- Good for dynamic content  
  
### Disadvantages  
- Higher server load  
  
---  
  
## 3. SSG (Static Site Generation)  
  
**Definition**  
Pages are generated during build time and served as static HTML files.  
  
**Examples**  
- Documentation websites  
- Blogs  
- Portfolio websites  
  
---  
  
## 4. ISR (Incremental Static Regeneration)  
  
**Definition**  
Allows static pages to be regenerated individually after deployment without rebuilding the entire website.  
  
---  
  
## 5. API (Application Programming Interface)  
  
**Definition**  
A set of rules and protocols that allows different software applications to communicate with each other.  
  
> [!example]  
> Weather API, GitHub API, Stripe API## HTML Generation  
  
| Rendering Strategy | HTML Generated On |  
|--------------------|------------------|  
| CSR | Client |  
| SSR | Server |  
| SSG | Build Time |  
| ISR | Static pages updated after deployment |  
  
---  
  
## CSR  
  
- HTML generated in the browser.  
- JavaScript builds the UI after loading.  
  
**Flow**  
  
```text  
Browser  
↓  
Download JS  
↓  
Generate HTML  
↓  
Render UI  
```  
  
---  
  
## SSR  
  
- HTML generated on the server.  
- Generated for every request.  
  
**Flow**  
  
```text  
Request  
↓  
Server generates HTML  
↓  
Browser receives HTML  
↓  
Hydration  
```  
  
---  
  
## SSG  
  
- HTML generated during build time.  
- Served as static files.  
  
Best for:  
  
- Blogs  
- Portfolio  
- Documentation  
- Marketing websites  
  
---  
  
## ISR  
  
- Static pages are regenerated after deployment.  
- Updates only affected pages.  
- No need to rebuild the whole website.  
  
Best for:  
  
- E-commerce  
- News sites  
- CMS-based websites
  
  ## Rendering Strategies  
  
### 1. CSR (Client-Side Rendering)  
  
**Definition**  
  
Client-Side Rendering is a rendering technique where the HTML content and UI are generated inside the user's browser using JavaScript.  
  
### Process  
  
```text  
Request  
↓  
Server sends minimal HTML + JS  
↓  
Browser downloads JavaScript  
↓  
JavaScript generates UI  
↓  
Page becomes interactive  
```  
  
### Pros  
  
- Rich user experience  
- Fast page transitions  
- Suitable for dashboards and SPAs  
  
### Cons  
  
- Slower first load  
- Poor SEO without optimization  
- Requires JavaScript  
  
---  
  
### 2. SSR (Server-Side Rendering)  
  
**Definition**  
  
Server-Side Rendering generates the HTML on the server for every request and sends the fully rendered page to the client.  
  
### Process  
  
```text  
Request  
↓  
Server generates HTML  
↓  
HTML sent to browser  
↓  
Browser displays page  
↓  
JavaScript hydrates the page  
```  
  
### Pros  
  
- Better SEO  
- Faster initial page load  
- Good for dynamic content  
  
### Cons  
  
- More server load  
- Slower response for every request  
  
---  
  
### 3. SSG (Static Site Generation)  
  
**Definition**  
  
Static Site Generation creates HTML pages during the build process.  
  
### Process  
  
```text  
Build Time  
↓  
Generate HTML  
↓  
Deploy  
↓  
Serve static files  
```  
  
### Pros  
  
- Extremely fast  
- Excellent SEO  
- Low hosting cost  
  
### Cons  
  
- Requires rebuilding after content changes  
  
---  
  
### 4. ISR (Incremental Static Regeneration)  
  
**Definition**  
  
ISR updates static pages after deployment without rebuilding the entire website.  
  
### Advantages  
  
- Static performance  
- Fresh content  
- No full rebuild required  
  
---  
  
# Build Process  
  
```text  
Source Code  
↓  
Build  
↓  
Server  
↓  
Client (Browser)  
```  
  
---  
  
## Comparison  
  
| Strategy | HTML Generated On               | Best For                   |     |
| -------- | ------------------------------- | -------------------------- | --- |
| CSR      | Client Browser                  | Dashboards, SPAs           |     |
| SSR      | Server                          | Dynamic websites, SEO      |     |
| SSG      | Build Time                      | Blogs, Documentation       |     |
| ISR      | Build + Background Regeneration | Frequently updated content |     |
# Programming Glossary  
  
## 1. API (Application Programming Interface)  
  
A set of rules, protocols, and tools that allow different software applications to communicate with each other.  
  
**Example:** REST API, GraphQL API.  
  
---  
  
## 2. Algorithm  
  
A finite sequence of well-defined steps used to solve a specific problem.  
  
---  
  
## 3. Argument  
  
A value passed to a function when it is called.  
  
```javascript  
greet("Lucky") // "Lucky" is an argument  
```  
  
---  
  
## 4. CI (Continuous Integration)  
  
A development practice where code changes from multiple developers are automatically integrated, tested, and validated.  
  
---  
  
## 5. CLI (Command Line Interface)  
  
A text-based interface used to interact with the operating system through commands.  
  
**Examples**  
  
- Terminal (Linux/macOS)  
- CMD (Windows)  
- PowerShell  
  
---  
  
## 6. Compile Time  
  
The phase in which source code is translated into machine code before execution.  
  
---  
  
## 7. Constant  
  
A value that cannot be changed during program execution.  
  
```javascript  
const PI = 3.14159;  
```  
  
---  
  
## 8. Declaration  
  
The process of defining a variable, function, or object.  
  
```javascript  
let age;  
```  
  
---  
  
## 9. Expression  
  
A combination of values, variables, operators, and function calls that evaluates to a value.  
  
```javascript  
5 + 10  
sum(a, b)  
```  
  
---  
  
## 10. Framework  
  
A collection of tools, libraries, and conventions that simplify application development.  
  
**Examples**  
  
- React  
- Angular  
- Django  
- Spring Boot  
  
---  
  
## 11. Iteration  
  
The repeated execution of a block of code using loops.  
  
```javascript  
for (...) {}  
while (...) {}  
```  
  
---  
  
## 12. Keyword  
  
A reserved word in a programming language with a predefined meaning.  
  
**Examples**  
  
- if  
- else  
- return  
- class  
- function  
  
---  
  
## 13. Low-Level Language  
  
A programming language that is close to machine hardware.  
  
**Examples**  
  
- Assembly Language  
- Machine Code  
  
---  
  
## 14. Object  
  
An instance containing **data (properties)** and **behavior (methods)**.  
  
```javascript  
const user = {  
name: "Lucky",  
greet() {}  
};  
```  
  
---  
  
## 15. Parameter  
  
A variable defined in a function declaration that receives an argument.  
  
```javascript  
function greet(name) {  
// name is a parameter  
}  
```  
  
---  
  
## 16. Pointer  
  
A variable that stores the memory address of another variable.  
  
> Mainly used in C and C++.  
  
---  
  
## 17. Reference  
  
A value that refers to another object in memory instead of storing the object itself.  
  
---  
  
## 18. Runtime  
  
The period during which a program is executing.  
  
---  
  
## 19. Statement  
  
A complete instruction that performs an action.  
  
```javascript  
let x = 10;  
```  
  
---  
  
## 20. Syntax  
  
The grammatical rules of a programming language.  
  
Incorrect syntax results in syntax errors.  
  
---  
  
## 21. Bug  
  
An error or flaw in a program that causes incorrect behavior.  
  
---  
  
## 22. Bit  
  
The smallest unit of digital information.  
  
Possible values:  
  
- 0  
- 1  
  
---  
  
## 23. Byte  
  
A unit of digital storage equal to **8 bits**.  
  
---  
  
## 24. ASCII  
  
**American Standard Code for Information Interchange**  
  
A character encoding standard that represents text using 7-bit (or extended 8-bit) codes.  
  
---  
  
## 25. Data Structure  
  
A method of organizing and storing data efficiently.  
  
Examples:  
  
- Array  
- Linked List  
- Stack  
- Queue  
- Tree  
- Graph  
  
---  
  
## 26. Array  
  
A linear data structure that stores elements of the same data type in contiguous memory.  
  
---  
  
## 27. Cookie  
  
A small file stored by a website in the user's browser to remember information.  
  
Uses:  
  
- Login sessions  
- User preferences  
- Tracking  
  
---  
  
## 28. Cache  
  
Temporary storage that keeps frequently accessed data for faster retrieval.  
  
---  
  
## 29. Debugger  
  
A software tool used to identify, inspect, and fix program errors.  
  
---  
  
## 30. IDE (Integrated Development Environment)  
  
Software that provides tools for writing, debugging, testing, and running code.  
  
Examples:  
  
- VS Code  
- IntelliJ IDEA  
- PyCharm  
- Visual Studio  
  
---  
  
## 31. Open Source  
  
Software whose source code is publicly available for anyone to inspect, modify, and distribute.  
  
Examples:  
  
- Linux  
- React  
- Node.js  
  
---  
  
## 32. Pair Programming  
  
A software development technique where two programmers work together on the same code.  
  
Roles:  
  
- Driver  
- Navigator  
  
---  
  
## 33. Subroutine  
  
A reusable block of code designed to perform a specific task.  
  
Also called:  
  
- Function  
- Method  
- Procedure  
  
---  
  
## 34. Web Crawler  
  
An automated program that systematically visits and indexes web pages.  
  
Examples:  
  
- Googlebot  
- Bingbot  
  
---  
  
## 35. Exception Handling  
  
A mechanism used to detect and handle runtime errors gracefully.  
  
```javascript  
try {  
// code  
} catch (error) {  
// handle error  
}  
```  
  
---  
  
## 36. CLI (Command Line Interface)  
  
A text-based interface used to interact with programs, files, and the operating system.  
  
---  
  
## 37. JSON (JavaScript Object Notation)  
  
A lightweight data-interchange format used to exchange structured information.  
  
Example:  
  
```json  
{  
"name": "Lucky",  
"age": 22  
}  
```  
  
---  
  
## 38. MVC (Model-View-Controller)  
  
A software architecture pattern that separates an application into three components:  
  
- **Model** → Data  
- **View** → User Interface  
- **Controller** → Business Logic  
  
---  
  
## 39. Unit Testing  
  
Testing the smallest independent piece of code, usually a function or method.  
  
---  
  
## 40. Pseudocode  
  
An informal way of writing algorithms using plain English instead of programming syntax.  
  
Example:  
  
```text  
Start  
Read input  
If number is even  
Print "Even"  
Else  
Print "Odd"  
End  
```  
  
---  
  
## 41. Thread  
  
The smallest unit of execution within a process.  
  
Multiple threads allow concurrent execution of tasks.  
  
---  
  
## 42. Race Condition  
  
A situation where multiple threads or processes access shared data simultaneously, causing unpredictable results.  
  
---  
  
# Quick Revision Table  
  
| Term | One-line Meaning |  
|-------|------------------|  
| API | Communication interface between software |  
| Algorithm | Step-by-step solution |  
| Argument | Value passed to a function |  
| Parameter | Variable in function definition |  
| CLI | Text-based interface |  
| CI | Automatic code integration |  
| Runtime | Program execution time |  
| Compile Time | Source code translation phase |  
| Framework | Platform for application development |  
| Object | Data + methods |  
| Pointer | Stores memory address |  
| Reference | Points to an object in memory |  
| Array | Sequential collection of elements |  
| Cache | Fast temporary storage |  
| Cookie | Browser-stored website data |  
| IDE | Programming environment |  
| Debugger | Tool for finding bugs |  
| JSON | Data exchange format |  
| MVC | Model-View-Controller architecture |  
| Unit Test | Testing a single unit of code |  
| Thread | Independent execution path |  
| Race Condition | Concurrent access conflict |  
| Pseudocode | Human-readable algorithm |
