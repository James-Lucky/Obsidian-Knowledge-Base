### 🚀 Basic

- **The Single Source of Truth:** GitHub acts as a central remote location where the production-ready application resides. Personal workspaces should never directly push experimental code into the main path without isolated branches
    
- **Git vs. GitHub Distinction:** Git is a local tracking engine that takes historical "snapshots" of files on your machine. GitHub is a cloud-based platform allowing multiple distributed machines to sync with a single timeline.
    
- **The Anatomy of Git Conflicts:** Merge conflicts happen when two separate development branches change the exact same line of code concurrently. Git drops a warning flag because it cannot programmatically infer which version to preserve.
    
- **Fast-Forward vs. Three-Way Merge:** Fast-forward simply shifts the local timeline pointer ahead because there are zero structural deviations. A Three-Way merge evaluates changes across three historical points to blend a split timeline together into a brand new merge commit.
    

### 🔍 Technical Breakdown

#### 1. Initial Global Configuration

Before initializing Git repositories, configurations must be written globally to identify authorship tags and prevent cross-platform file formatting breaks between Windows (CRLF) and macOS (LF) systems:

Bash

```
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
git config --global core.editor "code --wait"
git config --global core.autocrlf input # For Mac/Linux. Use "true" if on Windows
```

#### 2. Local Architecture: The Three Git States

Files inside an initialized tracking directory step through three distinct logical areas before arriving safely inside history:

1. **Untracked / Modified State (`?` or `M` flags):** Files containing newer changes that Git detects but isn't actively monitoring for snapshots).
    
2. **Staged State (`A` flag):** Files marked for snapshot selection. Staging adds files to the queue using `git add`.
    
3. **Committed State:** Safe checkpoints saved permanently in the `.git` directory under a cryptographic hash signature.
    

## 🛠️ Essential Command Reference

### Local File Tracking & State Management

| **Command**                 | **Functional Purpose**                                                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `git init`                  | Instantiates a fresh local `.git` repository folder hidden within the current workspace root directory.                        |
| `git status -s`             | Outputs short-form, readable status shorthand markers displaying modified (`M`), untracked (`??`), or staged (`A`) structures. |
| `git add .`                 | Pipelines all newly created, updated, or modified files from the local directory directly into the Staging area.               |
| `git commit -m "msg"`       | Permanently seals the current staged assets into a historical checkpoint block.                                                |
| `git log --oneline`         | Flattens repository snapshot history logs into single, scannable terminal lines carrying unique short hashes.                  |
| `git log --oneline --graph` | Renders a structural visual branch ancestry map timeline tree mapping splits and merges.                                       |

### Recovery

| **Command**               | **Functional Purpose**                                                                                                                       |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `git reset --hard HEAD~1` | **Destructive Action.** Hard wipes out files completely across your working tree, resetting paths backwards by exactly one generation level. |

### Branching & Context Shifting

| **Command**            | **Functional Purpose**                                                                                               |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `git branch`           | Lists all localized operational branch systems inside the repository.                                                |
| `git branch -d <name>` | Safe-deletes historical development branches once their feature payloads have been completely merged up.             |
| `git switch <branch>`  | Safely swaps working files and points context flags natively across different isolation environments.                |
| `git switch -c <name>` | Rapidly spins up a pristine feature branch pipeline and points focus inside it in one single execution block.        |
| `git stash`            | Shelves incomplete, uncommitted scratchpad edits safely into storage memory to allow quick emergency branch jumping. |
| `git stash apply`      | Restores previously stashed, loose workspace modifications back into active files without executing local commits.   |
| `git stash drop`       | Clears and clears memory blocks storing stashed fragments out from your system stack permanently.                    |

## 👥 Unified Team Collaboration Workflow

To collaborate smoothly with zero baseline code overwrite failures, teams should execute the following precise sequence:

**1.Repository Framework Initialization:**Executed by Project Lead.

The project manager designs base structures locally, initialises via `git init`, assigns an online target repository link using `git remote add origin <url>`, pushes base structures up, and configures peer repository access inside GitHub settings.

**2.Workspace Cloning:**Executed by Collaborators.

Team developers clone identical remote instances onto local architectures using `git clone <repo-url>` to build functional development workspaces matching the remote state.
**3.Feature Isolation Tracking:**Executed by Developer.

Developers immediately switch out of default timelines into isolated modules using `git switch -c feature/your-feature`. This completely insulates the production branch from structural bugs while feature work progresses.

**4.Payload Deployment:**Executed by Developer.

Once module codes pass checks, developers stage and commit snapshots locally before casting isolated track updates up online: `git push -u origin feature/your-feature`.

**5.Integration & Auditing:**Executed by Project Lead / Merger.

The code administrator fetches incoming tracks via `git fetch`, evaluates code integrity locally by running audits on the feature code, switches back to `main`, and runs `git merge feature/your-feature` to safely blend codebases.

### ⚠️ Resolving Structural Merge Conflicts

If automated merges trip over structural conflict warnings

1. Open the project root in VS Code to locate highlighted boundaries.
    
2. Select **Accept Current Change** to retain `main`'s native trajectory, **Accept Incoming Change** to adopt your peer's newer track adjustments, or **Accept Both Changes** to combine them.
    
3. Finalise resolution by re-executing `git add .` and creating an explicit validation checkpoint using `git commit -m "Resolved merge conflict"`. Push the unified results up to GitHub.

## 🏗️ Starting a Project

|**Command**|**What it Does**|
|---|---|
|`git init`|Starts a brand new local repository inside your current folder.|
|`git clone <url>`|Downloads an existing project from GitHub onto your computer.|

## 🛠️ The Daily Development Loop (Save Changes)

This is the core loop you will run multiple times a day to save your work.

