# 📁 [[Next JS Basic]] Project Structure (Production Ready)

> **Version:** Next.js (App Router)
> **Language:** TypeScript
> **Goal:** Scalable, Maintainable, Production-Ready Folder Structure

---

# 📌 Overview

This structure follows modern **Next.js App Router** best practices and is suitable for:

- Small Projects
- Medium Projects
- Large Scale Applications
- SaaS Products
- Startup Projects
- Portfolio Websites

It separates responsibilities (Separation of Concerns), making the codebase easier to maintain as the project grows.

---

# Recommended Folder Structure

```text
src/
├── app/
├── components/
├── providers/
├── hooks/
├── lib/
├── services/
├── store/
├── utils/
├── constants/
├── types/
└── middleware/
```

---

# Folder Explanation

## 📂 app/

Contains the **App Router** pages, layouts, loading pages, error pages, API routes, and route groups.

Example:

```text
app/
│
├── layout.tsx
├── page.tsx
├── globals.css
│
├── about/
│   └── page.tsx
│
├── contact/
│   └── page.tsx
│
└── api/
```

### Used For

- Routing
- Layouts
- Nested Routes
- Loading UI
- Error UI
- Server Components

---

## 📂 components/

Contains reusable React components.

Example:

```text
components/
│
├── ui/
├── landing/
├── background/
├── dashboard/
└── wrappers/
```

---

# UI Components

```text
components/
└── ui/
    ├── Button.tsx
    ├── Card.tsx
    ├── Input.tsx
    ├── Modal.tsx
    ├── Spinner.tsx
```

### Purpose

Reusable components used throughout the project.

Examples

- Button
- Card
- Modal
- Dialog
- Badge
- Avatar
- Tabs
- Dropdown

---

# Landing Components

```text
landing/
├── Hero.tsx
├── Features.tsx
├── Testimonials.tsx
├── Pricing.tsx
├── FAQ.tsx
└── CTA.tsx
```

Used only on the marketing/home page.

---

# Dashboard Components

```text
dashboard/
├── Sidebar.tsx
├── Topbar.tsx
├── TaskCard.tsx
├── AnalyticsChart.tsx
└── UserTable.tsx
```

Used inside the dashboard only.

---

# Background Components

Contains decorative backgrounds.

Example:

```text
background/
├── Gradient.tsx
├── Grid.tsx
└── Stars.tsx
```

---

# Wrapper Components

Reusable layout wrappers.

Example:

```text
wrappers/
├── Container.tsx
├── Section.tsx
└── MaxWidth.tsx
```

---

# 📂 providers/

Contains React Context Providers and global providers.

Example:

```text
providers/
├── ThemeProvider.tsx
├── AuthProvider.tsx
├── QueryProvider.tsx
```

### Common Providers

- Theme Provider
- Authentication
- React Query
- Zustand
- Redux
- Localization

---

# 📂 hooks/

Custom React Hooks.

Example

```text
hooks/
├── useAuth.ts
├── useTheme.ts
├── useWindowSize.ts
└── useDebounce.ts
```

---

# 📂 lib/

Configuration and third-party libraries.

Example

```text
lib/
├── axios.ts
├── prisma.ts
├── auth.ts
├── supabase.ts
└── firebase.ts
```

Usually contains initialized instances.

---

# 📂 services/

Business logic and API functions.

Example

```text
services/
├── auth.service.ts
├── user.service.ts
├── payment.service.ts
└── post.service.ts
```

### Example

```ts
login()

logout()

getProfile()

createPost()

deletePost()
```

Keeps API logic separate from components.

---

# 📂 store/

Global State Management.

Example

```text
store/
├── authStore.ts
├── userStore.ts
└── themeStore.ts
```

Works with:

- Zustand
- Redux Toolkit
- Jotai
- Context API

---

# 📂 utils/

Helper functions.

Example

```text
utils/
├── formatDate.ts
├── cn.ts
├── truncate.ts
└── slugify.ts
```

