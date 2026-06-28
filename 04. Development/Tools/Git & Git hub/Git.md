🛠️ Part 1: Version Control (Git & GitHub)

Overview

- **Git:** A free and open-source version control system that helps track history and changes in code. It is fast, scalable, and built for collaboration.
- **GitHub:** A website that allows developers to store and manage their code using Git.
- **Repository (Repo):** Folders used to store your code project.
- **Remote vs. Local:** "Remote" refers to GitHub (or the cloud), while "Local" refers to your laptop or personal machine.
- **Fork:** A new repository that shares code and visibility settings with the original "upstream" repository. It is essentially a rough copy of a repo.
- **Readme.md:** A file used to provide detailed information about the code.

Git File Status Lifecycle

A file in a Git directory can be in one of four states:

1. **Untracked:** New files that Git doesn't yet track.
2. **Modified:** Code that has been changed.
3. **Staged:** File is ready to be committed.
4. **Unmodified:** Unchanged code.

**Basic Workflow Diagram:** `GitHub repo -> Clone -> Changes -> Add -> Commit -> Push`. _(Or locally: New/Modified File -> Add (Staged) -> Commit (Unchanged))_.

Global Configuration Commands

- Check Git version: `git --version`.
- Set username: `git config --global user.name "Your Name"`.
- Set email: `git config --global user.email "your mail"`.
- Check username/email: `git config --global user.name` or `git config --global user.email`.
- Edit username/email: `git config --global --edit`.
- List configurations: `git config --list`.

Essential Git Commands

- **Initialization & Cloning:**
    - `git init`: Used to create a new Git repository.
    - `git clone (link paste)`: Cloning a repository onto your local machine.
- **Staging & Committing:**
    - `git status`: Displays the state of the code.
    - `git add (file name)`: Adds new or changed files in your working directory to the Git staging area. _(Note: "Add" does not save records, but "commit" does)_.
    - `git add .`: Adds all files.
    - `git commit -m "some message"`: Commits the changes; it is the record of the change.
- **Connecting & Pushing to Remote:**
    - `git remote add origin (link)`: Adds the remote origin link.
    - `git remote -v`: Verifies the remote repository.
    - `git push origin main`: Uploads local repo content to the remote repo.
    - `git push -u origin main`: Pushes with upstream tracking, if required.
- **Pulling & Updating:**
    - **Pull command:** Used to fetch and download content from a remote repo and immediately update the local repo to match the content.

Branching and Merging

**Branches** allow you to diverge from the `main` line of development (e.g., creating a `feature` branch) and merge them back later.

- Check current branch: `git branch`.
- Rename a branch: `git branch -m main`.
- Create a new branch: `git checkout -b new branch Name`.
- Navigate to a branch: `git checkout branch Name`.
- Delete a branch: `git branch -d branch Name`.

**Merging & Conflicts:**

- **Compare Code:** `git diff branch name` compares commits, branches, files, and more.
- **Merge Code:** `git merge branch Name` merges two branches together.
- **Pull Request (PR):** Lets you tell others about changes you've pushed to a branch in a repository on GitHub.
- **Merge Conflicts:** An event that takes place when Git is unable to automatically resolve differences in code between two commits.

Undoing Changes

- **Case 1 (Staged Changes):** `git reset file name` or `git reset`.
- **Case 2 (Committed Changes - Single Commit):** `git reset HEAD~1`.
- **Case 3 (Committed Changes - Many Commits):** `git reset commit hash` or `git reset --hard commit hash`.

---

💻 Part 2: Terminal / Command Line Interface Basics

The **CLI (Command Line Interface)** is a text-based way (or program) that allows you to interact with computer programs and operating systems, modify files, run programs, and navigate through folders and files (e.g., Terminal, CMD).

- `cd`: Change directory.
- `cd ..`: Move to the previous directory.
- `ls`: List files.
- `ls -a`: Show visible and hidden files.
- `mkdir Name`: Make/create a new directory.
- `~`: Represents the ROOT directory or main folder.

---

🌐 Part 3: Web Rendering Terminology & Build Process

**Build Process Flow:** `Source code -> Build -> Server -> Client`.

- **CSR (Client Side Rendering):** A JavaScript rendering technique where the HTML content and UI are generated on the client browser using JS.
- **SSR (Server Side Rendering):** Rendering technique executed on the server.
- **SSG (Static Site Generation):** Pre-rendering a static site at build time.
- **ISR (Incremental Static Regeneration):** Generating or updating static pages incrementally.