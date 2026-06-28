# Authentication

> Verifying a user's identity — ensuring they are who they claim to be. When you log in, the system checks if your credentials match a record in the database.

---

## 1. Basic Authentication

The simplest and oldest form. Client sends username + password (Base64 encoded) with **every request**.

```
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
```

**Problems:**

- Password sent on every request
- No logout mechanism
- Insecure without HTTPS

---

## 2. Session-Based Authentication

**Flow:**

1. User logs in → server validates credentials
2. Server creates a session → stores user info `{ sessionId: abc123, userId: 45 }`
3. Server sends `sessionId` to browser via cookie
4. Every request → browser sends cookie → server looks up session

**Key Points:**

- Session stored on **server**, cookie stored on **client**
- Easy to invalidate (just delete the session)
- Can scale with **Redis**

|||
|---|---|
|✅ Pros|Secure with HTTPS, simple to manage|
|❌ Cons|Server memory cost, harder horizontal scaling|

---

## 3. JWT (JSON Web Token) Authentication

**Flow:**

1. User logs in → server validates credentials
2. Server creates a signed JWT:

```json
{
  "userId": "45",
  "email": "user@example.com",
  "role": "admin"
}
```

3. Token signed with a **secret key**
4. Client stores token (localStorage or HTTP-only cookie)
5. Client sends token with each request:

```
Authorization: Bearer <token>
```

6. Server verifies signature → grants access

|||
|---|---|
|✅ Pros|Stateless, no session storage, ideal for APIs & microservices|
|❌ Cons|Hard to revoke, secret key must be protected, XSS risk if in localStorage|

---

## Summary

|Type|Storage|Stateless|Common Use|
|---|---|---|---|
|Basic Auth|Client credentials|❌|Internal APIs|
|Session Auth|Server + cookies|❌|Traditional web apps|
|JWT Auth|Client-side token|✅|SPAs, APIs, mobile apps|

---

## In MERN Stack

- **React** → store JWT in **HTTP-only cookie** (not localStorage)
- **Express** → verify JWT via middleware on protected routes

```js
// Express middleware example
const verifyToken = (req, res, next) => {
  const token = req.headers.authorization?.split(' ')[1]
  if (!token) return res.status(401).json({ message: 'Unauthorized' })
  jwt.verify(token, process.env.JWT_SECRET, (err, decoded) => {
    if (err) return res.status(403).json({ message: 'Invalid token' })
    req.user = decoded
    next()
  })
}
```

---
