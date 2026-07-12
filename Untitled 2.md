---
title: 6 Prompts to Hack-Proof Your AI/Vibe-Coded App
tags:
  - security
  - web-development
  - ai
  - backend
  - checklist
created: 2026-07-12
---

# 6 Prompts to Hack-Proof Your AI/Vibe-Coded App

> Most AI-generated applications fail because they ignore basic security practices.
> Before shipping, run these checks.

---

# 1. Rate Limiting

## Goal
Prevent brute-force attacks, API abuse, spam, and denial-of-service attempts.

## Checklist

- Apply different rate limits based on endpoint sensitivity.
- Use stricter limits for:
  - Login
  - Signup
  - Password Reset
  - OTP Verification
- Use moderate limits for:
  - Public APIs
  - Search
  - Read-only endpoints
- Allow higher limits for authenticated users.
- Combine:
  - Per-IP limits
  - Per-user/account limits
- Use exponential backoff instead of permanent lockouts.
- Keep thresholds configurable.

## Example

❌ Everyone: 100 requests/minute

✅ Better

Login:
- 5 attempts / 15 minutes

Search:
- 60 requests/minute

Authenticated Dashboard:
- 300 requests/minute

---

# 2. Input Validation

## Goal

Reject bad data before it reaches your application.

Never trust:

- Forms
- Query parameters
- URL params
- Cookies
- Headers
- JSON bodies
- AI-generated content

## Validate

- Data type
- Length
- Format
- Range
- Required fields
- Allowed values

## Use Schema Validation

Examples:

- Zod
- Joi
- Yup
- Valibot
- Pydantic

## Example

Email

✅ user@example.com

❌ user@@example

Age

✅ 18

❌ "eighteen"

Username

✅ Lucky_07

❌ ../../etc/passwd

---

# 3. File Upload Safety

## Goal

Prevent malicious file uploads.

## Validate

- File type
- MIME type
- File size
- File content

Don't trust file extensions alone.

Example

❌ malware.exe renamed to image.png

Always inspect MIME/content.

## Store uploads

Avoid:

```
public/uploads/
```

Prefer:

- Object storage
- Private bucket
- Separate upload server

Examples

- S3
- Cloudflare R2
- Supabase Storage

## Never

- Execute uploaded files
- Store executable scripts inside public folders

## Extra

- Virus scan uploads
- Rename files
- Generate unique IDs
- Strip metadata if needed

---

# 4. Secrets

## Goal

Ensure no credentials are exposed.

## Never expose

- API Keys
- JWT Secrets
- Database URLs
- AWS Keys
- OAuth Secrets
- Firebase Admin Keys
- Stripe Secret Keys
- OpenAI API Keys

## Store

Use environment variables.

Example

```
.env
```

Never commit:

```
.env
```

Use

```
.env.example
```

## Before pushing

Run secret scanners.

Examples

- GitHub Secret Scanning
- Gitleaks
- TruffleHog

---

# 5. Dependency Vulnerabilities

## Goal

Keep third-party packages secure.

## Audit

- npm
- pnpm
- yarn
- pip
- cargo
- composer

## Check

- Known CVEs
- High severity issues
- Deprecated packages
- Abandoned libraries

## Commands

Node

```bash
npm audit
npm audit fix
```

PNPM

```bash
pnpm audit
```

Python

```bash
pip-audit
```

Rust

```bash
cargo audit
```

## Before updating

- Read release notes
- Check breaking changes
- Test application

---

# 6. Error Handling & Information Leakage

## Goal

Don't reveal internal implementation details.

Never expose

- Stack traces
- SQL errors
- File paths
- Server versions
- Database schema
- Environment variables

Bad

```
SQLSTATE[23000]
Database: production
```

Good

```
Something went wrong.
Please try again later.
```

## Log internally

Log

- Full stack trace
- Request ID
- User ID
- Timestamp
- Endpoint
- Exception

Show users

- Generic messages
- Friendly errors

---

# Security Checklist Before Deployment

## Authentication

- [ ] Strong password policy
- [ ] Rate limiting
- [ ] MFA supported
- [ ] Session expiration

## API

- [ ] Input validation
- [ ] Authentication
- [ ] Authorization
- [ ] CORS configured
- [ ] CSRF protection
- [ ] HTTPS enforced

