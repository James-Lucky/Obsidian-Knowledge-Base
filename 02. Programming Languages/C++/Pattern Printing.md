---
tags:
  - cpp
  - pattern
  - loop
created: 2026-07-15
---
## 1. Square Pattern (Numbers)

### Output (`n = 4`)

```
1 2 3 4
1 2 3 4
1 2 3 4
1 2 3 4
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 4;

    for (int i = 1; i <= n; i++) {      // Outer loop (rows)
        for (int j = 1; j <= n; j++) {  // Inner loop (columns)
            cout << j << " ";
        }
        cout << endl;
    }

    return 0;
}
```

### Learning

The outer loop controls the number of rows, while the inner loop controls what is printed inside each row. Since `j` starts from `1` and goes to `n`, every row prints the same sequence.

Pattern printing is mainly about understanding the relationship between rows (`i`) and columns (`j`). Most DSA patterns can be solved by asking: "What should I print at position `(i, j)`?"

---

## 2. Square Pattern (Stars)

### Output (`n = 5`)

```
****
****
****
****
****
```

> Note: Your code uses `j < n`, so it prints 4 stars.

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 5;

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j < n; j++) {
            cout << "*";
        }
        cout << endl;
    }

    return 0;
}
```

### Learning

Replacing numbers with stars doesn't change the loop logic. Only the `cout` statement changes. This demonstrates that loops define the structure, while the printed value defines the pattern.

Whenever debugging patterns, first verify the loop conditions (`<`, `<=`). Small mistakes there are the most common source of incorrect outputs.

---

## 3. Character Square Pattern

### Output (`n = 4`)

```
ABCD
ABCD
ABCD
ABCD
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 4;

    for (int i = 0; i < n; i++) {
        char ch = 'A';

        for (int j = 0; j < n; j++) {
            cout << ch;
            ch++;
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

Characters are stored internally as ASCII values. `'A'` is 65, `'B'` is 66, and so on. Incrementing a character variable automatically moves to the next character.

Resetting `ch = 'A'` inside the outer loop causes every row to begin with `A`. If you move `char ch = 'A';` outside the outer loop, the sequence will continue across rows.

---

## 4. Continuous Number Pattern

### Output

```
123
456
789
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 3;
    int num = 1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            cout << num;
            num++;
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

Unlike previous patterns, the variable `num` is declared outside both loops. Therefore, it keeps increasing throughout the entire program instead of resetting after each row.

A useful rule: if you want values to continue, declare variables outside the loops. If you want values to restart every row, declare them inside the outer loop.

---

## 5. Continuous Character Pattern

### Output

```
ABC
DEF
GHI
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 3;
    char ch = 'A';

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            cout << ch;
            ch++;
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

This pattern follows the same logic as the continuous number pattern. Since `ch` is declared outside the loops, it continues increasing from one row to the next.

Understanding variable scope is critical in C++. Pattern questions often test whether you know when a variable should reset and when it should persist.

---

## 6. Star Pyramid

### Output (`n = 5`)

```
*
**
***
****
*****
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 5;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i + 1; j++) {
            cout << "*";
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

The number of stars depends on the row number. Row `0` prints `1` star, row `1` prints `2` stars, and so on. This is why the condition becomes `j < i + 1`.

Many triangle and pyramid problems use `i + 1`, `n - i`, or `2*i + 1`. Memorizing these relationships makes advanced patterns much easier.

---

## 7. Number Pyramid

### Output (`n = 4`)

```
1
2 2
3 3 3
4 4 4 4
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 4;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i + 1; j++) {
            cout << (i + 1) << " ";
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

The outer loop variable `i` determines both the number being printed and the number of times it appears. This demonstrates that one variable can control multiple aspects of a pattern.

When solving pattern questions, identify whether the output depends on the row number (`i`) or column number (`j`). That single observation usually solves the problem.

---

## 8. Increasing Number Triangle

### Output (`n = 4`)

```
0
0 1
0 1 2
0 1 2 3
```

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 4;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j <= i; j++) {
            cout << j << " ";
        }

        cout << endl;
    }

    return 0;
}
```

### Learning

This pattern is entirely controlled by the inner loop variable `j`. Each row prints numbers starting from `0` up to the current row index.

Pattern problems become significantly easier if you write down the `(row, column)` values on paper before coding. Most beginners try to code first and think later, which leads to confusion.

---
## 1. Reverse Number Triangle

### Output (`n=4`)

```
1
2 1
3 2 1
4 3 2 1
```

### Dry Run

|Row (i)|Elements|
|---|---|
|0|1|
|1|2 1|
|2|3 2 1|
|3|4 3 2 1|

### Logic

```
Rows = n
Columns = i+1
Print = j (decreasing)
```

### Code

```
for (int i=0; i<n; i++) {
    for (int j=i+1; j>0; j--) {
        cout << j << " ";
    }
    cout << endl;
}
```

---

## 2. Floyd's Triangle

### Output

```
1
2 3
4 5 6
7 8 9 10
```

### Dry Run

```
Row 0 -> 1
Row 1 -> 2 3
Row 2 -> 4 5 6
Row 3 -> 7 8 9 10
```

### Logic

```
Rows = n
Columns = i+1
Print = num
num++
```

### Code

```
int num = 1;

