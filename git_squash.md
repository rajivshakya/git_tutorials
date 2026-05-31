# Interview Question: What is Git Squash?

## Answer

Git Squash is a technique used to combine multiple commits into a single commit.

It is commonly used before merging a feature branch into the main branch to keep the commit history clean and meaningful.

### Important Note

```text
Git Squash is NOT a standalone Git command.
```

Instead, squashing is performed using:

```bash
git rebase -i
```

or

```bash
git merge --squash
```

---

# Why Do We Use Git Squash?

During development, developers often create many small commits such as:

```text
Added VPC
Fixed VPC CIDR
Added Public Subnet
Fixed Route Table
Removed Debug Code
```

These commits are useful during development but make the Git history noisy.

Before merging the feature branch into the main branch, we can combine them into a single meaningful commit.

---

# Practical Example

## Main Branch

```text
A --- B
```

Where:

```text
A = Initial Commit
B = Added Terraform Project Structure
```

---

## Feature Branch

A developer creates a feature branch from commit B.

```text
A --- B --- C1 --- C2 --- C3 --- C4
```

Where:

```text
C1 = Added VPC
C2 = Fixed VPC CIDR
C3 = Added Public Subnet
C4 = Fixed Route Table
```

---

# Scenario 1: Normal Merge

Switch to main:

```bash
git checkout main
```

Merge feature:

```bash
git merge feature
```

Result:

```text
A --- B --- C1 --- C2 --- C3 --- C4
```

All commits become part of the main branch.

Git history contains every commit.

---

# Problem with Normal Merge

The main branch now contains many small commits:

```text
Added VPC
Fixed VPC CIDR
Added Public Subnet
Fixed Route Table
```

This can make Git history difficult to read.

---

# Scenario 2: Squash Merge

Switch to main:

```bash
git checkout main
```

Run:

```bash
git merge --squash feature
```

---

# What Happens Internally?

Git takes all changes from:

```text
C1
C2
C3
C4
```

and combines them together.

However:

```text
No commit is created.
```

Git only places the combined changes into the staging area.

History still remains:

```text
A --- B
```

---

# Verify

Run:

```bash
git status
```

Output:

```text
Changes to be committed:
```

This confirms that Git has staged the combined changes.

---

# Why Do We Need git commit?

Because:

```bash
git merge --squash feature
```

does not create a commit.

It only stages the changes.

Now we create a single meaningful commit.

```bash
git commit -m "Terraform Network Infrastructure"
```

---

# Result

Before:

```text
main

A --- B


feature

A --- B --- C1 --- C2 --- C3 --- C4
```

After:

```text
A --- B --- S1
```

Where:

```text
S1 = Terraform Network Infrastructure
```

The changes from:

```text
C1 + C2 + C3 + C4
```

are now stored in a single commit.

---

# Visual Comparison

## Normal Merge

Before:

```text
main

A --- B


feature

A --- B --- C1 --- C2 --- C3 --- C4
```

After:

```text
A --- B --- C1 --- C2 --- C3 --- C4
```

All commits remain visible.

---

## Squash Merge

Before:

```text
main

A --- B


feature

A --- B --- C1 --- C2 --- C3 --- C4
```

After:

```text
A --- B --- S1
```

Where:

```text
S1 = C1 + C2 + C3 + C4
```

Only one commit appears on the main branch.

---

# Squash Using Interactive Rebase

Another common method is Interactive Rebase.

Suppose history is:

```text
A --- B --- C1 --- C2 --- C3
```

Where:

```text
C1 = Added Login Page
C2 = Fixed Login Validation
C3 = Updated Login CSS
```

Run:

```bash
git rebase -i HEAD~3
```

Git opens:

```text
pick C1 Added Login Page
pick C2 Fixed Login Validation
pick C3 Updated Login CSS
```

Change it to:

```text
pick C1 Added Login Page
squash C2 Fixed Login Validation
squash C3 Updated Login CSS
```

Save and close the editor.

Git will ask for a commit message.

Example:

```text
Added Login Page
Fixed Login Validation
Updated Login CSS
```

Replace with:

```text
Complete Login Feature
```

Save and close.

---

# Result

Before:

```text
A --- B --- C1 --- C2 --- C3
```

After:

```text
A --- B --- S1
```

Where:

```text
S1 = Complete Login Feature
```

The changes from C1, C2, and C3 are combined into a single commit.

---

# When Should We Use Git Squash?

Use Git Squash when:

- Cleaning up feature branch history.
- Before creating a Pull Request.
- Combining multiple small commits into one meaningful commit.
- Removing unnecessary "fix typo" or "debug" commits.

---

# Advantages of Git Squash

- Cleaner Git history.
- Easier code review.
- One feature = one commit.
- Easier rollback in production.

---

# Disadvantages of Git Squash

- Rewrites commit history.
- Individual commit details are lost.
- May require force push if branch is already pushed.

---

# Interview Question

## Is Git Squash a Command?

No.

Git Squash is not a standalone Git command.

It is a process of combining multiple commits into a single commit.

It is commonly performed using:

```bash
git rebase -i
```

or

```bash
git merge --squash
```

---

# Interview One-Liner

Git Squash is the process of combining multiple commits into a single commit to create a clean and meaningful Git history before merging code into the main branch.