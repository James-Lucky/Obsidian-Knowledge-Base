---
title: Next.js App Router - Complete Notes
tags:
  - nextjs
  - react
  - typescript
  - obsidian
  - web-development
created:
---

# Next.js App Router (Complete Notes)

> **Version:** Next.js 13+ / 14 / 15+ (App Router)

---

# What is the App Router?

The **App Router** is the modern routing system introduced in Next.js 13.

Instead of creating pages inside a `pages` folder (Pages Router), all routes are now created inside the **app** directory.

Every folder inside `app` represents a URL segment.

Example:

```
src/
└── app/
    ├── page.tsx
    ├── about/
    │   └── page.tsx
    ├── contact/
    │   └── page.tsx
    └── dashboard/
        └── page.tsx
```

Produces the following routes:

```
/                 → page.tsx
/about            → about/page.tsx
/contact          → contact/page.tsx
/dashboard        → dashboard/page.tsx
```

No React Router is required.

---

# Why App Router?

Benefits:

- File-based routing
- Nested layouts
- Route groups
- Server Components
- Streaming
- Loading UI
- Error UI
- Better scalability
- Better SEO

---

# Core Files inside app/

```
app/
│
├── layout.tsx
├── page.tsx
├── loading.tsx
├── error.tsx
├── not-found.tsx
└── globals.css
```

---

# page.tsx

Every route **must** contain a `page.tsx`.

It is the entry page of that route.

Example

```
app/
└── dashboard/
    └── page.tsx
```

URL

```
/dashboard
```

Example

```tsx
export default function DashboardPage() {
  return <h1>Dashboard</h1>;
}
```

---

# layout.tsx

`layout.tsx` wraps all child pages inside its folder.

Think of it as a shared template.

Example

```
dashboard/
├── layout.tsx
├── page.tsx
├── profile/
│   └── page.tsx
└── settings/
    └── page.tsx
```

If the layout contains:

- Sidebar
- Navbar
- Footer

Then every page inside dashboard automatically gets them.

Example

```tsx
export default function DashboardLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <>
      <Sidebar />
      <main>{children}</main>
    </>
  );
}
```

Now these pages all use the same sidebar.

```
/dashboard
/dashboard/profile
/dashboard/settings
```

---

# loading.tsx

Shows while the page is loading.

```
app/
└── dashboard/
    ├── loading.tsx
    └── page.tsx
```

Example

```tsx
export default function Loading() {
  return <p>Loading...</p>;
}
```

---

# error.tsx

Custom error page for that route.

Example

```tsx
"use client";

export default function Error() {
  return <h1>Something went wrong.</h1>;
}
```

---

# not-found.tsx

Shown when the page doesn't exist.

Example

```tsx
export default function NotFound() {
  return <h1>404 Page Not Found</h1>;
}
```

---

# globals.css

Global styles for the application.

Imported only once inside

```
layout.tsx
```

---

# Route Segments

Every folder inside app becomes a URL.

Example

```
app/
├── dashboard/
├── profile/
├── blog/
└── settings/
```

Routes become

```
/dashboard
/profile
/blog
/settings
```

---

# Nested Routes

Folders can contain more folders.

```
app/
└── dashboard/
    ├── page.tsx
    └── settings/
        └── page.tsx
```

Routes

```
/dashboard
/dashboard/settings
```

---

# Dynamic Routes

Use square brackets.

Example

```
blog/
└── [slug]/
    └── page.tsx
```

URLs

```
/blog/react
/blog/nextjs
/blog/javascript
```

Inside

```tsx
export default async function Blog({
  params,
}: {
  params: { slug: string };
}) {
  return <h1>{params.slug}</h1>;
}
```

---

# Catch-all Routes

```
[...slug]
```

Matches

```
/docs/react
/docs/react/hooks
/docs/react/hooks/useState
```

---

# Route Groups

Folders inside parentheses do **not** appear in the URL.

Example

```
app/
├── (marketing)/
│   ├── page.tsx
│   ├── donate/
│   └── support/
│
├── (auth)/
│   ├── signin/
│   └── signup/
│
├── (dashboard)/
│   └── dashboard/
│
└── layout.tsx
```

Actual URLs

```
/
/donate
/support
/signin
/signup
/dashboard
```

Notice

```
(marketing)
(auth)
(dashboard)
```

are **not** part of the URL.

They exist only for project organization.

---

# Why use Route Groups?

Without groups

```
app/
├── dashboard/
├── signin/
├── signup/
├── donate/
├── support/
├── blog/
├── pricing/
├── docs/
├── api/
└── settings/
```

As the project grows it becomes messy.

Instead

```
app/
├── (marketing)
├── (dashboard)
├── (auth)
├── (admin)
└── api
```

