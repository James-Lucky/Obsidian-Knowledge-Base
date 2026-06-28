
---

## 1. Where to Place `.git`

### ❌ Wrong

```
project/
├── client/   ← .git is here
└── server/   ← never tracked
```

### ✅ Correct

```
project/       ← .git goes here
├── client/
└── server/
```

> Git tracks from where `.git` exists. If you `git init` inside `client/`, the `server/` folder is completely invisible to Git.

---

## 2. Project Structure Rules

### Serious / Production Projects

```
one project = one repository
```

Use for: SaaS apps, portfolios, dashboards, client work, full-stack apps.

```
project-name/
├── client/
│   ├── src/
│   ├── public/
│   └── package.json
├── server/
│   ├── src/
│   ├── .env
│   └── package.json
├── docs/
├── .gitignore
└── README.md
```

### Mini / Practice Projects

```
one repo = many small projects
```

```
mini-projects/
├── qr-generator
├── timer
├── drag-drop
└── password-generator
```

---

## 3. What NOT to Do

### ❌ Mixing serious + unrelated projects in one repo

```
AllProjects/
├── portfolio-v1
├── portfolio-v2
├── ai-project
└── experiments
```

**Problems:**

- Deployment platform scans entire repo → build conflicts
- Multiple Next.js versions → vulnerability flags
- Root directory confusion on Vercel/Netlify
- Dependency detection failures

---

## 4. Git Push — How It Actually Works

Git pushes **commits**, not folders.

```bash
# Only push server changes
git add server/
git commit -m "fix: auth logic"
git push
```

Only changed + staged files are committed. The entire project is NOT re-uploaded every time.

---

## 5. Deploying a Specific Folder from Monorepo

On **Vercel / Netlify**, set:

```
Root Directory = qr-generator
```

Only that subfolder gets built and deployed.

---

## 6. Frontend vs Backend Deployment

|Part|Deploy To|
|---|---|
|`client/`|Vercel, Netlify|
|`server/`|Railway, Render, Fly.io|

---

## 7. Local Workspace Structure

```
Projects/           ← NOT a Git repo
├── portfolio/      ← own repo
├── ai-chat/        ← own repo
├── dashboard/      ← own repo
├── mini-projects/  ← one shared repo
└── experiments/
```

---

## 8. Naming Convention

Use **kebab-case** always.

|✅ Good|❌ Bad|
|---|---|
|`drag-drop`|`Drag&Drop`|
|`password-generator`|`FinalProjectNEW`|
|`mind-script`|`project-v2-final`|

---

## 9. Commit Message Format

Follow **Conventional Commits**:

```
feat: add JWT authentication
fix: resolve navbar overflow
refactor: optimize filtering logic
chore: update dependencies
docs: add API documentation
```

Avoid: `fix`, `changes`, `done`, `final`

---

## Quick Reference

| Situation                       | Action                                   |
| ------------------------------- | ---------------------------------------- |
| New full-stack project          | `git init` at root, not inside `client/` |
| Push only backend changes       | `git add server/` → commit → push        |
| Deploy one folder from monorepo | Set Root Directory in Vercel/Netlify     |
| Practice projects               | Put all in one `mini-projects` repo      |
| Production app                  | One app = one repo, always               |
