## 1. Naming Rules

### Folder Names

Never use:

```
MyProject/UserData/BackendAPI/
```

Use:

```
my-project/user-data/backend-api/
```

Reason:

- cleaner URLs
- better consistency
- avoids Linux/server issues
- industry standard

---

### File Names

Bad:

```
UserProfile.jsxFinalCode.jsAuthController.js
```

Better:

```
user-profile.jsxfinal-code.jsauth-controller.js
```

For React components specifically:

```
UserProfile.jsxNavbar.jsx
```

PascalCase is acceptable because components are classes/functions.

---

### Variable Names

Bad:

```
let d;let dataa;let finalFinalData;
```

Good:

```
let user;let filteredUsers;let totalPrice;
```

Names should explain purpose instantly.

---

### Function Names

Bad:

```
doStuff()handle()data()
```

Good:

```
fetchUserData()calculateTotalPrice()validateEmail()
```

Functions should sound like actions.

---

# 2. Project Structure Rules

## Never Dump Everything Together

Bad:

```
src/  app.js  auth.js  db.js  api.js  user.js  payment.js  helper.js  final.js
```

Better:

```
src/├── components/├── pages/├── services/├── utils/├── hooks/├── lib/├── middleware/├── config/└── types/
```

---

# 3. Code Rules

## Never Write Huge Functions

Bad:

```
function processOrder() {  // 300 lines}
```

Good:

```
validateOrder()calculatePrice()saveOrder()sendEmail()
```

Small functions are easier to:

- debug
- reuse
- test
- maintain

---

##  Avoid Deep Nesting

Bad:

```
if (user) {  if (user.isActive) {    if (user.isAdmin) {      // code    }  }}
```

Better:

```
if (!user) return;if (!user.isActive) return;if (!user.isAdmin) return;// code
```

Use early returns.

---

##  Never Hardcode Values

Bad:

```
if (user.role === "admin123")
```

Better:

```
const ADMIN_ROLE = "admin";if (user.role === ADMIN_ROLE)
```

---

##  Never Repeat Logic

Bad:

```
const tax1 = price * 0.18;const tax2 = amount * 0.18;
```

Better:

```
function calculateTax(amount) {  return amount * TAX_RATE;}
```

---

# 4. Git Rules

## Never Commit Random Messages

Bad:

```
git commit -m "fix"git commit -m "done"git commit -m "final final"
```

Good:

```
git commit -m "fix authentication middleware"git commit -m "add user profile validation"git commit -m "optimize database queries"
```

---

## Never Push Broken Code

Before push:

```
npm run lintnpm run buildnpm test
```

---

# 5. Debugging Rules

## Never Guess Bugs

Bad programmer:

```
"Maybe this works..."
```

Good programmer:

```
"Where exactly is the failure happening?"
```

---

## Read Error Messages Completely

Most beginners:

- panic
- skip error
- search random solution

Instead:

1. read exact line
2. identify root cause
3. reproduce issue
4. isolate issue

---

# 6. Learning Rules

## Never Learn Passively

Bad:

- watching tutorials for 6 hours

Good:

- build while learning
- break code intentionally
- modify examples
- experiment

---

## Never Copy-Paste Blindly

If you copy code:

- explain every line
- know why it exists
- know what breaks if removed

Otherwise you are not learning.

---

# 7. Architecture Rules

## Separate Concerns

Bad:

```
route -> database query -> validation -> email -> payment
```

Better:

```
routes/services/controllers/repositories/utils/
```

---

## Keep Business Logic Out of UI

Bad:

```
<button onClick={() => complexPaymentLogic()}>
```

Better:

```
handlePayment()
```

Move logic outside UI.

---

# 8. Database Rules

## Never Use SELECT *

Bad:

```
SELECT * FROM users;
```

Better:

```
SELECT id, username, email FROM users;
```

---

## Always Index Important Fields

Example:

- email
- userId
- createdAt

Without indexes:  
large apps become slow.

---

# 9. Security Rules

## Never Trust User Input

Always validate:

- forms
- APIs
- query params
- file uploads

---

## Never Store Plain Passwords

Use:

```
bcryptargon2
```

Never:

```
password: "123456"
```

---

# 10. Frontend Rules

## Never Overuse State

Bad:

```
50 useState hooks
```

Better:

- group related state
- use reducers when needed
- keep state minimal

---

## Avoid Massive Components

Bad:

```
Dashboard.jsx → 2000 lines
```

Better:

```
dashboard/├── sidebar.jsx├── analytics.jsx├── chart-card.jsx└── table.jsx
```

---

# 11. Backend Rules

## Never Put Everything in Controllers

Bad:

```
controller = validation + db + logic + response
```

Better:

```
controller → service → repository
```

---

# 12. Real Developer Mindset

## Think in Systems

Ask:

- why does this work?
- where does data flow?
- what can fail?
- what scales badly?
- what is bottleneck?

---

## Optimize After Correctness

First:

```
Make it work
```

Then:

```
Make it clean
```

Then:

```
Make it fast
```

Not reverse.