Much easier to navigate.

---

# Dashboard Structure

A professional dashboard usually looks like this.

```
dashboard/
├── layout.tsx
├── page.tsx
├── analytics/
│   └── page.tsx
├── profile/
│   └── page.tsx
├── settings/
│   └── page.tsx
├── tasks/
│   └── page.tsx
└── projects/
    └── page.tsx
```

Routes

```
/dashboard
/dashboard/profile
/dashboard/tasks
/dashboard/projects
/dashboard/settings
/dashboard/analytics
```

---

# Should Dashboard use page.tsx?

**Yes.**

Every page inside the dashboard should have its own `page.tsx`.

Never create

```
Dashboard.tsx
```

inside the app folder expecting it to become a route.

Only

```
page.tsx
```

creates routes.

---

# Where should Dashboard Components go?

Inside

```
components/
└── dashboard/
```

Example

```
components/
└── dashboard/
    ├── Sidebar.tsx
    ├── Topbar.tsx
    ├── AnalyticsChart.tsx
    ├── TaskCard.tsx
    ├── UserMenu.tsx
    └── DashboardStats.tsx
```

Then use them inside

```
dashboard/page.tsx
```

Example

```tsx
import Sidebar from "@/components/dashboard/Sidebar";
import DashboardStats from "@/components/dashboard/DashboardStats";

export default function DashboardPage() {
  return (
    <>
      <DashboardStats />
    </>
  );
}
```

---

# Difference Between page.tsx and Component

## page.tsx

- Creates a route
- Represents a page
- Can fetch data
- Uses layouts
- Lives inside `app`

Example

```
dashboard/page.tsx
```

---

## Component

- Reusable UI
- Does NOT create routes
- Can be used anywhere

Example

```
components/dashboard/Sidebar.tsx
```

---

# App Router vs React (Vite)

## React

```
src/
├── App.tsx
├── main.tsx
└── components/
```

Routing

```
React Router
```

---

## Next.js

```
app/
├── page.tsx
├── layout.tsx
└── dashboard/
```

Routing

```
Automatic
```

No `App.tsx`.

---

# Should I use App.tsx?

**No.**

`App.tsx` belongs to:

- React
- Vite
- CRA

It is **not used** in Next.js App Router.

---

# Complete Project Structure

```
src/
│
├── app/
│   ├── (marketing)/
│   │   ├── page.tsx
│   │   ├── donate/
│   │   │   └── page.tsx
│   │   └── support/
│   │       └── page.tsx
│   │
│   ├── (auth)/
│   │   ├── signin/
│   │   │   └── page.tsx
│   │   └── signup/
│   │       └── page.tsx
│   │
│   ├── (dashboard)/
│   │   └── dashboard/
│   │       ├── layout.tsx
│   │       ├── page.tsx
│   │       ├── analytics/
│   │       │   └── page.tsx
│   │       ├── profile/
│   │       │   └── page.tsx
│   │       ├── settings/
│   │       │   └── page.tsx
│   │       └── tasks/
│   │           └── page.tsx
│   │
│   ├── globals.css
│   └── layout.tsx
│
├── components/
│   ├── ui/
│   ├── landing/
│   ├── dashboard/
│   ├── wrappers/
│   └── background/
│
├── providers/
├── hooks/
├── lib/
├── services/
├── store/
├── constants/
├── utils/
├── types/
└── middleware/
```

---

# Best Practices

✅ Every route must have a `page.tsx`.

✅ Use `layout.tsx` for shared layouts.

✅ Keep `page.tsx` small.

✅ Put reusable UI in `components/`.

✅ Use Route Groups for organization.

✅ Use nested layouts for dashboards.

✅ Do **not** create `App.tsx` in Next.js.

✅ Use `page.tsx` to create routes.

✅ Keep business logic outside pages.

✅ Organize components by feature.

---

# Quick Cheat Sheet

| File | Purpose |
|------|---------|
| `page.tsx` | Creates a route/page |
| `layout.tsx` | Shared layout |
| `loading.tsx` | Loading UI |
| `error.tsx` | Error UI |
| `not-found.tsx` | 404 page |
| `globals.css` | Global CSS |
| `template.tsx` | Re-renders layout on navigation (optional) |
| `route.ts` | API Routes |

---

# Remember

> **`page.tsx` = URL**

```
dashboard/page.tsx
```

↓

```
/dashboard
```

---

> **`layout.tsx` = Shared UI**

```
Sidebar
Navbar
Footer
```

Shared across all child pages.

---

> **`components/` = Reusable UI**

```
Sidebar.tsx
Button.tsx
Hero.tsx
Navbar.tsx
```

They **do not** create routes.

---

> **`App.tsx` = React/Vite only**

**Next.js App Router does not use App.tsx.**