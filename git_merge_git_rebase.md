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
A --- B --- C
            ↑
          main
```

Suppose:

```text
A = Initial Commit
B = Added README
C = Added Application Code
```

Create a feature branch:

```bash
git checkout -b feature
```

Current History:

```text
A --- B --- C
            ↑
      main, feature
```

---

## Step 2: Add Commits on Feature Branch

```bash
git commit -m "Feature Commit 1"
git commit -m "Feature Commit 2"
git commit -m "Feature Commit 3"
```

History:

```text
A --- B --- C
            \
             D --- E --- F
                         ↑
                      feature
```

---

## Step 3: Main Branch Receives New Commits

Switch to main:

```bash
git checkout main
```

Add two commits:

```bash
git commit -m "Main Commit 1"
git commit -m "Main Commit 2"
```

History:

```text
A --- B --- C --- G --- H
                        ↑
                      main

            \
             D --- E --- F
                         ↑
                      feature
```

Now both branches have diverged.

---

## Step 4: Merge Feature into Main

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
A --- B --- C --- G --- H -------- M
            \                    /
             D --- E --- F ------
```

Where:

```text
M = Merge Commit
```

Git combines both histories and creates a merge commit.

---

## Verify

```bash
git log --oneline --graph
```

Output:

```text
*   M Merge branch 'feature'
|\
| * F Feature Commit 3
| * E Feature Commit 2
| * D Feature Commit 1
* | H Main Commit 2
* | G Main Commit 1
|/
* C Added Application Code
* B Added README
* A Initial Commit
```

# Git Rebase command

Let's use the same history before merge.

Current History:

```text
A --- B --- C --- G --- H
                        ↑
                      main

            \
             D --- E --- F
                         ↑
                      feature
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

Git temporarily removes:

```text
D
E
F
```

History becomes:

```text
A --- B --- C --- G --- H
```

Git moves the feature branch pointer to H.

Then Git reapplies commits one by one.

---

## Reapply Commit D

```text
A --- B --- C --- G --- H --- D'
```

---

## Reapply Commit E

```text
A --- B --- C --- G --- H --- D' --- E'
```

---

## Reapply Commit F

```text
A --- B --- C --- G --- H --- D' --- E' --- F'
```

---

# Result After Rebase

```text
A --- B --- C --- G --- H --- D' --- E' --- F'
                                            ↑
                                         feature
```

Notice:

```text
D' ≠ D
E' ≠ E
F' ≠ F
```

Git recreated all feature commits because their parent commits changed.

---

# Why Does Rebase Create New Commits?

Before Rebase:

```text
D Parent = C
E Parent = D
F Parent = E
```

After Rebase:

```text
D' Parent = H
E' Parent = D'
F' Parent = E'
```

Since parent commits changed, Git had to create new commits with new commit hashes.

---

## Verify

```bash
git log --oneline --graph
```

Output:

```text
* F' Feature Commit 3
* E' Feature Commit 2
* D' Feature Commit 1
* H Main Commit 2
* G Main Commit 1
* C Added Application Code
* B Added README
* A Initial Commit
```