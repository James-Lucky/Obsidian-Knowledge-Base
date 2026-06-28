## Variables

```css
:root {
  /* Colors */
  --primary-color:    #000000;
  --secondary-color:  #ffffff;
  --accent-color:     #4942E4;
  --text-color:       #202020;
  --bg-color:         #ffffff;

  /* Fonts */
  --primary-font:   'Inter', sans-serif;
  --secondary-font: 'Inter', sans-serif;

  /* Spacing */
  --spacing-sm:  0.8rem;
  --spacing-md:  1.6rem;
  --spacing-lg:  3.2rem;
  --spacing-xl:  6.4rem;

  /* Border */
  --border-radius: 8px;
  --border-color:  #e0e0e0;
}
```

---

## Reset

```css
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 62.5%; /* 1rem = 10px */
  scroll-behavior: smooth;
  overflow-x: hidden;
}

body {
  font-family: var(--primary-font);
  font-size: 1.6rem;
  color: var(--text-color);
  background-color: var(--bg-color);
  line-height: 1.6;
  overflow-x: hidden;
}
```

---

## Typography

```css
h1, h2, h3, h4, h5, h6 {
  font-family: var(--primary-font);
  font-weight: 700;
  line-height: 1.2;
  color: var(--text-color);
}

h1 { font-size: 4.8rem; }
h2 { font-size: 3.6rem; }
h3 { font-size: 2.4rem; }
h4 { font-size: 2.0rem; }
h5 { font-size: 1.8rem; }
h6 { font-size: 1.6rem; }

p {
  font-family: var(--secondary-font);
  font-size: 1.6rem;
  font-weight: 400;
  line-height: 1.7;
  color: var(--text-color);
}
```

---

## Links & Lists

```css
a {
  text-decoration: none;
  color: var(--accent-color);
  transition: color 0.2s ease;
}

a:hover {
  color: var(--primary-color);
}

ul, ol {
  list-style: none;
  margin: 0;
  padding: 0;
}
```

---

## Images & Media

```css
img,
video,
svg {
  display: block;
  max-width: 100%;
  height: auto;
}
```

---

## Scrollbar

```css
/* Chrome / Edge */
::-webkit-scrollbar        { width: 8px; }
::-webkit-scrollbar-track  { background: var(--bg-color); }
::-webkit-scrollbar-thumb  { background: var(--accent-color); border-radius: 4px; }
::-webkit-scrollbar-thumb:hover { background: var(--primary-color); }

/* Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: var(--accent-color) var(--bg-color);
}
```

---

## Focus (Accessible)

```css
:focus-visible {
  outline: 2px solid var(--accent-color);
  outline-offset: 3px;
}
```

> Never use `outline: 0` without a replacement — breaks keyboard navigation.

---

## Utilities

```css
.container {
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
}

.flex         { display: flex; }
.flex-center  { display: flex; align-items: center; justify-content: center; }
.flex-between { display: flex; align-items: center; justify-content: space-between; }
.grid         { display: grid; }

.text-center { text-align: center; }
.text-left   { text-align: left; }
.text-right  { text-align: right; }

.w-full  { width: 100%; }
.h-full  { height: 100%; }
.hidden  { display: none; }
```

---

## rem Reference

|`rem`|`px`|
|---|---|
|`1rem`|`10px`|
|`1.6rem`|`16px`|
|`2.4rem`|`24px`|
|`3.2rem`|`32px`|
|`4.8rem`|`48px`|
|`6.4rem`|`64px`|