Bash

```
# Step 1: Check what has changed
git status -s

# Step 2: Stage your files (add them to the dynamic staging area)
git add .               # Stages all files
git add path/to/file.txt # Stages a specific file

# Step 3: Commit (Take a permanent local snapshot of your project)
git commit -m "Brief descriptive message of what you changed"
```

## 🌿 Working with Branches (Feature Isolation)

Never work directly on your `main` or `master` branch. Use branches to isolate your experimental features safely.

|**Command**|**What it Does**|
|---|---|
|`git branch`|Lists all local branches. (The one with `*` is active).|
|`git switch -c <branch-name>`|Creates a brand new branch and switches your context directly into it.|
|`git switch <branch-name>`|Switches back to an existing branch.|
|`git merge <branch-name>`|Merges the changes of the specified branch into your _current active branch_.|
|`git branch -d <branch-name>`|Deletes a branch safely (usually done after it is successfully merged).|

## 🚀 Syncing with Remote Repositories (GitHub)

Use these commands to share code with team members or update your local files with changes made online.

|**Command**|**What it Does**|
|---|---|
|`git remote add origin <url>`|Links your local repository to a remote GitHub repository path for the first time.|
|`git push -u origin <branch-name>`|Uploads your local branch snapshots to GitHub for the first time.|
|`git push`|Uploads future commits to GitHub once the upstream branch is set up.|
|`git pull`|Downloads all newer updates from GitHub and automatically merges them into your active files.|
|`git fetch`|Downloads updates from GitHub _without_ altering your local files, allowing you to review changes first.|

## ⏳ Emergency & Safety Net 

If you make a mistake, break your code layout, or need to pivot tasks quickly, these commands act as a rescue layer.

**1.Shelve Temporary Unfinished Edits:**git stash.

If you are in the middle of a feature and need to switch branches quickly but aren't ready to commit incomplete work, run `git stash` to clear your workspace and hide edits safely in memory.

**2.Restore Shelved Changes Later:**git stash apply.

Once you switch back to your development branch, run `git stash apply` to bring back your tucked-away unfinished changes exactly where you left off.

**3.Nuclear Option: Reset Workspace:**git reset --hard HEAD~1.

**Warning: Destructive.** Completely discards all uncommitted modifications and completely erases your last local commit, rewinding your repository back exactly one generation level.

## 📊 Viewing Project History

|**Command**|**What it Does**|
|---|---|
|`git log --oneline`|Displays a scannable, clean, single-line list of all previous local project checkpoints.|
|`git log --oneline --graph`|Displays an ASCII timeline mapping out branch splits and chronological merges.|


Here is a quick cheat sheet for **deleting things in Git**, depending on what exactly you need to remove.

### 1. Removing Files

|**Command**|**What it Does**|
|---|---|
|**`git rm <filename>`**|Deletes a file from both your computer **and** stops Git from tracking it.|
|**`git rm --cached <filename>`**|Stops Git from tracking a file, but **keeps the file safe on your computer**. (Great if you accidentally committed passwords or data files).|

### 2. Deleting Branches

|**Command**|**What it Does**|
|---|---|
|**`git branch -d <branch-name>`**|**Safe delete.** Deletes a local branch _only_ if you have already merged its code into your main timeline.|
|**`git branch -D <branch-name>`**|**Force delete.** Permanently deletes a local branch, even if you haven't merged the code. (Use this to throw away failed experiments).|
|**`git push origin --delete <branch-name>`**|Deletes the branch **off the GitHub cloud servers**.|

### 3. Deleting Uncommitted Local Changes (Undo)

If you wrote messy code and just want to wipe it out and start over from your last clean save point:

|**Command**|**What it Does**|
|---|---|
|**`git restore <filename>`**|Discards all newer uncommitted edits in a specific file, resetting it back to its last saved state.|
|**`git restore .`**|Discards **all local edits** in the entire folder. Everything returns to your last commit.|
|**`git clean -fd`**|Deletes all **untracked files and folders** that you created but never added to Git.|

### 4. Erasing Commits (History Rewriting)

If you already hit the save button (`git commit`) but want to undo it:

|**Command**|**What it Does**|
|---|---|
|**`git reset --soft HEAD~1`**|Deletes your last commit, but **keeps your code changes loose** in your editor so you can edit and try committing again.|
|**`git reset --hard HEAD~1`**|**The nuclear option.** Completely erases your last commit **and** destroys all the code you wrote in it. Returns your files entirely back to the generation before it.|

### 5. Clearing Stashes

| **Command**           | **What it Does**                                                          |
| --------------------- | ------------------------------------------------------------------------- |
| **`git stash drop`**  | Deletes your most recently shelved temporary code snapshot.               |
| **`git stash clear`** | Permanently deletes **all stashes** currently saved in your memory stack. |
**Rename locally and push to GitHub:**

bash

```bash
# Rename the branch you're currently on
git branch -m new-branch-name

# Or rename a different branch
git branch -m old-branch-name new-branch-name

# Push the renamed branch to GitHub
git push origin new-branch-name

# Delete the old branch from GitHub
git push origin --delete old-branch-name
```

**If you renamed the default branch:**

- Go to your GitHub repo → **Settings** → **Branches**
- Change the default branch if it points to the old name
- Update any references in your CI/CD workflows, documentation, or links

**Important considerations:**

1. **If others are using the old branch** — they need to update their local tracking:

bash

```bash
   git fetch origin
   git branch -m old-name new-name
   git branch -u origin/new-name new-name
```

2. **If the branch is protected** — you might need to temporarily disable branch protection rules in Settings before deleting the old one.
3. **For PRs pointing to the old branch** — GitHub will show them as invalid. You'll need to update or close them.