for (int i=0; i<n; i++) {
    for (int j=0; j<=i; j++) {
        cout << num << " ";
        num++;
    }
    cout << endl;
}
```

---

## 3. Character Floyd's Triangle

### Output

```
A
BC
DEF
GHIJ
```

### Logic

```
Rows = n
Columns = i+1
Print = ch
ch++
```

### Code

```
char ch='A';

for (int i=0; i<n; i++) {
    for (int j=0; j<=i; j++) {
        cout << ch;
        ch++;
    }

    cout << endl;
}
```

---

## 4. Inverted Number Triangle

### Output

```
1111
222
33
4
```

### Dry Run

|i|n-i|
|---|---|
|0|4|
|1|3|
|2|2|
|3|1|

### Logic

```
Rows = n
Columns = n-i
Print = i+1
```

### Code

```
for (int i=0; i<n; i++) {

    for (int j=0; j<n-i; j++) {
        cout << i+1;
    }

    cout << endl;
}
```

> Tumhare code me `for(int j=0; j<1; j++)` hai. Ye useless loop hai. Sirf ek space print kar raha hai. Hata do.

---

## 5. Inverted Character Triangle

### Output

```
ABCD
EFG
HI
J
```

### Logic

```
Rows = n
Columns = n-i
Print = ch
ch++
```

### Code

```
char ch='A';

for (int i=0; i<n; i++) {

    for (int j=0; j<n-i; j++) {
        cout << ch;
        ch++;
    }

    cout << endl;
}
```

---

## Pyramid Problems 

She uses this formula:

```
1. Spaces
2. Left Numbers
3. Right Numbers
```

Example:

```
   1
  121
 12321
1234321
```

### Step 1: Spaces

```
for(int j=0; j<n-i-1; j++)
    cout<<" ";
```

|Row|Spaces|
|---|---|
|0|3|
|1|2|
|2|1|
|3|0|

Formula:

```
n-i-1
```

---

### Step 2: Increasing Numbers

```
for(int j=1; j<=i+1; j++)
    cout<<j;
```

Output:

```
1
12
123
1234
```

---

### Step 3: Decreasing Numbers

```
for(int j=i; j>=1; j--)
    cout<<j;
```

Output:

```
(empty)
1
21
321
```

---

### Final Output

```
   1
  121
 12321
1234321
```

### Complete Code

```
int n = 4;
for (int i=0; i<n; i++) {
    // Spaces
    for (int j=0; j<n-i-1; j++) {
        cout << " ";
    }

    // Increasing
    for (int j=1; j<=i+1; j++) {
        cout << j;
    }

    // Decreasing
    for (int j=i; j>=1; j--) {
        cout << j;
    }

    cout << endl;
}
```

---
#  Hollow diamond pattern 
### Output (`n = 4`)

```
   *
  * *
 *   *
*     *
 *   *
  * *
   *
```

---

### Pattern Breakdown

#### Top Half

```
1. Left Spaces = n-i-1
2. First Star
3. Middle Spaces = 2*i-1
4. Second Star (except first row)
```

|Row (i)|Left Spaces|Middle Spaces|
|---|---|---|
|0|3|X|
|1|2|1|
|2|1|3|
|3|0|5|

---

#### Bottom Half

```
1. Left Spaces = i+1
2. First Star
3. Middle Spaces = 2*(n-i)-5
4. Second Star (except last row)
```

|Row (i)|Left Spaces|Middle Spaces|
|---|---|---|
|0|1|3|
|1|2|1|
|2|3|X|

---

### Formula

```
Top:
Spaces = n-i-1
Middle = 2*i-1

Bottom:
Spaces = i+1
Middle = 2*(n-i)-5
```

---

### Code

```
#include <iostream>
using namespace std;