Examples

- Date Formatting
- ClassName Merge
- String Helpers
- Math Helpers

---

# 📂 constants/

Application constants.

Example

```text
constants/
├── routes.ts
├── colors.ts
├── api.ts
└── config.ts
```

Contains values that rarely change.

---

# 📂 types/

Global TypeScript types.

Example

```text
types/
├── user.ts
├── auth.ts
├── api.ts
└── common.ts
```

Keeps interfaces organized.

---

# 📂 middleware/

Custom middleware.

Example

```text
middleware/
└── auth.ts
```

Examples

- Authentication
- Redirects
- Permissions

---

# Recommended Route Groups

Instead of placing everything inside one route group, organize routes by feature.

Example

```text
app/
│
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
├── globals.css
└── layout.tsx
```

## Why Use Route Groups?

Benefits:

- Better organization
- Easier navigation
- Logical separation of features
- Scales well for large applications

---

# Naming Conventions

## Component Names

Use **PascalCase**

✅ Good

```text
Hero.tsx
Button.tsx
AnalyticsChart.tsx
```

❌ Avoid

```text
hero.tsx
button.tsx
analyticschart.tsx
```

---

## Home Component

Instead of

```text
Home.tsx
```

Use

```text
Hero.tsx
```

### Why?

The first section of a landing page is commonly referred to as the **Hero Section**, making the component's purpose immediately clear.

---

## FAQ Component

Instead of

```text
Faq.tsx
```

Use

```text
FAQ.tsx
```

This is the more common naming convention in professional codebases.

---

# TypeScript Files

## When to use `.ts`

Use `.ts` files for **non-JSX** TypeScript code.

Examples:

```text
auth.service.ts
routes.ts
user.ts
useAuth.ts
config.ts
```

These files contain:

- Functions
- Utilities
- Hooks (without JSX)
- Constants
- Types
- Services
- Configurations

---

## When to use `.tsx`

Use `.tsx` files whenever the file contains **JSX/TSX**.

Examples:

```text
Button.tsx
Hero.tsx
layout.tsx
page.tsx
Navbar.tsx
Footer.tsx
```

These files render React components.

---

# Final Recommended Structure

```text
src/
│
├── app/
│
├── components/
│   ├── ui/
│   ├── landing/
│   ├── background/
│   ├── dashboard/
│   └── wrappers/
│
├── providers/
│
├── hooks/
│
├── lib/
│
├── services/
│
├── store/
│
├── utils/
│
├── constants/
│
├── types/
│
└── middleware/
```

---

# Why This Structure?

### Scalability

Easy to expand without creating a messy codebase.

### Maintainability

Each folder has a single responsibility, making updates and debugging easier.

### Reusability

Shared UI components and utility functions can be reused across the application.

### Team Collaboration

Developers can quickly locate files because responsibilities are clearly separated.

### Production Ready

This structure closely matches what is commonly used in professional Next.js applications.

---

# Best Practices Checklist

- Use the **App Router** (`app/`) instead of the old `pages/` router for new projects.
- Use **TypeScript** throughout the project.
- Use `.ts` for files without JSX and `.tsx` for React components.
- Keep components focused on a single responsibility.
- Place reusable UI elements inside `components/ui`.
- Group related routes using route groups like `(marketing)`, `(auth)`, and `(dashboard)`.
- Separate API/business logic into `services`.
- Keep reusable helper functions inside `utils`.
- Store global state inside `store`.
- Place third-party configurations in `lib`.
- Define shared types in `types`.
- Keep global providers inside `providers`.
- Follow consistent naming conventions (e.g., `Hero.tsx`, `FAQ.tsx`, `Button.tsx`).

---

# Overall Rating

**⭐ 9.5 / 10**

This structure is an excellent foundation for a production-quality Next.js application. As the project grows, adding folders like `components/ui`, `providers`, `dashboard`, and `middleware` will make it even more scalable and maintainable.