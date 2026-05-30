# Interview Question: What is the Difference Between Git Merge and Git Rebase?

## Answer

Both **Git Merge** and **Git Rebase** are used to integrate changes from one branch into another branch.

The major difference is:

- **Git Merge** preserves branch history.
- **Git Rebase** rewrites commit history and creates a clean linear history.

Before understanding Merge vs Rebase, it is important to understand **Fast-Forward Merge** and **Non-Fast-Forward Merge**.

---

# Scenario 1: Fast-Forward Merge

## Step 1: Initial Repository

```bash
git init

echo "Version 1" > app.txt
git add .
git commit -m "Initial Commit"
```

History:

```text
A
↑
main
```

Create a feature branch:

```bash
git checkout -b feature
```

Add two commits:

```bash
echo "Feature Change 1" >> app.txt
git commit -am "Feature Commit 1"

echo "Feature Change 2" >> app.txt
git commit -am "Feature Commit 2"
```

History:

```text
A --- B --- C
↑           ↑
main      feature
```

Main branch is still at A.

---

## Merge Feature into Main

Switch to main:

```bash
git checkout main
```

Merge feature:

```bash
git merge feature
```

---

## Result

```text
A --- B --- C
            ↑
     main, feature
```

Git simply moves the main pointer from A to C.

### Important Point

No merge commit is created.

This is called a **Fast-Forward Merge** because Git can simply move the branch pointer forward.

---

## Verify

```bash
git log --oneline --graph
```

Output:

```text
* C Feature Commit 2
* B Feature Commit 1
* A Initial Commit
```

Notice:

There is no merge commit.

---

# Scenario 2: Non-Fast-Forward Merge (3-Way Merge)

This is where Git creates a merge commit.

---

## Step 1: Initial History

```text
A
↑
main
```

Create feature branch:

```bash
git checkout -b feature
```

Add commit:

```bash
echo "Feature Change" >> app.txt
git commit -am "Feature Commit"
```

History:

```text
A --- B
      ↑
   feature
```

---

## Step 2: Add Commit to Main

Switch to main:

```bash
git checkout main
```

Add another commit:

```bash
echo "Main Change" >> app.txt
git commit -am "Main Commit"
```

History becomes:

```text
A --- C
↑
main

 \
  B
  ↑
feature
```

Or:

```text
A --- C
 \     
  B
```

Now both branches have different commits.

Branches have diverged.

---

## Step 3: Merge Feature into Main

Switch to main:

```bash
git checkout main
```

Run:

```bash
git merge feature
```

---

## Result

```text
A -------- C -------- M
 \                  /
  B ---------------
```

Where:

```text
M = Merge Commit
```

Git cannot simply move the branch pointer.

Git must combine changes from both branches.

Therefore Git creates a new merge commit.

---

## Verify

```bash
git log --oneline --graph
```

Output:

```text
*   M Merge branch 'feature'
|\
| * B Feature Commit
* | C Main Commit
|/
* A Initial Commit
```

---

# Git Rebase

Now let's use the same diverged history.

Before Rebase:

```text
A --- C
 \
  B
```

Where:

```text
main    = C
feature = B
```

Switch to feature:

```bash
git checkout feature
```

Run:

```bash
git rebase main
```

---

# What Happens Internally?

## Step 1

Git temporarily removes commit B.

```text
A --- C
```

---

## Step 2

Git moves the feature branch to C.

```text
A --- C
```

---

## Step 3

Git reapplies B on top of C.

```text
A --- C --- B'
```

Notice:

```text
B' ≠ B
```

Git creates a brand-new commit.

The commit content remains the same, but the commit hash changes.

---

# Result After Rebase

```text
A --- C --- B'
```

History becomes completely linear.

No merge commit is created.

---

## Verify

```bash
git log --oneline --graph
```

Output:

```text
* B' Feature Commit
* C Main Commit
* A Initial Commit
```

---

# Visual Comparison

## Fast-Forward Merge

Before:

```text
A --- B --- C
↑           ↑
main      feature
```

After:

```text
A --- B --- C
            ↑
     main, feature
```

No merge commit.

---

## Non-Fast-Forward Merge

Before:

```text
A --- C

 \
  B
```

After:

```text
A -------- C -------- M
 \                  /
  B ---------------
```

Merge commit created.

---

## Rebase

Before:

```text
A --- C

 \
  B
```

After:

```text
A --- C --- B'
```

No merge commit.

Linear history.

---

# Real DevOps Example

Suppose while working on a Terraform feature branch, other team members push commits to main.

Main:

```text
A --- B --- C
```

Feature:

```text
A
 \
  D --- E
```

---

## Using Merge

```bash
git checkout feature
git merge main
```

Result:

```text
A --- B --- C -------- M
 \                   /
  D --- E ----------
```

History preserved.

---

## Using Rebase

```bash
git checkout feature
git rebase main
```

Result:

```text
A --- B --- C --- D' --- E'
```

History becomes linear and cleaner.

---

# When Should We Use Merge?

Use Merge when:

- Working on shared branches.
- History preservation is important.
- Multiple developers work on the same branch.

Example:

```bash
git merge feature
```

---

# When Should We Use Rebase?

Use Rebase when:

- Updating your feature branch with latest main branch changes.
- Keeping Git history clean.
- Preparing a Pull Request.

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

Because rebase rewrites commit history.

---

# Merge vs Rebase Comparison

| Feature | Merge | Rebase |
|----------|--------|---------|
| Creates Merge Commit | Sometimes | No |
| Fast-Forward Possible | Yes | N/A |
| Rewrites History | No | Yes |
| Preserves Branch Structure | Yes | No |
| Linear History | No | Yes |
| Safe for Shared Branches | Yes | No |
| Clean Git Log | No | Yes |

---

# Interview Answer (Short Version)

Git Merge combines branches and preserves history. If the branches have not diverged, Git performs a Fast-Forward Merge without creating a merge commit. If the branches have diverged, Git performs a Non-Fast-Forward Merge and creates a merge commit.

Git Rebase moves commits from one branch on top of another branch, rewrites history, and creates a clean linear commit history without creating merge commits.