int main() {
    int n = 4;

    // TOP
    for (int i=0; i<n; i++) {

        for (int j=0; j<n-i-1; j++)
            cout << " ";

        cout << "*";

        if (i != 0) {

            for (int j=0; j<2*i-1; j++)
                cout << " ";

            cout << "*";
        }

        cout << endl;
    }

    // BOTTOM
    for (int i=0; i<n-1; i++) {

        for (int j=0; j<i+1; j++)
            cout << " ";

        cout << "*";

        if (i != n-2) {

            for (int j=0; j<2*(n-i)-5; j++)
                cout << " ";

            cout << "*";
        }

        cout << endl;
    }
}
```

---

### Learning

A hollow pattern is simply a normal pattern where the inside is replaced by spaces. Instead of printing all stars, you print only the boundary stars.

Whenever you see a diamond, immediately split it into two problems: Top Triangle and Bottom Triangle.

---

 Butterfly Pattern

### Output (`n = 4`)

```
*      *
**    **
***  ***
********
********
***  ***
**    **
*      *
```

---

### Pattern Breakdown

The butterfly consists of 4 parts on every row:

```
1. Left Stars
2. Middle Spaces
3. Right Stars
4. Top + Bottom
```

---

## Top Half

### Formula

```
Left Stars  = i+1
Middle Space = 2*(n-i)-2
Right Stars = i+1
```

|i|Left Stars|Spaces|Right Stars|
|---|---|---|---|
|0|1|6|1|
|1|2|4|2|
|2|3|2|3|
|3|4|0|4|

---

## Bottom Half

### Formula

```
Left Stars = n-i-1
Spaces = 2*i+2
Right Stars = n-i-1
```

|i|Left Stars|Spaces|Right Stars|
|---|---|---|---|
|0|3|2|3|
|1|2|4|2|
|2|1|6|1|

---

### Visual Representation

```
*      *
^^      ^^

Left     Right
Stars    Stars
```

---

### Code

```
#include <iostream>
using namespace std;

int main() {

    int n = 4;

    // TOP
    for (int i=0; i<n; i++) {

        // Left Stars
        for (int j=0; j<i+1; j++)
            cout << "*";

        // Spaces
        for (int j=0; j<2*(n-i)-2; j++)
            cout << " ";

        // Right Stars
        for (int j=0; j<i+1; j++)
            cout << "*";

        cout << endl;
    }

    // BOTTOM
    for (int i=0; i<n-1; i++) {

        // Left Stars
        for (int j=0; j<n-i-1; j++)
            cout << "*";

        // Spaces
        for (int j=0; j<2*i+2; j++)
            cout << " ";

        // Right Stars
        for (int j=0; j<n-i-1; j++)
            cout << "*";

        cout << endl;
    }

    return 0;
}
```

---

### Dry Run

```
Row 0: *      *
Row 1: **    **
Row 2: ***  ***
Row 3: ********
```

Observe:

- Stars increase by 1.
- Spaces decrease by 2.
- Then the pattern mirrors itself.

---

### Learning

Butterfly patterns are combinations of two mirrored triangles. The left and right sides always behave the same, while the middle spaces change.

A useful approach for complex patterns is:

```
1. Split vertically.
2. Split horizontally.
3. Find formulas.
4. Combine.
```

---

## Pattern Cheat Sheet

|Pattern|Formula|
|---|---|
|Triangle|`i+1`|
|Reverse Triangle|`n-i`|
|Pyramid Spaces|`n-i-1`|
|Hollow Middle|`2*i-1`|
|Butterfly Spaces|`2*(n-i)-2`|
|Diamond Bottom|`2*(n-i)-5`|
---

### Golden Rule for Every Pattern

Whenever you see a new pattern, write:

```
Rows?
Columns?
What to print?
```

Example:

```
****
***
**
*

Rows = n
Columns = n-i
Print = *
```

Example:

```
1
12
123
1234

Rows = n
Columns = i+1
Print = j
```
---

## Key Takeaways

1. Outer Loop = Number of Rows.
2. Inner Loop = Number of Columns/Elements.
3. Variables inside the outer loop reset every row.
4. Variables outside both loops continue across rows.
5. Always determine whether the output depends on:
    - `i` (row)
    - `j` (column)
    - `n` (size)
    - A separate variable (`num`, `ch`)

> Formula to solve patterns:
> 
> - Step 1: Count rows.
> - Step 2: Determine columns for each row.
> - Step 3: Decide what to print at `(i, j)`.
> - Step 4: Code the loops.
> - Step 5: Dry run with `n = 3` before compiling.