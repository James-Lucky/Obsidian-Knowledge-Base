## What is Bootstrap?

Bootstrap is a **mobile-first CSS framework** used to build responsive and modern websites quickly using prebuilt classes and components. It provides:

- Responsive Grid System
- Utility Classes
- Ready-made Components
- JavaScript Plugins
- Faster UI Development

Bootstrap 5 removed dependency on jQuery and uses vanilla JavaScript.

---

# Table of Contents

1. Introduction
2. Installation
3. Containers
4. Grid System
5. Breakpoints
6. Typography
7. Colors
8. Spacing Utilities
9. Flex Utilities
10. Buttons
11. Cards
12. Forms
13. Tables
14. Navbar
15. Alerts
16. Modals
17. Carousel
18. Utilities
19. Bootstrap Icons
20. Bootstrap JS Components
21. Customization
22. Best Practices
23. Interview Questions
24. Mini Project Structure

---

# 1. Introduction

## Features

- Mobile-first design
- Responsive grid system
- Flexbox-based layout
- Utility-first classes
- Reusable UI components
- Cross-browser support

---

# 2. Installation

## Using CDN

```
<!DOCTYPE html><html lang="en"><head>  <meta charset="UTF-8">  <meta name="viewport" content="width=device-width, initial-scale=1.0">  <!-- Bootstrap CSS -->  <link    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"    rel="stylesheet"  ></head><body>  <h1 class="text-center">Hello Bootstrap</h1>  <!-- Bootstrap JS -->  <script    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js">  </script></body></html>
```

Bootstrap provides both CSS and JS bundles. The bundle includes Popper.js.

---

# 3. Containers

Containers are layout wrappers.

## Types

|Class|Description|
|---|---|
|`.container`|Responsive fixed-width|
|`.container-fluid`|Full width|
|`.container-sm/md/lg/xl/xxl`|Responsive containers|

## Example

```
<div class="container">  Content</div><div class="container-fluid">  Full width content</div>
```

---

# 4. Grid System

Bootstrap uses a **12-column responsive flexbox grid**.

## Structure

```
<div class="container">  <div class="row">    <div class="col">      Column    </div>  </div></div>
```

---

## Equal Columns

```
<div class="row">  <div class="col">1</div>  <div class="col">2</div>  <div class="col">3</div></div>
```

---

## Fixed Columns

```
<div class="row">  <div class="col-4">4</div>  <div class="col-8">8</div></div>
```

---

## Responsive Columns

```
<div class="row">  <div class="col-md-6">Half</div>  <div class="col-md-6">Half</div></div>
```

Meaning:

- Full width below `md`
- Half width on `md+`

---

## Nested Grid

```
<div class="row">  <div class="col-6">    <div class="row">      <div class="col-6">Nested</div>      <div class="col-6">Nested</div>    </div>  </div></div>
```

---

# 5. Breakpoints

|Breakpoint|Class Prefix|Min Width|
|---|---|---|
|Extra Small|none|<576px|
|Small|`sm`|≥576px|
|Medium|`md`|≥768px|
|Large|`lg`|≥992px|
|Extra Large|`xl`|≥1200px|
|XXL|`xxl`|≥1400px|

---

# 6. Typography

## Headings

```
<h1>Heading</h1>
```

## Display Headings

```
<h1 class="display-1">Big Heading</h1>
```

---

## Text Alignment

```
<p class="text-center">Center</p><p class="text-end">Right</p>
```

---

## Font Weight

```
<p class="fw-bold">Bold</p><p class="fw-light">Light</p>
```

---

# 7. Colors

## Text Colors

```
<p class="text-primary">Primary</p><p class="text-danger">Danger</p>
```

---

## Background Colors

```
<div class="bg-success text-white">  Success</div>
```

---

## Common Color Classes

|Class|Color|
|---|---|
|`primary`|Blue|
|`secondary`|Gray|
|`success`|Green|
|`danger`|Red|
|`warning`|Yellow|
|`info`|Cyan|
|`dark`|Black|
|`light`|White|

---

# 8. Spacing Utilities

Bootstrap spacing uses:

