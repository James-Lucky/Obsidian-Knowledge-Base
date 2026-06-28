## 1. Function Naming — Verbs & Consistency

- **Use verbs**: Functions represent actions, so name them accordingly
    - ❌ `product()`, `freshProduct()`
    - ✅ `fetchProduct()`, `createProduct()`
- **Stay consistent**: Pick one verb per concept and use it everywhere
    - ❌ `fetchUser()` in one file, `getUser()` in another
    - ✅ Choose one — `getUser()` or `fetchUser()` — and never mix

---

## 2. Limit Parameters

- **Target**: Max 2–3 parameters per function
- **The risk of too many**: Argument swapping causes silent data corruption
    - e.g., accidentally swapping `category` and `image` in a 5-param call
- **Fix**: Pass a single object instead of individual variables

js

```js
// ❌ Fragile
createProduct(name, price, category, image, stock)

// ✅ Clean
createProduct({ name, price, category, image, stock })
```

---

## 3. Return Early — Avoid the Pyramid of Doom

- **The mistake**: Deeply nested `if-else` chains that bury the actual logic
- **The fix**: Check for _failure conditions first_, return immediately, keep the happy path at the bottom — flat and readable

js

```js
// ❌ Nested hell
function process(user) {
  if (user) {
    if (user.active) {
      if (user.verified) {
        // actual logic
      }
    }
  }
}

// ✅ Early returns
function process(user) {
  if (!user) return;
  if (!user.active) return;
  if (!user.verified) return;
  // actual logic
}
```

---

## 4. Avoid Boolean Flags

- **The mistake**: Passing `true`/`false` to toggle behavior — the call site tells you _nothing_
    - `registerUser(user, true)` — what does `true` mean here?
- **The fix**: Use named constants or enums — self-documenting at the call site

js

```js
// ❌ Cryptic
registerUser(user, true)

// ✅ Self-documenting
const shouldReturnToken = true
registerUser(user, shouldReturnToken)
```

---

## 5. Single Level of Abstraction

- **Rule**: One function = one thing at one level of complexity
- **The mistake**: A controller that validates, hashes, queries the DB, and sends a response — all inline
- **The fix**: Extract each responsibility into its own function; the parent only _coordinates_

js

```js
// ❌ God function
async function registerUser(req, res) {
  // validate input inline
  // hash password inline
  // insert into DB inline
  // send response inline
}

// ✅ Coordinated abstraction
async function registerUser(req, res) {
  validateUser(req.body)
  const user = await userService.create(req.body)
  res.send(user)
}
```

---

## Bonus: Function Names Should Tell Stories

A good name makes the code read like documentation.

|❌ Vague|✅ Descriptive|
|---|---|
|`handleData()`|`filterActiveUsers()`|
|`process()`|`calculateMonthlyRevenue()`|
|`doStuff()`|`sendPasswordResetEmail()`|

# Clean Coding Principles

## 1. Keep Code Simple

Write code in a clear and readable format. Avoid writing everything in one line.

Example:

```
if (ans == "yes") {
  // do task 1
} else if (ans == "maybe") {
  // do task 2
} else {
  // do task 3
}
```

Guidelines:

- [ ] Prefer readability over clever tricks
- [ ] Avoid complex one-line logic
- [ ] Break complex logic into steps

---

## 2. Modular Functions (Single Responsibility)

Each function should do **one job only**.

Example:

```
function helper(arr) {
  // calculate average
}

function modular(arr) {
  // input array
  helper(arr)
  // return result
}
```

Guidelines:

- [ ] One function = one responsibility
- [ ] Small reusable functions
- [ ] Avoid large multi-purpose functions

---

## 3. Meaningful Names

Use names that explain the purpose of variables and functions.

Example:

```
int age = 25
float price = 100
string name = "James Lucky"

function sum(a, b) {
  return a + b
}
```

Guidelines:

- [ ] Use descriptive variable names
- [ ] Avoid single letter variables (except loops)
- [ ] Functions should describe their action

Good examples:

```
totalPrice
userAge
calculateAverage()
getUserData()
```

---

## 4. Use Comments (Moderately)

Comments should explain **why**, not just what.

Examples:

```
TODO: create a button
FIXME: solve bug later
```

Guidelines:

- [ ] Use comments to explain complex logic
- [ ] Avoid obvious comments
- [ ] Mark tasks and bugs clearly

---

## 5. DRY Principle (Don't Repeat Yourself)

Avoid repeating the same logic.

Example:

```
const PI = 3.14

function area(radius) {
  return PI * radius * radius
}

function circumference(radius) {
  return 2 * PI * radius
}
```

Guidelines:

- [ ] Extract reusable constants
- [ ] Reuse functions
- [ ] Avoid duplicate code

---

## 6. Proper Indentation

Consistent spacing improves readability.

Example:

```
function example() {
  if (condition) {
    doSomething()
  }
}
```

Guidelines:

- [ ] Use consistent spacing
- [ ] Keep nested code aligned
- [ ] Avoid messy formatting

---

## 7. Use Consistent Naming Styles

Different naming conventions are used in programming.

### Camel Case (common in JS, Java, C++)

```
fullName
totalSum
getAverage()
```

### Snake Case (common in Python)

```
full_name
total_sum
get_average()
```

### Pascal Case (used for classes)

```
FullName
TotalSum
GetAverage()
```

### Kebab Case (used in URLs and HTML)

```
full-name
total-sum
get-average
```