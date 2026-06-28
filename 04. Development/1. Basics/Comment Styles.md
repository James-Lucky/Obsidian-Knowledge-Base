## Comment Types

| Type        | Syntax             | Use                                |
| ----------- | ------------------ | ---------------------------------- |
| Single-line | `// comment`       | Quick inline notes                 |
| Multi-line  | `/* comment */`    | Block explanations                 |
| JSDoc       | `/** * comment */` | Documentation, function signatures |

---

## Attention Markers

```js
// ! important
// ? question
// TODO: fix later
// FIXME: broken logic
// NOTE: explanation
```

> `TODO` and `FIXME` are picked up by most VS Code extensions (e.g. **Todo Tree**).

---

## Section Headers

```js
// ===== SECTION NAME =====
// --- Subsection ---
// ### Block Title ###
// ==== Setup ====
// ----- Modal: Dentist Details -----
```

---

## Dividers

```js
// -------------------------------
// ===============================
// ***************
// ///////////////////////////////
```

---

## Bracket Labels

```js
// [SECTION]
// [Modal] Dentist Details
// {Config}
// (Helpers)
```

---

## Alternate / Regional Styles

```js
// region Dentist Modal
// endregion

/* ---- Dentist Modal ---- */

/*======== CONFIG ========*/

/**
 * @section Dentist Modal
 */
```

> `// region` / `// endregion` is supported in VS Code for **code folding**.

---

## ❌ Invalid / Non-Standard

```js
//!something       // no space after //
/// something      // triple slash (valid only in TypeScript for reference paths)
//// something     // not a standard comment style
```

**Rule:** Always put a space after `//` → `// comment` not `//comment`

---

## Quick Reference

```js
// ===== SECTION =====        → major section break
// --- subsection ---         → minor section break
// TODO: task                 → pending work
// FIXME: issue               → broken, needs fix
// NOTE: info                 → context or warning
// ! alert                    → critical attention
// ? why                      → question / uncertainty
// region Name / endregion    → foldable block in VS Code
```