```
m = marginp = padding
```

Sides:

```
t = topb = bottoms = starte = endx = horizontaly = vertical
```

Scale:

```
0 → 5
```

---

## Examples

```
<div class="mt-5">Margin top</div><div class="p-3">Padding</div><div class="mx-auto">Center horizontally</div>
```

Spacing utilities are one of Bootstrap’s core helper systems.

---

# 9. Flex Utilities

Bootstrap grid itself is based on Flexbox.

---

## Display Flex

```
<div class="d-flex">
```

---

## Justify Content

```
<div class="d-flex justify-content-between">
```

Options:

- start
- center
- end
- between
- around
- evenly

---

## Align Items

```
<div class="d-flex align-items-center">
```

---

## Flex Direction

```
<div class="d-flex flex-column">
```

---

# 10. Buttons

## Basic Buttons

```
<button class="btn btn-primary">  Click</button>
```

---

## Button Variants

```
btn-primarybtn-successbtn-dangerbtn-warningbtn-dark
```

---

## Outline Buttons

```
<button class="btn btn-outline-primary">
```

---

## Button Sizes

```
btn-lgbtn-sm
```

---

# 11. Cards

Cards are flexible content containers.

## Basic Card

```
<div class="card" style="width: 18rem;">  <img src="img.jpg" class="card-img-top">  <div class="card-body">    <h5 class="card-title">Title</h5>    <p class="card-text">      Content    </p>    <a href="#" class="btn btn-primary">      Go    </a>  </div></div>
```

---

# 12. Forms

Bootstrap provides styled forms and validation.

---

## Input

```
<input type="text" class="form-control">
```

---

## Label

```
<label class="form-label">  Email</label>
```

---

## Select

```
<select class="form-select">
```

---

## Checkbox

```
<input type="checkbox" class="form-check-input">
```

---

## Input Groups

```
<div class="input-group">  <span class="input-group-text">@</span>  <input type="text" class="form-control"></div>
```

---

# 13. Tables

Bootstrap tables are opt-in styled tables.

## Basic Table

```
<table class="table">
```

---

## Variants

```
table-stripedtable-hovertable-borderedtable-dark
```

---

## Example

```
<table class="table table-striped">
```

---

# 14. Navbar

## Basic Navbar

```
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">  <div class="container">    <a class="navbar-brand" href="#">      Brand    </a>  </div></nav>
```

---

## Navbar Expand

|Class|Behavior|
|---|---|
|`navbar-expand-sm`|Expand after small|
|`navbar-expand-md`|Expand after medium|
|`navbar-expand-lg`|Expand after large|

---

# 15. Alerts

```
<div class="alert alert-success">  Success message</div>
```

---

# 16. Modal

## Button

```
<button  class="btn btn-primary"  data-bs-toggle="modal"  data-bs-target="#exampleModal">  Open</button>
```

---

## Modal Structure

```
<div class="modal fade" id="exampleModal">  <div class="modal-dialog">    <div class="modal-content">      <div class="modal-header">        <h5>Title</h5>      </div>      <div class="modal-body">        Body      </div>    </div>  </div></div>
```

---

# 17. Carousel

```
<div id="carouselExample" class="carousel slide">
```

Used for:

- Image sliders
- Hero sections
- Testimonials

---

# 18. Utilities

Utilities are shortcut classes. Bootstrap 5 heavily relies on utilities.

---

## Display Utilities

```
d-noned-blockd-flex
```

---

## Visibility

```
visibleinvisible
```

---

## Borders

```
borderborder-0roundedrounded-circle
```

---

## Shadows

```
shadowshadow-lg
```

---

## Width & Height

```
w-100h-100
```

---

# 19. Bootstrap Icons

Bootstrap icons are separate.