## Database

- [ ] Parameterized queries
- [ ] ORM protection
- [ ] Least privilege accounts
- [ ] Regular backups

## File Uploads

- [ ] File type validation
- [ ] Size limits
- [ ] Virus scanning
- [ ] Private storage

## Secrets

- [ ] No secrets in Git
- [ ] Environment variables
- [ ] Secret scanning enabled

## Dependencies

- [ ] Audit completed
- [ ] Vulnerabilities fixed
- [ ] Unused packages removed

## Errors

- [ ] Generic user errors
- [ ] Internal logging
- [ ] No stack traces exposed

## Infrastructure

- [ ] HTTPS
- [ ] Security headers
- [ ] WAF (optional)
- [ ] Monitoring
- [ ] Backups
- [ ] Logging

---

# Useful Security Tools

## Node.js

- Helmet
- Express Rate Limit
- Zod
- Prisma
- npm audit

## Next.js

- Middleware
- Server Actions
- Route Handlers
- next-safe

## Testing

- OWASP ZAP
- Burp Suite Community
- Postman
- Bruno
- Insomnia

---

# Remember

Security is not a feature you add at the end.

It is a process that should be part of every development stage:

Design → Build → Test → Deploy → Monitor

---
title: Frontend Performance & Browser Rendering
tags:
  - frontend
  - performance
  - browser
  - web
  - optimization
  - rendering
created: 2026-07-12
---

# Frontend Performance & Browser Rendering

## Topics

- Browser Rendering Pipeline
- Critical Rendering Path (CRP)
- Reflow (Layout)
- Image Priority (`fetchpriority="high"`)

---

# Browser Rendering Pipeline

## What is it?

The Browser Rendering Pipeline is the sequence of steps a browser follows to convert HTML, CSS, and JavaScript into pixels displayed on the screen.

```
Request
    ↓
HTML Download
    ↓
Parse HTML
    ↓
DOM Tree
    ↓
Download CSS
    ↓
CSSOM Tree
    ↓
Render Tree
    ↓
Layout (Reflow)
    ↓
Paint
    ↓
Compositing
    ↓
Screen
```

---

## Step 1 — HTML Parsing

The browser downloads HTML.

Example

```html
<html>
<body>
<h1>Hello</h1>
</body>
</html>
```

The browser converts it into the **DOM (Document Object Model)**.

```
Document
 └── html
      └── body
            └── h1
```

---

## Step 2 — CSS Parsing

CSS files are downloaded.

```css
h1{
 color:red;
}
```

The browser creates a

**CSSOM (CSS Object Model)**

---

## Step 3 — Render Tree

Browser combines

- DOM
- CSSOM

into

```
Render Tree
```

Only visible elements are included.

Example

```html
<div>Hello</div>
<div style="display:none">
Hidden
</div>
```

Only

```
Hello
```

is added to the Render Tree.

---

## Step 4 — Layout (Reflow)

Browser calculates

- Position
- Width
- Height
- Margin
- Padding

Example

```
Header

Main

Footer
```

Every element gets coordinates.

---

## Step 5 — Paint

Browser paints

- Colors
- Borders
- Backgrounds
- Shadows
- Text

---

## Step 6 — Compositing

Layers are merged by the GPU.

GPU-friendly properties

- transform
- opacity
- filter

These don't trigger layout.

---

# Critical Rendering Path (CRP)

## Definition

The Critical Rendering Path is the minimum work required before the browser can display the first visible content.

Goal:

```
Fast First Paint
```

---

## CRP Flow

```
HTML
 ↓
DOM

CSS
 ↓
CSSOM

DOM + CSSOM
 ↓
Render Tree
 ↓
Layout
 ↓
Paint
```

---

## Why It Matters

A shorter CRP means

- Faster page load
- Better Largest Contentful Paint (LCP)
- Better Core Web Vitals
- Better Lighthouse Score
- Improved SEO
- Better User Experience

---

## How to Optimize the CRP

### Minify CSS

Remove whitespace and comments.

---

### Inline Critical CSS

Load only above-the-fold CSS first.

Example

```html
<style>
header{
background:black;
}
</style>
```

---

### Defer JavaScript

