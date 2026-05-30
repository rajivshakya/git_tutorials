# Interview Question: What is the Difference Between Git Merge and Git Rebase?

## Answer

Both **Git Merge** and **Git Rebase** are used to integrate changes from one branch into another branch. However, they handle commit history differently.

- **Git Merge** preserves branch history and creates a merge commit.
- **Git Rebase** rewrites commit history and creates a clean linear history.

---

# Practical Hands-On Example

## Step 1: Create a New Repository

```bash
mkdir git-demo
cd git-demo

git init

echo "Version 1" > app.txt
git add .
git commit -m "Initial Commit"
```

Current History:

```text
A
```

---

## Step 2: Create a Feature Branch

```bash
git checkout -b feature
```

Add a commit:

```bash
echo "Feature Change 1" >> app.txt
git add .
git commit -m "Feature Commit 1"
```

History:

```text
A --- B
```

Where:

```text
B = Feature Commit 1
```

---

## Step 3: Add a Commit to Main Branch

Switch to main branch:

```bash
git checkout main
```

Add another commit:

```bash
echo "Main Change 1" >> app.txt
git add .
git commit -m "Main Commit 1"
```

History now becomes:

```text
        B
       /
A ---- C
```

Where:

```text
B = Feature Commit 1
C = Main Commit 1
```

Now the feature branch and main branch have diverged.

---

# Git Merge

## Command

Switch to feature branch:

```bash
git checkout feature
```

Merge main branch:

```bash
git merge main
```

---

## Before Merge

```text
        B
       /
A ---- C
```

---

## After Merge

```text
        B -------- M
       /          /
A ---- C --------
```

Where:

```text
M = Merge Commit
```

Git creates an additional merge commit to combine both branches.

---

## Verify History

```bash
git log --oneline --graph
```

Example Output:

```text
*   M Merge branch 'main'
|\
| * C Main Commit 1
* | B Feature Commit 1
|/
* A Initial Commit
```

---

## Advantages of Merge

- Preserves complete history.
- Easy to track branch relationships.
- Safe for shared branches.
- No history rewriting.

---

## Disadvantages of Merge

- Creates extra merge commits.
- History can become cluttered.

Example:

```text
Merge branch 'main'
Merge branch 'release'
Merge branch 'hotfix'
Merge branch 'feature'
```

---

# Git Rebase

Instead of merge, let's use rebase.

Switch to feature branch:

```bash
git checkout feature
```

Run:

```bash
git rebase main
```

---

## What Happens Internally?

### Original History

```text
        B
       /
A ---- C
```

---

### Step 1

Git temporarily removes commit B.

```text
A ---- C
```

---

### Step 2

Git moves the feature branch pointer to commit C.

```text
A ---- C
```

---

### Step 3

Git reapplies commit B on top of C.

```text
A ---- C ---- B'
```

Notice:

```text
B' ≠ B
```

Git creates a brand-new commit with a new commit hash.

---

## After Rebase

```text
A ---- C ---- B'
```

History becomes linear.

---

## Verify History

```bash
git log --oneline --graph
```

Example Output:

```text
* B' Feature Commit 1
* C Main Commit 1
* A Initial Commit
```

No merge commit is created.

---

# Visual Comparison

## Git Merge

```text
        B
       /
A ---- C
       \
        M
```

History preserves branching.

---

## Git Rebase

```text
A ---- C ---- B'
```

History becomes linear.

---

# Real DevOps Example

Suppose another engineer pushes commits to main while you are working on a feature branch.

### Main Branch

```text
A ---- B ---- C
```

### Feature Branch

```text
A ---- D ---- E
```

---

## Using Merge

```bash
git checkout feature
git merge main
```

Result:

```text
          D ---- E
         /        \
A ---- B ---- C ---- M
```

---

## Using Rebase

```bash
git checkout feature
git rebase main
```

Result:

```text
A ---- B ---- C ---- D' ---- E'
```

The history is much cleaner.

---

# Merge Conflict During Rebase

Suppose both branches modify the same line.

Main branch:

```text
Application Version = 2
```

Feature branch:

```text
Application Version = 3
```

Run:

```bash
git rebase main
```

Git may stop with a conflict.

Check the conflict:

```bash
git status
```

Fix the file manually.

After fixing:

```bash
git add .
git rebase --continue
```

Git continues the rebase process.

---

# When Should We Use Merge?

Use Merge when:

- Working on shared branches.
- Multiple developers collaborate on the same branch.
- History preservation is important.
- You do not want to rewrite history.

Example:

```bash
git merge main
```

---

# When Should We Use Rebase?

Use Rebase when:

- Updating a feature branch before creating a Pull Request.
- Keeping Git history clean.
- Working on your own feature branch.
- You want a linear commit history.

Example:

```bash
git rebase main
```

---

# Golden Rule of Rebase

Never rebase a branch that has already been shared with other developers.

Avoid:

```bash
git rebase main
git push --force
```

unless you fully understand the impact.

Because rebase rewrites commit history, other team members may face issues when pulling changes.

---

# Merge vs Rebase Comparison

| Feature | Merge | Rebase |
|----------|--------|---------|
| Creates Merge Commit | Yes | No |
| Rewrites History | No | Yes |
| Preserves Branch Structure | Yes | No |
| Linear History | No | Yes |
| Safe for Shared Branches | Yes | No |
| Clean Git Log | No | Yes |

---

# Interview Answer (Short Version)

Git Merge combines branches while preserving history and creating a merge commit.

Git Rebase moves commits from one branch on top of another branch, rewrites history, and creates a clean linear commit history without creating merge commits.

---

# Interview One-Liner

Git Merge preserves branch history by creating a merge commit, whereas Git Rebase rewrites history by replaying commits on top of another branch to create a clean and linear commit history.