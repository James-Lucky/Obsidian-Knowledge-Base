# Loading States & Perceived Performance

## Definition

Loading states are UI elements shown while data or an action is being processed.

Purpose:

- Reduce user uncertainty
- Provide feedback
- Improve perceived performance
- Prevent repeated actions
- Increase trust

---

# Why Loading States Matter

Users don't like waiting.

The problem isn't only waiting.

It's **waiting without knowing what's happening.**

Good loading states answer:

- Is the app working?
- How long will it take?
- Should I wait?
- Did my click work?

---

# Psychology Behind Loading States

Users experience anxiety when:

- Nothing changes after clicking
- No progress is visible
- They don't know if something is broken

Proper loading feedback reduces:

- Anxiety
- Confusion
- Rage clicks
- Page abandonment

---

# Types of Loading States

---

## 1. Skeleton Screen

### What is it?

A fake layout shown before real content loads.

Example

```
██████████████

██████████

█████████████
```

Instead of

```
Loading...
```

---

### Best Use Cases

- News websites
- Social media feeds
- Dashboards
- Product listings
- Blogs
- Entire page loading

Examples

- YouTube
- LinkedIn
- Instagram
- Facebook
- Medium

---

### Advantages

- Feels faster
- Users understand layout
- Lower perceived waiting time
- Prevents layout shift

---

### Avoid

Small actions like:

- Save
- Delete
- Like

---

## 2. Progress Bar

### What is it?

Shows completion percentage.

Example

```
██████████░░░░

68%
```

---

### Best Use Cases

Known duration tasks

Examples

- File upload
- Download
- Installation
- Data migration
- Video processing

---

### Advantages

Users know

- How much is completed
- Remaining time
- Task is progressing

---

### Types

Determinate

```
45%
```

Indeterminate

```
█████ moving █████
```

when exact progress is unknown.

---

### Best Practice

Show

- Percentage
- Time remaining (if possible)
- Current step

Example

```
Uploading image...

68%

2 minutes remaining
```

---

## 3. Spinner

### What is it?

Rotating animation indicating work in progress.

```
⟳
```

---

### Best Use Cases

Very short operations

Examples

- Save button
- Login
- Refresh
- Search
- Submit form

---

### Advantages

Simple

Lightweight

Easy to implement

---

### Problems

Bad for long loading

Users think

"Is it frozen?"

---

### Rule

If loading exceeds

```
2–3 seconds
```

Use skeleton or progress indicator instead.

---

## 4. Optimistic UI

### Definition

Update the UI immediately before receiving server confirmation.

Example

User clicks ❤️

Immediately

```
❤️ Liked
```

Backend request happens afterward.

If request fails

```
Undo action

Show error
```

---

### Best Use Cases

- Like
- Bookmark
- Follow
- Toggle switch
- Checkbox
- Add to favorites

---

### Benefits

Feels instant

Makes apps appear extremely fast

---

### Risk

Need rollback if server fails.

Example

```
Liked

↓

Server failed

↓

Unlike automatically

↓

Show

"Couldn't save changes."
```

---

# Choosing the Right Loading State

|Situation|Best Choice|
|---|---|
|Entire page|Skeleton|
|Dashboard|Skeleton|
|Feed|Skeleton|
|File upload|Progress bar|
|Installation|Progress bar|
|Download|Progress bar|
|Save button|Spinner|
|Refresh table|Spinner|
|Search|Spinner|
|Like button|Optimistic UI|
|Bookmark|Optimistic UI|
|Toggle switch|Optimistic UI|

---

# Loading Time Guidelines

|Waiting Time|Recommended UX|
|---|---|
|0–100 ms|No loader|
|100–300 ms|Usually no loader|
|300 ms–1 s|Spinner|
|1–3 s|Skeleton|
|>3 s|Skeleton + progress|
|>10 s|Progress + ETA + Cancel|

---

# UX Best Practices

## Disable repeated clicks

Bad

```
Save

Save

Save

Save
```

Good

```
Saving...

Button Disabled
```

---

## Prevent Layout Shift

Reserve image/content space before loading.

Skeletons help.

---

## Use Meaningful Messages

Bad

```
Loading...
```

Good

```
Fetching your projects...
```

---

## Keep Animations Smooth

Use subtle animations.

Avoid flashy effects.

---

## Don't Fake Long Delays

Don't intentionally delay data just to show a loader.

---

## Show Errors

Instead of infinite spinner

Show

```
Couldn't load data.

Retry
```

---

## Preserve User Input

If loading fails, don't erase form data.

---

# Common Mistakes

❌ Spinner for every loading state

❌ Infinite spinner

❌ No error handling

❌ Layout jumping

❌ Multiple loaders on one page

❌ Blocking the entire page unnecessarily

❌ No feedback after button click

---

# Real-World Examples

### YouTube

- Skeleton thumbnails
- Progressive image loading

---

### Instagram

- Skeleton feed
- Optimistic like
- Optimistic comments

---

### GitHub

- Skeleton repository list
- Progress for uploads

---

### Google Drive

- Progress bars for uploads
- Optimistic folder creation

---

### Notion

- Skeleton blocks
- Progressive content rendering

---

# Related Topics to Learn Next

Understanding loading states is only one piece of building fast-feeling applications. You should also study:

### Performance

- Core Web Vitals (LCP, INP, CLS)
- Lazy Loading
- Code Splitting
- Tree Shaking
- Prefetching vs Preloading
- Image Optimization
- Virtual Scrolling
- Infinite Scroll
- Pagination
- Caching (Browser, CDN, API)

### Frontend Architecture

- Server-Side Rendering (SSR)
- Static Site Generation (SSG)
- Incremental Static Regeneration (ISR)
- Client-Side Rendering (CSR)
- Streaming UI
- Partial Hydration
- React Suspense
- React Transitions
- Error Boundaries

### Data Fetching

- React Query / TanStack Query
- SWR
- Stale-While-Revalidate
- Optimistic Updates
- Background Refetching
- Request Deduplication

### UX Design

- Microinteractions
- Empty States
- Error States
- Success States
- Accessibility (ARIA for loaders)
- Visual Feedback
- Progressive Disclosure
- Nielsen's 10 Usability Heuristics

### Backend Concepts

- Asynchronous Processing
- WebSockets
- Server-Sent Events (SSE)
- Polling vs Long Polling
- Background Jobs
- Queues (BullMQ, RabbitMQ, Kafka)

### Animation

- CSS Transitions
- CSS Keyframes
- Framer Motion
- View Transitions API
- Motion Principles (ease, duration, anticipation)