```html
<script defer src="app.js"></script>
```

or

```html
<script async src="analytics.js"></script>
```

---

### Remove Unused CSS

Example tools

- PurgeCSS
- Tailwind JIT
- Lightning CSS

---

### Lazy Load Images

```html
<img loading="lazy">
```

---

### Preload Important Assets

```html
<link
rel="preload"
href="/fonts/font.woff2"
as="font">
```

---

# Reflow (Layout)

## Definition

Reflow happens when the browser recalculates the layout because an element's size or position changes.

Reflow is one of the most expensive browser operations.

---

## Triggers of Reflow

Changing

- width
- height
- padding
- margin
- font-size
- display
- position
- content
- window resize

Example

```javascript
box.style.width="300px";
```

Browser recalculates layout.

---

## Expensive Example

```javascript
for(let i=0;i<1000;i++){
element.style.width=i+"px";
}
```

This can trigger many layouts.

---

## Better

```javascript
element.classList.add("large");
```

One layout update.

---

## Avoid Layout Thrashing

Bad

```javascript
element.style.width="200px";

console.log(element.offsetWidth);

element.style.height="300px";
```

Reading layout after writing forces synchronous reflow.

---

## Batch DOM Updates

Bad

```
Read
Write
Read
Write
Read
Write
```

Good

```
Read
Read
Read

Write
Write
Write
```

---

## Prefer GPU Properties

Instead of

```css
left
top
width
height
```

Use

```css
transform
opacity
```

Example

```css
transform:translateX(100px);
```

Much faster.

---

# Image Priority (`fetchpriority="high"`)

## What is it?

The `fetchpriority` attribute tells the browser how important a resource is during loading.

```html
<img
src="hero.jpg"
fetchpriority="high"
alt="Hero">
```

Browser downloads this image before less important images.

---

## Benefits

- Faster Hero Image
- Better Largest Contentful Paint (LCP)
- Better Core Web Vitals
- Better Lighthouse Performance Score
- Improved Perceived Load Speed

---

## When to Use

Use for

- Hero banner
- Landing page image
- Main product image
- Largest Contentful Paint element
- Above-the-fold content

---

## Avoid Using On

- Every image
- Icons
- Avatars
- Footer images
- Gallery thumbnails
- Lazy-loaded images

If everything is high priority, nothing is prioritized.

---

## Example

### Hero Image

```html
<img
src="/hero.webp"
fetchpriority="high"
width="1200"
height="700"
alt="Hero">
```

### Normal Image

```html
<img
src="/gallery1.webp"
loading="lazy"
alt="">
```

---

# Related Image Loading Attributes

### Lazy Loading

```html
<img loading="lazy">
```

Loads only when near the viewport.

---

### Eager Loading

```html
<img loading="eager">
```

Loads immediately.

---

### Async Decoding

```html
<img decoding="async">
```

Allows asynchronous image decoding to reduce blocking.

---

# Performance Checklist

## HTML

- [ ] Semantic HTML
- [ ] Minified HTML
- [ ] Remove unused elements

---

## CSS

- [ ] Minified CSS
- [ ] Inline critical CSS
- [ ] Remove unused CSS
- [ ] Avoid expensive selectors

---

## JavaScript

- [ ] Use `defer` where appropriate
- [ ] Use `async` for independent scripts
- [ ] Split bundles
- [ ] Remove unused libraries

---

## Images

- [ ] Use WebP or AVIF
- [ ] Set `width` and `height`
- [ ] Compress images
- [ ] Use `loading="lazy"` for non-critical images
- [ ] Use `fetchpriority="high"` only for the primary above-the-fold image

---

## Rendering

- [ ] Reduce reflows
- [ ] Batch DOM updates
- [ ] Prefer `transform` and `opacity` for animations
- [ ] Minimize layout shifts (CLS)

---

# Key Takeaways

- The browser renders pages through: **DOM → CSSOM → Render Tree → Layout → Paint → Composite**.
- The **Critical Rendering Path** determines how quickly users see the first content.
- **Reflows** are expensive; avoid unnecessary layout recalculations.
- Use **`fetchpriority="high"`** only for the most important image (typically the LCP/hero image).
- Optimize HTML, CSS, JavaScript, and images together for the biggest performance improvements.