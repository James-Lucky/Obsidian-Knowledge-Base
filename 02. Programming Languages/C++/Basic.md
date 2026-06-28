### 1. `Basic Syntax`

```
#include <iostream>
using namespace std;

int main() {
    cout << "Type Your Number : " << endl;
    return 0;
}
```

### 2. `Basic Calculator`

`#include <iostream>`
`using namespace std;`

`int main() {`
    `int x, y;`
    `int sum;`

    ```cout << "Type Your Number : " << endl;```
    ```cin >> x;```

    ```cout << "Type Another Number" << endl;```
    ```cin >> y;```

    ```sum = x + y;```
    ```cout << "Sum is \t" << sum;```

    ```return 0;```
`}`

## 3. `Arithmetic Operators`

`#include <iostream>`
`using namespace std;`

`int main() {`
    `int x, y;`

    ``cout << "Type Your Number : " << endl;``
    ``cin >> x;``

    ``cout << "Type Another Number" << endl;``
    ``cin >> y;``

    ``cout << "Sum is \t" << (x + y);``

    ``return 0;``
`}`

## `4. Print the Last Character of a String`

`#include <iostream>`
`#include <string>`
`using namespace std;`

`int main() {`
    `string myString = "Hello";`
    `cout << myString[myString.length() - 1];`
    `return 0;`
`}`


### `## 5. Change String Characters`

`#include <iostream>`
`#include <string>`
`using namespace std;`

`int main() {`
    `string myString = "Hello";`
    `myString[0] = 'J';`
    `cout << myString;`
    `return 0;`
`}`


### `6. `at()` Function in String`

`#include <iostream>`
`#include <string>`
`using namespace std;`

`int main() {`
    `string myString = "Hello";`

    `cout << myString.at(0);`
    `cout << myString.at(1);`
    `cout << myString.at(myString.length() - 1);`

    `myString.at(0) = 'J';`
    `cout << myString;`

    `return 0;`
`}`

### `7. `## Change an Array Element

`string cars[4] = {"Volvo", "BMW", "Ford", "Mazda"};`  
`cars[0] = "Opel";`  
`cout << cars[0];`


### `7. `## The foreach Loop
## 
### Syntax

```
for (_type variableName_ : _arrayName_) {  
  // code block to be executed  
}

Example:

// Create an array of integers  
int myNumbers[5] = {10, 20, 30, 40, 50};  
  
// Loop through integers  
for (int num : myNumbers) {  
  cout << num << "\n";  
}
```


### Example