## CDN

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css">
```

---

## Example

```
<i class="bi bi-alarm"></i>
```

---

# 20. Bootstrap JS Components

Require Bootstrap JS bundle.

## Components

|Component|Purpose|
|---|---|
|Modal|Popup|
|Collapse|Toggle content|
|Dropdown|Menus|
|Carousel|Sliders|
|Tooltip|Hover tips|
|Toast|Notifications|
|Offcanvas|Sidebar|

Bootstrap 5 JS no longer requires jQuery.

---

# 21. Customization

Bootstrap uses Sass variables and utility APIs.

---

## Customize Colors

```
$primary: #ff0000;
```

---

## Install via NPM

```
npm install bootstrap
```

---

## Import in React/Vite

```
import 'bootstrap/dist/css/bootstrap.min.css'
```

---

# 22. Best Practices

## DO

- Use grid properly
- Prefer utilities before custom CSS
- Keep responsive design in mind
- Use reusable components
- Combine Bootstrap with custom CSS

---

## DON'T

- Overwrite Bootstrap randomly
- Use too many nested rows
- Depend only on Bootstrap for design
- Ignore accessibility

---

# 23. Common Interview Questions

## Q1. Difference between container and container-fluid?

- `container` → fixed responsive width
- `container-fluid` → full width

---

## Q2. Explain Bootstrap Grid System

Bootstrap uses:

- 12-column system
- Flexbox
- Responsive breakpoints

---

## Q3. Difference between Bootstrap 4 and 5?

Bootstrap 5:

- Removed jQuery
- Added RTL support
- Improved utilities
- Better forms
- Better grid system

---

# 24. Mini Project Folder Structure

```
project/│├── index.html├── css/│   └── style.css│├── js/│   └── app.js│└── images/
```

---

# Most Important Bootstrap Classes to Memorize

## Layout

```
containerrowcold-flexjustify-content-betweenalign-items-center
```

---

## Spacing

```
m-3mt-5p-4px-2py-5
```

---

## Components

```
btncardnavbarform-controltablealertmodal
```

---

# Bootstrap Learning Strategy

## Phase 1

Learn:

- Containers
- Grid
- Spacing
- Flex

---

## Phase 2

Learn:

- Navbar
- Cards
- Forms
- Buttons

---

## Phase 3

Build:

- Landing page
- Admin dashboard
- Portfolio
- Blog UI

---

# Bootstrap vs Tailwind

|Bootstrap|Tailwind|
|---|---|
|Component-based|Utility-first|
|Faster for beginners|More customizable|
|Pre-designed|Fully custom|
|Larger CSS|Smaller optimized builds|
|Less design freedom|High design freedom|

---

# Final Reality Check

Bootstrap is still useful for:

- Dashboards
- Admin panels
- Internal tools
- Rapid MVPs
- Freelance projects with tight deadlines

But for high-end modern UI work:

- Tailwind + component systems dominate
- Bootstrap designs often look generic unless heavily customized

If you're already comfortable with Tailwind, use Bootstrap mainly to:

- Understand legacy codebases
- Work faster on quick projects
- Handle internships/client projects that still use it

# Install Bootstrap 5 in Different Environments

---

# 1. Bootstrap in Normal HTML/CSS/JS

Fastest method.

## Using CDN

```
<!DOCTYPE html><html lang="en"><head>  <meta charset="UTF-8" />  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  <!-- Bootstrap CSS -->  <link    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"    rel="stylesheet"  />  <title>Bootstrap</title></head><body>  <div class="container">    <h1 class="text-primary">Hello Bootstrap</h1>    <button class="btn btn-success">      Click    </button>  </div>  <!-- Bootstrap JS -->  <script    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js">  </script></body></html>
```

---

## Why Use CDN?

Good for:

- Practice
- Small projects
- Static sites
- Quick testing

Bad for:

- Large production apps
- Offline environments
- Performance optimization

---

# 2. Install Bootstrap in React (Vite or CRA)

---

## Step 1 — Install Bootstrap

```
npm install bootstrap
```

or

```
yarn add bootstrap
```

---

## Step 2 — Import Bootstrap CSS

### Inside `main.jsx` or `index.js`

```
import 'bootstrap/dist/css/bootstrap.min.css'
```

---

## Step 3 — Use Bootstrap Classes

```
function App() {  return (    <div className="container mt-5">      <h1 className="text-primary">        Hello React Bootstrap      </h1>      <button className="btn btn-danger">        Click      </button>    </div>  )}export default App
```

---

## Step 4 — Import Bootstrap JS (Optional)

Needed for:

- Modal
- Dropdown
- Collapse
- Tooltip
- Offcanvas

```
import 'bootstrap/dist/js/bootstrap.bundle.min.js'
```

Usually placed in:

```
main.jsx
```

---

# React Reality Check

Most serious React projects today:

- use Tailwind
- use component libraries
- avoid Bootstrap JS

Why?  
Because Bootstrap JS manipulates DOM directly, while React prefers state-driven UI.

In React:

- Bootstrap CSS = acceptable
- Bootstrap JS = often avoided

Instead people use:

- React-Bootstrap
- Headless UI
- Radix UI
- shadcn/ui

---

# 3. Install Bootstrap in Next.js

---

## Step 1 — Install Bootstrap

```
npm install bootstrap
```

---

# Next.js App Router (Modern Next.js)

Folder structure:

```
app/  layout.js  page.js
```

---

## Step 2 — Import CSS in `app/layout.js`

```
import 'bootstrap/dist/css/bootstrap.min.css'export default function RootLayout({ children }) {  return (    <html lang="en">      <body>{children}</body>    </html>  )}
```

---

## Step 3 — Import Bootstrap JS

Create:

```
app/bootstrap.js
```

---

## `bootstrap.js`

```
'use client'import 'bootstrap/dist/js/bootstrap.bundle.min.js'
```

---

## Step 4 — Use Bootstrap Loader

Inside `layout.js`

```
import 'bootstrap/dist/css/bootstrap.min.css'import BootstrapClient from './bootstrap'export default function RootLayout({ children }) {  return (    <html lang="en">      <body>        <BootstrapClient />        {children}      </body>    </html>  )}
```

---

## Step 5 — Use Bootstrap Classes

```
export default function Home() {  return (    <div className="container mt-5">      <h1 className="text-success">        Hello Next.js Bootstrap      </h1>    </div>  )}
```

---

# Why Bootstrap JS Needs Special Handling in Next.js

Because:

- Next.js uses SSR (Server Side Rendering)
- Bootstrap JS depends on `window` and browser APIs

Without client-side loading:  
you may get hydration or window errors.

---

# 4. Install React-Bootstrap (Better for React)

Instead of using Bootstrap JS directly.

---

## Install

```
npm install react-bootstrap bootstrap
```

---

## Import CSS

```
import 'bootstrap/dist/css/bootstrap.min.css'
```

---

## Example

```
import Button from 'react-bootstrap/Button'function App() {  return (    <Button variant="primary">      Click    </Button>  )}export default App
```

---

# Why React-Bootstrap is Better

Because:

- Uses React components
- No direct DOM manipulation
- Cleaner React integration
- More maintainable

---

# 5. Bootstrap Icons Installation

---

## CDN

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css">
```

---

## NPM

```
npm install bootstrap-icons
```

Import:

```
import 'bootstrap-icons/font/bootstrap-icons.css'
```

---

## Usage

```
<i class="bi bi-alarm"></i>
```

---

# 6. Common Errors

---

## Bootstrap Classes Not Working

Usually because:

- CSS not imported
- Wrong file location
- Cache issue

---

## Modal/Dropdown Not Working

Because Bootstrap JS not imported.

Need:

```
import 'bootstrap/dist/js/bootstrap.bundle.min.js'
```

---

## Next.js Hydration Error

Because Bootstrap JS runs on server.

Fix:

- use client component
- dynamic import
- separate bootstrap loader

---

# 7. Recommended Usage Strategy

## Use Bootstrap If:

- Fast prototyping
- College projects
- Admin dashboards
- Internal tools
- Client wants Bootstrap

---

## Avoid Bootstrap If:

- Building modern SaaS UI
- Heavy React state management
- Need highly custom UI
- Using Tailwind already

---

# Best Stack Choices

## Fast Development

```
Bootstrap + Vanilla JS
```

---

## Professional React

```
Tailwind + shadcn/ui
```

---

## Enterprise Dashboard

```
Bootstrap + React-Bootstrap
```