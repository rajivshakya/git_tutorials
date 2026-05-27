# SESSION 1 — Git Fundamentals

# Version Control System (VCS)

## Introduction

In software development, source code changes continuously over time.
New features are added, bugs are fixed, and existing functionality is updated regularly.

Now imagine a situation where:

* Multiple developers are working on the same project
* Different versions of files are being created daily
* A recent change breaks the application
* Someone accidentally deletes important code

Without a proper tracking system, managing code becomes very difficult.

To solve these problems, we use a **Version Control System (VCS).**

---

# What is a Version Control System?

A Version Control System is a tool that helps developers:

* Track changes made to source code
* Maintain history of all modifications
* Collaborate with multiple developers
* Restore previous versions when needed
* Manage code efficiently and safely

In simple words:

> A Version Control System keeps track of every change made in a project.

---

# Why Do We Need Version Control?

Before Version Control Systems existed, developers used to manage projects manually.

For example:

```text
project-final
project-final-new
project-final-updated
project-final-v2
project-final-latest
project-final-final
```

This approach created many problems:

* File confusion
* No proper history tracking
* Difficult collaboration
* High risk of overwriting code
* No easy rollback option

As projects and teams became larger, a better solution was needed.

That solution was the **Version Control System.**

---

# Real-World Scenario

Suppose three developers are working on the same application:

* Developer 1 is working on Login Feature
* Developer 2 is fixing Bugs
* Developer 3 is creating Dashboard UI

Now imagine all three developers editing the same files manually.

Problems may occur like:

* One developer overwrites another developer’s code
* Code conflicts happen
* Latest working code may get lost
* No visibility of who changed what

A Version Control System solves all these problems by managing and tracking code changes systematically.

---

# Features of Version Control System

## 1. Change Tracking

Every modification made to the code is tracked.

Example:

* Which file changed
* What changes were made
* Who made the changes
* When the changes were made

---

## 2. Version History

All previous versions of the project are stored safely.

If needed, developers can go back to older versions easily.

---

## 3. Collaboration

Multiple developers can work on the same project simultaneously without affecting each other’s work.

---

## 4. Backup and Recovery

Even if code gets deleted or corrupted, previous versions can be restored.

---

## 5. Branching Support

Developers can work on new features separately without disturbing the main application.

---

# Types of Version Control System

There are mainly three types of Version Control Systems:

1. Local Version Control System
2. Centralized Version Control System (CVCS)
3. Distributed Version Control System (DVCS)

---

# 1. Local Version Control System

## Definition

In a Local Version Control System, all version history is stored on a single computer.

The developer manages versions locally on their own machine.

---

## Working

```text
Developer Machine
 ├── Version 1
 ├── Version 2
 ├── Version 3
```

The system stores different versions of files locally.

---

## Advantages

* Simple to use
* Fast
* No network required

---

## Disadvantages

* No team collaboration
* Risk of data loss if the machine crashes
* No centralized backup

---

## Example

* RCS (Revision Control System)

---

# 2. Centralized Version Control System (CVCS)

## Definition

In Centralized Version Control Systems, a central server stores the complete repository and history.

Developers connect to the central server to download and upload changes.

---

## Working

```text
             Central Server
                   |
    --------------------------------
    |              |              |
Developer 1   Developer 2   Developer 3
```

All developers depend on the central server.

---

## Advantages

* Easy collaboration
* Centralized management
* Better control over permissions

---

## Disadvantages

* If the central server fails, development work is affected
* Requires internet or network connection
* Single point of failure

---

## Examples

* SVN (Subversion)
* CVS

---

# 3. Distributed Version Control System (DVCS)

## Definition

In Distributed Version Control Systems, every developer gets a complete copy of the repository along with its entire history.

This means every developer machine acts as a full backup repository.

---

## Working

```text
               Remote Repository
                    /   |   \
                   /    |    \
          Developer1 Developer2 Developer3

Each developer has a full repository copy
```

Developers can work independently and sync changes later.

---

## Advantages

* Faster operations
* Offline work supported
* Full backup available on every machine
* Better branching and merging support
* No single point of failure

---

## Disadvantages

* Slightly more complex for beginners
* Initial repository cloning may take time for large projects

---

## Examples

* Git
* Mercurial

---

# Comparison Between CVCS and DVCS

| Feature             | CVCS            | DVCS                             |
| ------------------- | --------------- | -------------------------------- |
| Repository Storage  | Central Server  | Every Developer Machine          |
| Internet Dependency | Mostly Required | Not Required for most operations |
| Performance         | Slower          | Faster                           |
| Backup Availability | Single Backup   | Multiple Backups                 |
| Offline Support     | Limited         | Fully Supported                  |
| Failure Risk        | High            | Low                              |

---

# Why Git Became Popular

Git became popular because it provides:

* High performance
* Fast operations
* Powerful branching and merging
* Offline working capability
* Strong backup support
* Better collaboration
* Open-source availability

Today, Git is the most widely used Version Control System in the software industry.

---

# Summary

* A Version Control System helps manage source code changes
* It maintains complete project history
* It improves collaboration among developers
* It provides backup and recovery support
* There are three major types of VCS:

  * Local VCS
  * Centralized VCS
  * Distributed VCS
* Git is a Distributed Version Control System widely used in modern development environments.

# Introduction to Git

## Interview Question: What is Git?

Git is a **Distributed Version Control System (DVCS)** used to track changes in source code during software development.

It helps developers:

* Track code changes
* Maintain project history
* Collaborate with team members
* Restore previous versions
* Work on multiple features safely

Git is fast, lightweight, and widely used in modern software development.

# Small History of Git

Git is a distributed version control system used to track changes in source code during software development.

It helps developers manage code, collaborate with teams, and maintain project history efficiently.

---

# Origin of Git

Git was created by:

```text
Linus Torvalds
```

the creator of the Linux operating system.

---

# Why Git Was Created

Before Git, the Linux kernel project used a version control system called:

```text
BitKeeper
```

In 2005, licensing issues occurred between the Linux community and BitKeeper.

As a result, Linus Torvalds decided to create a new version control system with the following goals:

- High performance
- Distributed architecture
- Strong branching support
- Fast operations
- Data integrity

---

# Birth of Git

Git was officially created in:

```text
2005
```

---

# Meaning of the Name "Git"

Linus Torvalds jokingly explained that:

```text
"Git" is British slang for an unpleasant or foolish person.
Example:
“Don’t be such a git!”
→ “इतने बेवकूफ मत बनो!”
```

He humorously named it after himself.

---

# Key Features Introduced by Git

Git introduced several powerful concepts:

- Distributed version control
- Fast branching and merging
- Local repositories
- Cheap commits
- Strong data integrity using SHA hashing

---

# Growth of Git

Git quickly became popular because it was:

- Fast
- Reliable
- Open source
- Flexible for teams

Today Git is the most widely used version control system in the world.

---

# GitHub and Git Popularity

In 2008, GitHub was launched.

GitHub made Git collaboration much easier by providing:

- Remote repositories
- Pull requests
- Collaboration tools
- Code hosting

This greatly increased Git adoption worldwide.

---

# Today

Git is now used by:

- Software companies
- Cloud engineers
- DevOps engineers
- Open-source communities
- Students and educators

It is considered an essential skill in software development and DevOps.

---

# Short Timeline

| Year | Event |
|---|---|
| Before 2005 | Linux used BitKeeper |
| 2005 | Git created by Linus Torvalds |
| 2008 | GitHub launched |
| Present | Git became industry standard |

---

# Final Summary

Git was created by Linus Torvalds in 2005 to manage Linux kernel development after issues with BitKeeper.

It became popular because of its speed, distributed nature, and powerful branching capabilities, and today it is the industry-standard version control system.
---

# Understanding Git Workflow

Before learning Git commands, it is very important to understand how Git works internally.

Git mainly works with the following areas:

1. Working Directory
2. Staging Area
3. Local Repository
4. Remote Repository

Understanding these components makes Git much easier to learn.

---

# Git Architecture

```text id="zv4twj"
                Remote Repository (GitHub/GitLab/Bitbucket)
                               ^
                               |
                           git push
                               |
                           git pull
                               |
+-------------------------------------------------------------+
|                     Local Machine                           |
|                                                             |
|   Working Directory ---> Staging Area ---> Local Repository |
|         |                   |                  |             |
|         |                   |                  |             |
|      git add            git commit         git push         |
|                                                             |
+-------------------------------------------------------------+
```

---

# 1. Working Directory

## Definition

The Working Directory is the place where developers create and modify project files.

It contains the actual files and folders of the project.

Example:

```text id="2n6ehn"
project/
 ├── app.py
 ├── index.html
 ├── style.css
```

When you create or modify files, the changes first happen inside the Working Directory.

---

## Real-World Example

Suppose you edit a file:

```bash
nano app.py
```

At this stage:

* Changes exist only in the Working Directory
* Git is aware that files changed
* Changes are NOT yet saved permanently in Git history

---

# 2. Staging Area

## Definition

The Staging Area is an intermediate area where changes are prepared before committing.

It acts like a "waiting room" before saving changes into Git history.

---

## Why Staging Area is Important?

The Staging Area allows developers to:

* Select specific files for commit
* Organize commits properly
* Avoid committing unwanted changes

---

## Moving Changes to Staging Area

```bash
git add filename
```

Example:

```bash
git add app.py
```

Now the file moves from:

```text id="h6n7fi"
Working Directory ---> Staging Area
```

---

# 3. Local Repository

## Definition

The Local Repository is the Git database stored on your local machine.

It contains:

* Commit history
* Branches
* Git metadata
* Project versions

---

## Saving Changes into Local Repository

```bash
git commit -m "Added login feature"
```

Now the changes move from:

```text id="vz5d3m"
Staging Area ---> Local Repository
```

---

# 4. Remote Repository

## Definition

A Remote Repository is a Git repository hosted on a remote server.

Common platforms:

* GitHub
* GitLab
* Bitbucket

It is mainly used for:

* Backup
* Team collaboration
* Sharing code

---

# Git Complete Workflow

```text id="zbf7ur"
Step 1:
Create/Modify Files
        |
        v
Working Directory

Step 2:
git add
        |
        v
Staging Area

Step 3:
git commit
        |
        v
Local Repository

Step 4:
git push
        |
        v
Remote Repository
```

---

# Understanding `git init`

## Interview Question: What is `git init`?

The `git init` command initializes a new Git repository.

It converts a normal project directory into a Git-tracked repository.

---

## Syntax

```bash
git init
```

---

## Example

```bash
mkdir myproject
cd myproject
git init
```

---

## What Happens Internally?

When you run:

```bash
git init
```

Git creates a hidden directory called:

```text id="xsmx5l"
.git
```

This `.git` directory stores:

* Commit history
* Branch information
* Configuration
* Logs
* Git metadata

---

# Flow of `git init`

```text id="nt1w3n"
Before git init

myproject/
 ├── app.py
 ├── index.html

After git init

myproject/
 ├── .git/
 ├── app.py
 ├── index.html
```

Now Git starts tracking this project.

---

# Understanding `git add`

## Interview Question: What is `git add`?

The `git add` command moves changes from the Working Directory to the Staging Area.

---

## Syntax

```bash
git add filename
```

---

## Example

```bash
git add app.py
```

---

## Complete Flow

```text id="v1d4oc"
Modified File
      |
      v
Working Directory
      |
   git add
      |
      v
Staging Area
```

---

# Understanding `git commit`

## Interview Question: What is `git commit`?

The `git commit` command permanently saves staged changes into the Local Repository.

Each commit creates a snapshot of the project.

---

## Syntax

```bash
git commit -m "message"
```

---

## Example

```bash
git commit -m "Initial commit"
```

---

## Commit Flow

```text id="0gjv39"
Staging Area
      |
  git commit
      |
      v
Local Repository
```

---

# Understanding `git push`

## Interview Question: What is `git push`?

The `git push` command uploads local repository commits to the Remote Repository.

---

## Syntax

```bash
git push origin main
```

---

## Push Flow

```text id="o6f7m0"
Local Repository
      |
   git push
      |
      v
Remote Repository
```

---

# Complete Git Lifecycle

```text id="74f1qk"
Create/Modify File
        |
        v
Working Directory
        |
     git add
        |
        v
Staging Area
        |
    git commit
        |
        v
Local Repository
        |
      git push
        |
        v
Remote Repository
```

---

# Example Complete Workflow

## Step 1: Create Project

```bash
mkdir myproject
cd myproject
```

---

## Step 2: Initialize Git

```bash
git init
```

---

## Step 3: Create File

```bash
touch app.py
```

---

## Step 4: Check Status

```bash
git status
```

---

## Step 5: Add File to Staging Area

```bash
git add app.py
```

---

## Step 6: Commit Changes

```bash
git commit -m "Added app.py"
```

---

## Step 7: Push Code to Remote Repository

```bash
git push origin main
```

---

# Summary

* `git init`

  * Initializes a Git repository
  * Creates `.git` directory

* `git add`

  * Moves changes to Staging Area

* `git commit`

  * Saves changes into Local Repository

* `git push`

  * Uploads commits to Remote Repository

Git workflow mainly consists of:

```text id="mmp5p6"
Working Directory
        ↓
Staging Area
        ↓
Local Repository
        ↓
Remote Repository
```

# Understanding Remote Repository in Git

Before learning `git push`, it is important to understand how Git connects a local repository with a remote repository.

A local repository exists on your system, while a remote repository exists on platforms like:

* GitHub
* GitLab
* Bitbucket

To upload code from local machine to remote server, Git first needs a connection between them.

That connection is created using:

```bash id="0zjlwm"
git remote add
```

---

# What is a Remote Repository?

A Remote Repository is a repository hosted on a remote server.

It is mainly used for:

* Backup
* Collaboration
* Code sharing
* Team development

---

# Local vs Remote Repository

```text id="sl5fh6"
Local Repository
----------------
Stored on your computer

Remote Repository
-----------------
Stored on GitHub/GitLab/Bitbucket
```

---

# Git Remote Workflow

```text id="lmd58x"
Local Repository
       |
       | git remote add
       |
       v
Remote Connection
       |
       | git push
       |
       v
Remote Repository
```

---

# Understanding `git remote add`

## What is `git remote add`?

The `git remote add` command connects a local repository to a remote repository.

---

# Syntax

```bash id="w4j2lp"
git remote add <name> <repository-url>
```

---

# Example

```bash id="4yxjkr"
git remote add origin https://github.com/user/myproject.git
```

---

# Explanation

| Part             | Meaning                   |
| ---------------- | ------------------------- |
| `git remote add` | Adds a remote connection  |
| `origin`         | Remote nickname           |
| URL              | Remote repository address |

---

# Why is `origin` Used?

`origin` is simply a default nickname for the remote repository.

You can use any name.

Example:

```bash id="sgbnn8"
git remote add github https://github.com/user/myproject.git
```

But in most projects, `origin` is used as a standard convention.

---

# What Happens Internally?

When you run:

```bash id="czm8p7"
git remote add origin https://github.com/user/myproject.git
```

Git stores the remote repository URL inside:

```text id="w10b7w"
.git/config
```

Now Git knows where to push and pull code.

---

# Understanding `git remote -v`

## What is `git remote -v`?

The `git remote -v` command displays configured remote repositories.

---

# Syntax

```bash id="vjl4gm"
git remote -v
```

---

# Example Output

```text id="nygv40"
origin  https://github.com/user/myproject.git (fetch)
origin  https://github.com/user/myproject.git (push)
```

---

# Meaning of Output

| Term      | Meaning                   |
| --------- | ------------------------- |
| `origin`  | Remote name               |
| `(fetch)` | Used for downloading code |
| `(push)`  | Used for uploading code   |

---

# Understanding `git push`

## Interview Question: What is `git push`?

The `git push` command uploads local commits to the remote repository.

It transfers code from:

```text id="mr9ynw"
Local Repository ---> Remote Repository
```

---

# Syntax

```bash id="mjlwm6"
git push <remote-name> <branch-name>
```

---

# Example

```bash id="jlwm1p"
git push origin main
```

---

# Explanation

| Part       | Meaning                |
| ---------- | ---------------------- |
| `git push` | Upload code            |
| `origin`   | Remote repository name |
| `main`     | Branch name            |

---

# Complete Push Flow

```text id="a3jhr2"
Working Directory
        |
     git add
        |
        v
Staging Area
        |
    git commit
        |
        v
Local Repository
        |
     git push
        |
        v
Remote Repository
```

---

# First Push Using `-u`

Usually, during the first push we use:

```bash id="8v3v6f"
git push -u origin main
```

---

# What Does `-u` Mean?

`-u` means:

```text id="h5w7i5"
--set-upstream
```

It links the local branch with the remote branch.

After this, you can simply run:

```bash id="ly8jlwm"
git push
```

instead of:

```bash id="3s49u8"
git push origin main
```

---

# Example Complete Workflow

## Step 1: Create Project

```bash id="n15vll"
mkdir myproject
cd myproject
```

---

## Step 2: Initialize Git

```bash id="0s13ol"
git init
```

---

## Step 3: Create File

```bash id="kt4s18"
touch app.py
```

---

## Step 4: Add File

```bash id="80qeb5"
git add .
```

---

## Step 5: Commit Changes

```bash id="69mjlwm"
git commit -m "Initial commit"
```

---

## Step 6: Add Remote Repository

```bash id="hh2a9d"
git remote add origin https://github.com/user/myproject.git
```

---

## Step 7: Verify Remote

```bash id="my0j5u"
git remote -v
```

---

## Step 8: Push Code

```bash id="fjlwmr"
git push -u origin main
```

---

# Important Commands Related to Remote Repository

---

# 1. View Remote Repository

```bash id="xjlwmz"
git remote -v
```

Displays configured remotes.

---

# 2. Remove Remote Repository

```bash id="g9c4ae"
git remote remove origin
```

Removes remote connection.

---

# 3. Change Remote Repository URL

```bash id="l67n8r"
git remote set-url origin https://github.com/user/newrepo.git
```

Updates remote repository URL.

---

# 4. Rename Remote

```bash id="crzjlwm"
git remote rename origin github
```

Changes remote name.

---

# 5. Show Remote Details

```bash id="s7hjlwm"
git remote show origin
```

Displays detailed remote information.

---

# Common Errors During `git push`

# 1. Remote Repository Does Not Exist

```text id="pz4p1j"
remote: Repository not found
```

## Cause

* Wrong repository URL
* Repository not created on GitHub

---

# 2. Authentication Failed

```text id="zjlwm2"
Authentication failed
```

## Cause

* Wrong credentials
* Invalid token/password

---

# 3. Permission Denied

```text id="jlwmc9"
Permission denied
```

## Cause

* No access to repository

---

# 4. Branch Does Not Exist

```text id="jlwmq7"
src refspec main does not match any
```

## Cause

* No commit created yet
* Wrong branch name

---

# Important Concept

## `git push` only uploads committed changes.

This means:

```text id="jlwmv4"
Working Directory ❌
Staging Area ❌
Local Repository ✅
```

Only committed changes are pushed to the remote repository.

---

# Summary

* `git remote add`

  * Connects local repository to remote repository

* `git remote -v`

  * Displays remote repository details

* `git push`

  * Uploads local commits to remote repository

* `git push -u origin main`

  * Sets upstream tracking for future pushes

---

# Complete Git Push Architecture

```text id="q4dxws"
                Remote Repository
                       ^
                       |
                   git push
                       |
                Local Repository
                       ^
                       |
                  git commit
                       |
                  Staging Area
                       ^
                       |
                    git add
                       |
                Working Directory
```
# Git Internal Storage

After running `git init`, Git creates a hidden `.git` folder.  
This folder stores all Git repository data.

## Important Components

| Git Concept | Location inside `.git` |
|---|---|
| Staging Area | `.git/index` |
| Local Repository (commits/data) | `.git/objects/` |
| Branches | `.git/refs/heads/` |
| Current Branch Pointer | `.git/HEAD` |
| Tags | `.git/refs/tags/` |
| Repository Configuration | `.git/config` |
| Logs / Reflog | `.git/logs/` |

## Git Workflow

```text
Working Directory
       ↓
    git add
       ↓
.git/index
(Staging Area)
       ↓
  git commit
       ↓
.git/objects
(Local Repository)
```

---

# SESSION 2 — Branching, Merge and Rebase

# Understanding Git Branches, Commits and Important Industry-Level Git Commands

Before learning advanced Git commands, it is very important to understand how Git internally works with:

* Commits
* Branches
* Branch workflows
* Code history
* Collaboration

These concepts are the foundation of real-world Git usage.

---

# Understanding Git Commits

## Interview Question: What is a Commit?

A commit is a snapshot of your project at a particular point in time.

Whenever developers save changes into Git using:

```bash id="w9j4d2"
git commit -m "message"
```

Git creates a commit.

---

# Simple Definition

> A commit is a saved version of the project.

---

# Real Example

Suppose we create a project.

---

# Step 1: Create Project

```bash id="t4x8p1"
mkdir myproject
cd myproject
git init
```

---

# Step 2: Create File

```bash id="u2m6q9"
touch app.py
```

---

# Step 3: Add Content

```python id="n8r5w3"
print("Hello World")
```

---

# Step 4: Add File to Staging Area

```bash id="v7k2y1"
git add app.py
```

---

# Step 5: Create Commit

```bash id="x3p9m6"
git commit -m "Initial commit"
```

---

# What Happens Internally?

Before commit:

```text id="f6w1q8"
Working Directory
        |
    git add
        |
        v
Staging Area
```

After commit:

```text id="p4z7n2"
Local Repository
        |
     Commit Created
```

Git permanently saves project snapshot into local repository.

---

# Commit Diagram

```text id="c9m5v1"
Commit A ---> Commit B ---> Commit C
```

Each commit stores:

* Code snapshot
* Commit message
* Timestamp
* Author details

---

# Viewing Commit History

```bash id="r8x2q4"
git log
```

---

# Short Format

```bash id="j5w9m3"
git log --oneline
```

Example Output:

```text id="n1v7k8"
a1b2c3d Initial commit
f4g5h6i Added login feature
```

---

# Understanding Git Branches

## Interview Question: What is a Branch?

A branch is an independent line of development.

It allows developers to work separately without affecting the main code.

---

# Why Branches Are Important?

Suppose:

* Application is running in production
* Team wants to add new features
* Bugs need fixing

If everyone directly modifies production code:

* Application may break
* Unstable code may reach users

Branches solve this problem.

---

# Main Branch

By default Git creates:

```text id="d7v4p2"
main
```

This branch usually contains:

* Stable code
* Production-ready code

---

# Main Branch Diagram

```text id="b8n3q1"
main
  |
  A ---- B ---- C
```

---

# Creating Feature Branch

Suppose developer wants to work on Login Feature.

---

# Create Branch

```bash id="m2q8x5"
git checkout -b feature-login
```

---

# What Happens Internally?

Git creates a new branch pointer.

---

# Branch Structure

```text id="s4k9w7"
main
  |
  A ---- B

feature-login
            \
             C ---- D
```

Now:

* main branch remains stable
* feature-login branch contains new feature development

---

# View Branches

```bash id="h1x6v9"
git branch
```

Example Output:

```text id="y8p2m4"
* feature-login
  main
```

`*` indicates current branch.

---

# Switching Branches

```bash id="q6n3w1"
git checkout main
```

or modern command:

```bash id="k4v8p7"
git switch main
```

---

# Merging Branches

After feature testing completes:

```bash id="c5m1x9"
git merge feature-login
```

---

# Merge Diagram

Before Merge:

```text id="v7n2k5"
main
  |
  A ---- B

feature-login
            \
             C ---- D
```

After Merge:

```text id="z1p8q4"
main
  |
  A ---- B -------- E
            \      /
             C ---- D
```

`E` becomes merge commit.

---

# Real Industry Branch Types

| Branch    | Purpose                 |
| --------- | ----------------------- |
| main      | Production code         |
| develop   | Integration branch      |
| feature-* | New feature development |
| bugfix-*  | Bug fixing              |
| hotfix-*  | Urgent production fix   |
| release-* | Release preparation     |

---

# Important Industry-Level Git Commands

---

# 1. git clone

## What is `git clone`?

The `git clone` command copies a remote repository to your local machine.

---

# Syntax

```bash id="n7q3w5"
git clone <repository-url>
```

---

# Example

```bash id="t8v1m4"
git clone https://github.com/user/project.git
```

---

# What Happens Internally?

```text id="j2x7p9"
Remote Repository
        |
    git clone
        |
        v
Local Repository Created
```

Git automatically:

* Downloads project files
* Creates local repository
* Configures remote origin

---

# Industry Use Case

Used when:

* Joining new project
* Setting up development environment
* Downloading existing repositories

---

# 2. git pull

## Interview Question: What is `git pull`?

The `git pull` command downloads latest changes from remote repository and merges them into current branch.

---

# Syntax

```bash id="p9k2v6"
git pull origin main
```

---

# Example

Suppose another developer pushed new code to GitHub.

To get latest code:

```bash id="x4m7q1"
git pull origin main
```

---

# What Happens Internally?

```text id="s6w8n3"
Remote Repository
        |
    git fetch
        |
    git merge
        |
        v
Current Branch Updated
```

`git pull` internally performs:

* git fetch
* git merge

---

# Industry Use Case

Developers usually run:

```bash id="d1v5k8"
git pull
```

before starting daily work.

---

# 3. git fetch

## Interview Question: What is `git fetch`?

Downloads latest changes from remote repository WITHOUT merging.

---

# Syntax

```bash id="g7p2x9"
git fetch
```

---

# Example

```bash id="l5n1w6"
git fetch origin
```

---

# What Happens Internally?

```text id="v3m8q2"
Remote Repository
        |
    git fetch
        |
        v
Downloads changes only
```

Current working branch remains unchanged.

---

# Difference Between Pull and Fetch

| Command   | Downloads Code | Automatically Merge |
| --------- | -------------- | ------------------- |
| git fetch | Yes            | No                  |
| git pull  | Yes            | Yes                 |

---

# Industry Use Case

Used when developers want to:

* review changes first
* avoid automatic merge conflicts

---

# 4. git branch

## What is `git branch`?

Used to create and manage branches.

---

# Create Branch

```bash id="w4x9m1"
git branch feature-payment
```

---

# What Happens?

Git creates a new branch pointer.

---

# View Branches

```bash id="k8q2v5"
git branch
```

---
# Rename Branch

First, switch to the branch that you want to rename.

For example, if you want to rename the `master` branch to `main`:

```bash
git switch master
# or
git checkout master

git branch -m main
```

---

# Explanation

- `git switch master`  
  Switches to the `master` branch.

- `git branch -m main`  
  Renames the current branch from `master` to `main`.

---

# Verify Renamed Branch

Run:

```bash
git branch
```

Example output:

```text
* main
```

---

# Important Note

This command only renames the local branch.

To update the remote repository as well, run:

```bash
git push -u origin main
```

Then optionally delete the old remote branch:

```bash
git push origin --delete master
```
# Delete Branch

```bash id="m6p1x7"
git branch -d feature-payment
```

---

# Industry Use Case

Used for:

* feature development
* bug fixing
* release management

---

# 5. git checkout

## What is `git checkout`?

Used to switch branches.

---

# Switch Branch

```bash id="r2n7w4"
git checkout feature-payment
```

---

# Create and Switch Together

```bash id="y9v3m6"
git checkout -b feature-payment
```

---

# What Happens Internally?

Git:

* switches HEAD pointer
* updates working directory files

---

# Industry Use Case

Developers frequently switch between:

* feature branches
* production branches
* bugfix branches

---

# 6. git switch

Modern alternative to:

```bash id="h1q8x5"
git checkout
```

---

# Syntax

```bash id="c4m7v2"
git switch main
```

---

# Create and Switch

```bash id="p6x1n9"
git switch -c feature-api
```

---

# Industry Use Case

Preferred in modern Git versions for cleaner branch switching.

---
# Different Ways to Create a New Branch in Git

Git provides multiple commands to create branches.

The most commonly used commands are:

1. `git checkout -b <branch_name>`
2. `git branch <branch_name>`
3. `git switch -c <branch_name>`

---

# 1. `git checkout -b <branch_name>`

## Syntax

```bash
git checkout -b <branch_name>
```

---

## Example

```bash
git checkout -b feature/login
```

---

## What Does It Do?

This command:

- creates a new branch
- automatically switches to that branch

---

## Equivalent To

```bash
git branch feature/login
git checkout feature/login
```

---

# 2. `git branch <branch_name>`

## Syntax

```bash
git branch <branch_name>
```

---

## Example

```bash
git branch feature/login
```

---

## What Does It Do?

This command:

- only creates a new branch
- does NOT switch to that branch

You remain on the current branch.

---

## To Switch After Creating

```bash
git checkout feature/login
```

or

```bash
git switch feature/login
```

---

# 3. `git switch -c <branch_name>`

## Syntax

```bash
git switch -c <branch_name>
```

---

## Example

```bash
git switch -c feature/login
```

---

## What Does It Do?

This command:

- creates a new branch
- automatically switches to it

It is the modern alternative to:

```bash
git checkout -b
```

---

# Difference Between These Commands

| Command | Creates Branch | Switches Branch |
|---|---|---|
| `git checkout -b` | Yes | Yes |
| `git branch` | Yes | No |
| `git switch -c` | Yes | Yes |

---

# Recommended Usage

| Situation | Recommended Command |
|---|---|
| Create branch only | `git branch` |
| Create + switch (older style) | `git checkout -b` |
| Create + switch (modern style) | `git switch -c` |

---

# Important Note

`git switch` was introduced to simplify branch switching because:

```bash
git checkout
```

was doing multiple jobs like:

- switching branches
- restoring files
- checking out commits

So Git introduced:

- `git switch` → for branches
- `git restore` → for files

---

# Final Recommendation

Modern Git workflows generally prefer:

```bash
git switch -c <branch_name>
```

because it is more readable and purpose-specific.

# 7. git merge

# Understanding git merge

## Interview Question: What is `git merge`?

The `git merge` command is used to combine changes from one branch into another branch.

In simple words:

> Git merge joins two branches together.

It is one of the most important commands used in real-world software development and DevOps projects.

---

# Why Do We Use git merge?

Merge is mainly used when:

* Feature development is completed
* Bug fixes are completed
* Pull Request is approved
* Code needs to move into main branch
* Multiple developers are working on same project

---

# Important Concept

## git merge preserves original history.

This means:

* Original commits remain unchanged
* Original commit IDs remain same
* Git combines branch histories together

---

# Real Industry Scenario

Suppose:

* `main` branch contains stable production code
* Developer wants to create Login Feature

Instead of directly modifying main branch, developer creates separate feature branch.

---

# Initial Structure

```text id="n7q2m5"
main
  |
  A ---- B
```

---

# Step 1: Create Feature Branch

```bash id="x4m8q1"
git checkout -b feature-login
```

---

# Step 2: Add New Feature Commits

Developer works on Login Feature.

```bash id="q5v1m7"
git commit -m "Created login page"

git commit -m "Added login validation"
```

---

# Branch Structure

```text id="t8q3m4"
main
  |
  A ---- B

feature-login
            \
             C ---- D
```

---

# Explanation

| Commit | Description            |
| ------ | ---------------------- |
| A      | Initial project        |
| B      | Stable code            |
| C      | Login page created     |
| D      | Login validation added |

---

# Goal

Now we want:

* Login feature should become part of main branch

---

# Step 3: Switch to Main Branch

```bash id="k1m7q5"
git checkout main
```

---

# Step 4: Merge Feature Branch

```bash id="r4v8q2"
git merge feature-login
```

---

# What Happens Internally?

Git:

1. Takes changes from feature branch
2. Combines them into main branch
3. Preserves original commits
4. Updates main branch history

---

# Final Structure After Merge

```text id="y2q8m1"
A ---- B -------- M
       \         /
        C ----- D
```

---

# Important Observation

Notice:

```text id="p6m1q7"
M
```

This is called:

```text id="x8v4q2"
Merge Commit
```

---

# What is Merge Commit?

Merge commit is a special commit created by Git when it combines histories from two different branches.

Unlike normal commits:

* merge commit has two parents

Example:

```text id="m5q1v8"
Parent 1 = main branch latest commit
Parent 2 = feature branch latest commit
```

---

# Why Merge Commit is Important?

Merge commit helps:

* preserve branch history
* identify feature integrations
* maintain project development flow
* audit project changes later

---

# Important Point

During merge:

```text id="n3m7q4"
Original commits remain unchanged
```

This means:

* `C` remains `C`
* `D` remains `D`

Git does NOT recreate commits.

---

# Why git merge is Safe?

Because:

* commit history is preserved
* commit IDs remain same
* no history rewriting happens

That is why merge is considered safe for:

* shared branches
* team projects
* production repositories

---

# Fast-Forward Merge

Now let us understand another important concept.

---

# What is Fast-Forward Merge?

Fast-forward merge happens when:

* target branch has not changed
* after feature branch creation

In this case Git simply moves branch pointer forward.

---

# Example

Initial Structure:

```text id="r7v2m5"
A --- B   (main)
         \
          C --- D   (feature-login)
```

---

# Important Observation

After branch creation:

* main branch has NO new commits

---

# Merge Command

```bash id="t4m8q1"
git checkout main
git merge feature-login
```

---

# What Happens?

Git sees:

```text id="x1q7m4"
main can directly move forward
```

So Git:

* does NOT create merge commit
* simply moves main pointer forward

---

# Final Structure

```text id="p5v8q2"
A --- B --- C --- D
```

---

# Important Observation

✅ Linear history
✅ No merge commit
✅ Original commits preserved

This is called:

```text id="m2q9v5"
Fast-Forward Merge
```

---

# Non Fast-Forward Merge

Now let us understand when merge commit is created.

---

# Initial Structure

```text id="k6v1q8"
A --- B --- E   (main)
         \
          C --- D   (feature-login)
```

---

# Important Observation

Now:

* main branch also contains new commit `E`
* feature branch contains commits `C` and `D`

Both branches diverged.

---

# Merge Command

```bash id="r3m7q1"
git checkout main
git merge feature-login
```

---

# What Happens?

Git now needs to:

* combine two different histories

So Git creates:

```text id="y8q2m4"
Merge Commit
```

---

# Final Structure

```text id="m7q2v5"
A --- B --- E -------- M
         \            /
          C -------- D
```

---

# Important Observation

✅ Merge commit created
✅ Branch structure preserved
✅ Feature history visible

---

# Why Companies Sometimes Prefer Merge Commits?

Because merge commits:

* preserve exact feature history
* show feature integration point
* help in auditing
* improve traceability

---

# Merge Conflict

Sometimes:

* same file
* same lines

are modified in both branches.

Then Git becomes confused.

---

# Conflict Example

```text id="x4m8q1"
CONFLICT (content): Merge conflict in app.py
```

---

# What Happens During Conflict?

Git pauses merge process and asks developer to manually resolve conflict.

---

# Conflict Example File

```python id="q5v1m7"
<<<<<<< HEAD
Code from main branch
=======
Code from feature branch
>>>>>>> feature-login
```

---

# Resolve Conflict

Developer manually edits file.

Example:

```python id="t8q3m4"
Final combined code
```

---

# Add Fixed File

```bash id="k1m7q5"
git add app.py
```

---

# Complete Merge

```bash id="r4v8q2"
git commit
```

Git now creates merge commit.

---

# Important Merge Commands

---

# Start Merge

```bash id="y2q8m1"
git merge feature-login
```

---

# Abort Merge

```bash id="p6m1q7"
git merge --abort
```

Cancels merge process.

---

# Force Merge Commit

```bash id="x8v4q2"
git merge --no-ff feature-login
```

Creates merge commit even if fast-forward is possible.

---

# Why `--no-ff` is Used?

Companies use it to:

* preserve feature branch history
* clearly identify feature integrations

---

# Merge Workflow in Real Industry

```text id="m5q1v8"
Create Feature Branch
        |
Code Changes
        |
git add
        |
git commit
        |
Testing
        |
Pull Request
        |
Code Review
        |
git merge
        |
Deployment
```

---

# Important Industry Best Practices

## Use Separate Feature Branches

Example:

```text id="n3m7q4"
feature-login
feature-payment
bugfix-auth
```

---

# Pull Latest Code Before Merge

```bash id="r7v2m5"
git pull origin main
```

---

# Resolve Conflicts Carefully

Always verify:

* business logic
* configuration files
* deployment scripts

---

# Prefer Merge for Shared Branches

Because merge:

* preserves history
* avoids history rewriting
* safer for teams

---

# Summary

## git merge

* Combines one branch into another
* Preserves original commit history
* Usually creates merge commit
* Safe for team collaboration
* Commonly used after Pull Request approval

---

# Fast-Forward Merge

* No merge commit created
* Happens when target branch has no new commits
* History becomes linear

---

# Non Fast-Forward Merge

* Merge commit created
* Preserves branch structure
* Useful for auditing and tracking

---

# Final Easy Understanding

## Fast-Forward Merge

```text id="t4m8q1"
"Simply move branch pointer forward"
```

---

## Non Fast-Forward Merge

```text id="x1q7m4"
"Combine two diverged branch histories"
```

# 8. git rebase
# Understanding git rebase in Detail

## Interview Question: What is `git rebase`?

The `git rebase` command is used to move or replay commits from one branch on top of another branch.

In simple words:

> Rebase takes commits from the current branch and places them on top of another branch.

---

# Why Do We Use Rebase?

Rebase is mainly used to:

* Synchronize feature branch with latest main branch
* Create cleaner commit history
* Avoid unnecessary merge commits
* Maintain linear project history
* Simplify debugging and tracking

---

# Simple Understanding

Suppose:

* You created a feature branch
* Meanwhile other developers pushed new commits into main branch

Now your feature branch becomes outdated.

Using rebase:

* your feature commits are moved on top of latest main branch commits

---

# Important Concept

## Rebase always changes the CURRENT branch.

Command:

```bash id="v4m8q1"
git rebase <target-branch>
```

Meaning:

```text id="q7x2m5"
Take current branch commits
and replay them on top of target branch
```

---

# What Happens Internally During Rebase?

When rebase runs:

1. Git temporarily removes commits from current branch
2. Moves current branch to target branch latest commit
3. Replays removed commits one by one
4. Creates NEW commit IDs

---

# Why New Commit IDs Are Created?

Because commit parent changes.

In Git:

```text id="m2v9q4"
Parent change = New Commit
```

That is why rebase is called:

```text id="x5q1m7"
History Rewriting Operation
```

---

# Example 1:

# Rebase from Feature Branch (Most Common Industry Workflow)

---

# Initial Structure

Suppose project structure is:

```text id="n8q4m2"
main
  |
  A ---- B ---- C

feature-login
              \
               D ---- E
```

---

# Explanation

| Commit | Description               |
| ------ | ------------------------- |
| A      | Initial project           |
| B      | Database setup            |
| C      | API changes added in main |
| D      | Login page created        |
| E      | Login validation added    |

---

# Important Observation

Feature branch was created from:

```text id="y1v6q8"
Commit B
```

But now:

* main branch has moved ahead to `C`
* feature branch is outdated

---

# Goal

We want:

```text id="k4x9m1"
feature-login branch should include latest main branch changes
```

---

# Step 1: Switch to Feature Branch

```bash id="w7m2q5"
git checkout feature-login
```

---

# Step 2: Run Rebase

```bash id="t3v8q1"
git rebase main
```

---

# What Happens Internally?

---

# Step 1: Git Temporarily Removes Feature Commits

Git removes:

```text id="r6q1m4"
D and E
```

---

# Step 2: Feature Branch Moves to Latest Main Commit

Now structure becomes:

```text id="p9x3m7"
A --- B --- C
```

---

# Step 3: Git Replays Feature Commits

Git reapplies:

```text id="n5v2q8"
D and E
```

on top of commit `C`.

---

# Final Structure After Rebase

```text id="x1m7q4"
A --- B --- C --- D' --- E'
```

---

# Important Observation

Notice:

```text id="z8q2m5"
D' and E'
```

These are NEW commits.

Why?

Because:

* parent changed
* commit IDs changed

Earlier:

```text id="c4v9q1"
D parent = B
```

After rebase:

```text id="u7m3q8"
D' parent = C
```

So Git recreated commits.

---

# What Changed After Rebase?

| Before Rebase              | After Rebase           |
| -------------------------- | ---------------------- |
| Feature branch outdated    | Feature branch updated |
| Branch structure separated | Linear history created |
| Old commit IDs             | New commit IDs         |
| Complex history            | Cleaner history        |

---

# Final Result

Now feature branch contains:

* latest main branch changes
* feature commits on top

---

# Why This Is Common in Industry?

This is the most common workflow because:

* feature branch gets latest production code
* conflicts resolved early
* Pull Requests become cleaner
* history becomes easier to understand

---

# Most Common Industry Workflow

```bash id="f2x8m1"
git checkout feature-login
git fetch origin
git rebase origin/main
```

---

# Example 2:

# Rebase from Main Branch (Rare and Dangerous)

Now let us understand opposite scenario.

---

# Initial Structure

```text id="m8q4v2"
main
  |
  A --- B --- C

feature-login
       \
        D --- E
```

---

# Step 1: Switch to Main Branch

```bash id="q5x1m7"
git checkout main
```

---

# Step 2: Run Rebase

```bash id="y2v8q4"
git rebase feature-login
```

---

# Important Understanding

Current branch is:

```text id="k7m3q1"
main
```

So:

* main branch will change
* feature branch remains unchanged

---

# What Happens Internally?

Git checks:

```text id="n4v9q2"
Which commits exist in main but not in feature branch?
```

Answer:

```text id="x6m1q8"
Commit C
```

---

# Step 1: Git Removes Commit C

Temporary structure:

```text id="t8q3m5"
A --- B

feature-login:
A --- B --- D --- E
```

---

# Step 2: Main Branch Moves to Feature Branch Latest Commit

Main moves to:

```text id="v1m7q4"
E
```

---

# Step 3: Git Replays Commit C

Git reapplies commit `C` on top of `E`.

---

# Final Structure After Rebase

```text id="p5x9m2"
A --- B --- D --- E --- C'
```

---

# Important Observation

Notice:

```text id="r3v8q1"
C'
```

This is recreated commit.

Earlier:

```text id="m2q7v5"
C parent = B
```

After rebase:

```text id="x9m4q2"
C' parent = E
```

So Git creates new commit.

---

# What Changed After Rebase?

| Before Rebase        | After Rebase                 |
| -------------------- | ---------------------------- |
| main independent     | main moved on top of feature |
| commit C old history | commit C recreated           |
| feature unchanged    | main rewritten               |

---

# Why This Is Rarely Used?

Because:

* main is usually production branch
* rewriting main history is risky
* other developers may face conflicts
* commit history mismatch may occur

---

# Industry Best Practice

## Recommended

```bash id="u5m1q8"
git checkout feature-branch
git rebase main
```

---

# Avoid

```bash id="n8v3q4"
git checkout main
git rebase feature-branch
```

especially on shared repositories.

---

# Merge vs Rebase

---

# Using Merge

```text id="t4q9m1"
A --- B --- C -------- M
       \              /
        D ---------- E
```

* Keeps original history
* Creates merge commit

---

# Using Rebase

```text id="g7m2q5"
A --- B --- C --- D' --- E'
```

* Cleaner linear history
* No merge commit
* Commits recreated

---

# Important Rebase Commands

---

# Start Rebase

```bash id="k1v8m4"
git rebase main
```

---

# Continue Rebase After Conflict

```bash id="q7m2x5"
git rebase --continue
```

---

# Abort Rebase

```bash id="v4q9m1"
git rebase --abort
```

---

# Skip Problematic Commit

```bash id="x2m7q8"
git rebase --skip
```

---

# Rebase Conflict Example

```text id="m5v1q4"
CONFLICT (content): Merge conflict in app.py
```

This happens when:

* same lines modified in both branches

---

# Resolving Conflict

## Step 1: Edit File Manually

Fix conflict.

---

## Step 2: Add File

```bash id="r8q3m2"
git add app.py
```

---

## Step 3: Continue Rebase

```bash id="n6v1q7"
git rebase --continue
```

---
| Command                 | Meaning                            |
| ----------------------- | ---------------------------------- |
| `git rebase --continue` | Conflict resolved, continue rebase |
| `git rebase --abort`    | Cancel complete rebase             |
| `git rebase --skip`     | Ignore current conflicting commit  |

# Summary

* Rebase moves current branch commits on top of another branch
* Rebase rewrites commit history
* New commit IDs are created
* Feature branch rebasing is common in industry
* Main branch rebasing is risky
* Rebase creates cleaner linear history
* Merge preserves original history
* Rebase is heavily used before Pull Requests and code integration

---

# SESSION 3 — Advanced Git Commands

# 9. git stash

## Interview Question: What is `git stash`?

Temporarily saves uncommitted changes.

---

# Example

Suppose:

* You are working on feature branch
* Production issue suddenly arrives

Save current work:

```bash id="m2v7q4"
git stash
```

---

# What Happens?

Git temporarily stores:

* modified files
* staged changes

Working directory becomes clean.

---

# Restore Stash

```bash id="t5x1n8"
git stash pop
```

---

# Industry Use Case

Very common during:

* urgent production fixes
* branch switching

---

# 10.# git diff Command in Git

`git diff` is used to compare changes in Git.
It shows the line-by-line differences between files, commits, branches, or different Git areas.

# Basic Syntax

```bash
git diff
```

This command shows the difference between:

* the **working directory**
* and the **staging area**

It means:

* changes you made in files
* but have NOT added using `git add`

---

# Example

Suppose a file contains:

```txt
Hello World
```

After modification:

```txt
Hello Git
```

Now run:

```bash
git diff
```

Output:

```diff
-Hello World
+Hello Git
```

## Meaning

* `-` → removed line
* `+` → added line

---

# Important Variations

## 1. Show Unstaged Changes

```bash
git diff
```

Shows changes that are modified but not staged.

---

## 2. Show Staged Changes

```bash
git diff --staged
```

or

```bash
git diff --cached
```

Shows changes that are already added using `git add` and will be included in the next commit.

---

## 3. Compare Two Branches

```bash
git diff main feature
```

Shows differences between the `main` branch and `feature` branch.

---

## 4. Compare Two Commits

```bash
git diff commit1 commit2
```

Example:

```bash
git diff a1b2c3 d4e5f6
```

---

## 5. Compare a Specific File

```bash
git diff file.txt
```

---

# Real-Time Use Cases

`git diff` is commonly used for:

* reviewing code changes
* troubleshooting issues
* verifying changes before deployment
* checking configuration updates
* pull request/code review process

---

# Interview Question

## What is the difference between `git status` and `git diff`?

### Answer:

* `git status` → shows which files are changed
* `git diff` → shows the actual line-by-line changes inside files

---

# Short Definition

> `git diff` is used to compare changes between the working directory, staging area, commits, or branches in Git.


# 11. git reset

# Git Reset Example Explained

`git reset` is used to move HEAD to a previous commit.

Unlike `git revert`, `git reset` can modify Git history.

It is commonly used for local commit cleanup and history rewriting.

---

# Scenario

Suppose we have a simple project.

---

# Step 1: Initial Commit

Create a file and commit it.

```bash
echo "Hello World" > app.txt
git add app.txt
git commit -m "Initial commit"
```

---

# Step 2: Add Login Feature

```bash
echo "Login Feature Added" >> app.txt
git add app.txt
git commit -m "Added login feature"
```

---

# Step 3: Add Payment Feature

```bash
echo "Payment Feature Added" >> app.txt
git add app.txt
git commit -m "Added payment feature"
```

---

# Current Commit History

Run:

```bash
git log --oneline
```

Output:

```text
c3d4e5f Added payment feature
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# Problem

Suppose the payment feature commit was created by mistake and we want to remove it.

---

# 1. Soft Reset Example

Run:

```bash
git reset --soft HEAD~1
```

---

# What Happens?

Git removes the last commit but keeps the changes staged.

---

# Commit History After Soft Reset

```text
a1b2c3d Added login feature
x9y8z7w Initial commit
```

The commit is removed.

---

# File Content After Soft Reset

```text
Hello World
Login Feature Added
Payment Feature Added
```

The changes still exist.

---

# Git Status After Soft Reset

```bash
git status
```

Output:

```text
Changes to be committed:
```

Meaning:

- changes are still staged
- ready for recommit

---

# Use Case of Soft Reset

Use when:

- commit message was wrong
- you want to combine commits
- you want to recommit changes

---

# 2. Mixed Reset Example (Default)

Run:

```bash
git reset HEAD~1
```

---

# What Happens?

- Last commit removed
- Changes remain in working directory
- Changes become unstaged

---

# Git Status After Mixed Reset

```text
Changes not staged for commit:
```

---

# File Still Contains

```text
Hello World
Login Feature Added
Payment Feature Added
```

But now changes are unstaged.

---

# Use Case of Mixed Reset

Use when:

- you want to edit files again
- you want to selectively stage changes

---

# 3. Hard Reset Example

Run:

```bash
git reset --hard HEAD~1
```

---

# What Happens?

- Last commit removed
- Changes permanently deleted
- Working directory cleaned

---

# Commit History After Hard Reset

```text
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# File Content After Hard Reset

```text
Hello World
Login Feature Added
```

The payment feature is completely removed.

---

# Warning

`git reset --hard` is dangerous because deleted changes may not be recoverable easily.

Use carefully.

---

# Visual Understanding

---

## Before Reset

```text
A ---> B ---> C
```

Where:

- `A` = Initial commit
- `B` = Login feature
- `C` = Payment feature

---

## After Reset

```text
A ---> B
```

HEAD moves backward and commit `C` is removed.

---

# Difference Between Soft, Mixed, and Hard Reset

| Reset Type | Commit Removed | Changes Kept | Changes Staged |
|---|---|---|---|
| `--soft` | Yes | Yes | Yes |
| `mixed` | Yes | Yes | No |
| `--hard` | Yes | No | No |

---

# Best Use Cases of `git reset`

Use `git reset` when:

- cleaning local commits
- fixing commit mistakes
- rewriting local history
- reorganizing commits before push

---

# Important Recommendation

Avoid using `git reset` on already pushed/shared commits unless you fully understand the consequences.

For shared repositories, `git revert` is usually safer.

---

# Key Point to Remember

`git reset` changes Git history by moving HEAD backward.
---

# Best Practice Recommendation

| Situation | Recommended Command |
|---|---|
| Undo pushed commit | `git revert` |
| Remove file from tracking | `git rm --cached` |
| Cleanup local commits | `git reset` |
| Shared branch work | Prefer `git revert` |
| Dangerous history rewrite | Use `git reset` carefully |

---

# Easy Memory Trick

| Command | Memory Trick |
|---|---|
| `git rm --cached` | Stop tracking |
| `git revert` | Safe undo |
| `git reset` | Move backward in time |

---

# Final Conclusion

- `git rm --cached` is used to stop tracking files.
- `git revert` is the safest way to undo commits in shared repositories.
- `git reset` is powerful for local history rewriting but should be used carefully, especially after pushing commits.

# Difference Between `git pull` and `git fetch`

Both `git pull` and `git fetch` are used to get changes from a remote repository, but they work differently.

---

# 1. `git fetch`

## Purpose

`git fetch` downloads the latest changes from the remote repository without modifying your current working branch.

It only updates remote tracking branches.

---

## Syntax

```bash
git fetch
```

---

# What Happens?

Suppose the remote repository has new commits:

```text
origin/main:
A ---> B ---> C
```

Your local branch contains:

```text
main:
A ---> B
```

Now run:

```bash
git fetch
```

Git downloads commit `C`, but your local branch remains unchanged.

---

# Result After Fetch

```text
origin/main:
A ---> B ---> C

main:
A ---> B
```

Your working code does NOT change automatically.

---

# How to Review Fetched Changes

You can compare local and remote branches using:

```bash
git log main..origin/main
```

or

```bash
git diff main origin/main
```

---

# Common Use Cases of `git fetch`

Use `git fetch` when:

- you want to review remote changes first
- you want safer synchronization
- you do not want automatic merge
- working in collaborative environments

---

# 2. `git pull`

## Purpose

`git pull` downloads remote changes AND automatically merges them into the current branch.

---

## Syntax

```bash
git pull
```

---

# What Happens?

Suppose remote repository has:

```text
A ---> B ---> C
```

Your local branch contains:

```text
A ---> B
```

Now run:

```bash
git pull
```

Git will:

1. Fetch remote changes
2. Merge them automatically

---

# Result After Pull

```text
A ---> B ---> C
```

Your local branch and working directory are updated immediately.

---

# Important Understanding

`git pull` is basically:

```bash
git fetch + git merge
```

---

# Visual Comparison

---

## Git Fetch

Before:

```text
Local:   A ---> B
Remote:  A ---> B ---> C
```

After `git fetch`:

```text
Local:        A ---> B
origin/main:  A ---> B ---> C
```

No merge happens.

---

## Git Pull

Before:

```text
Local:   A ---> B
Remote:  A ---> B ---> C
```

After `git pull`:

```text
Local:   A ---> B ---> C
```

Automatic merge happens.

---

# Practical Example

---

# Using `git fetch`

```bash
git fetch
git log origin/main
```

Review changes first.

Then manually merge:

```bash
git merge origin/main
```

---

# Using `git pull`

```bash
git pull origin main
```

Everything happens automatically.

---

# Key Difference Table

| Feature | `git fetch` | `git pull` |
|---|---|---|
| Downloads remote changes | Yes | Yes |
| Updates working directory | No | Yes |
| Automatic merge | No | Yes |
| Safer | Yes | Less safe |
| Best for review | Yes | No |
| Best for quick sync | No | Yes |

---

# Best Practice Recommendation

## Use `git fetch`

When:

- working in teams
- reviewing code changes
- avoiding accidental merge conflicts

---

## Use `git pull`

When:

- you trust remote changes
- quick synchronization is needed
- simple workflow is used

---

# Easy Memory Trick

| Command | Memory Trick |
|---|---|
| `git fetch` | Download only |
| `git pull` | Download + merge |

---

# Final Conclusion

- `git fetch` safely downloads changes without modifying your branch.
- `git pull` downloads and merges changes automatically.
- `git fetch` is safer for professional/team workflows.
- `git pull` is faster and convenient for quick updates.

######################

# Difference Between `git rm --cached`, `git revert`, and `git reset`

These Git commands are used for different purposes.  
Although all of them can help undo changes in some way, they work very differently.

---

# 1. `git rm --cached <file_name>`

## Purpose
Removes a file from Git tracking **without deleting it from the local system**.

---

## Syntax

```bash
git rm --cached <file_name>
```

---

## Example

```bash
git rm --cached .env
```

---

## What Happens?

- File is removed from Git repository tracking
- File remains available on your local machine
- Useful when you accidentally commit sensitive or unnecessary files

---

## Common Use Cases

### Remove sensitive files

Example:

```bash
.env
password.txt
secrets.json
```

---

### Use with `.gitignore`

After removing tracking:

```bash
git rm --cached .env
```

Add file into `.gitignore`:

```bash
echo ".env" >> .gitignore
```

---

## Important Note

This command does NOT remove commit history.  
It only stops Git from tracking the file in future commits.

---

# 2. `git revert`

## Purpose
Undo a previous commit safely by creating a **new commit**.

---

## Syntax

```bash
git revert <commit_id>
```

or

```bash
git revert HEAD
```

---

## Example

```bash
git revert HEAD
```

---

## What Happens?

Suppose commit history is:

```text
A ---> B ---> C
```

If you revert commit `C`:

```text
A ---> B ---> C ---> Revert_C
```

Git creates a new commit that reverses the changes made in commit `C`.

---

## Key Features

- Commit history remains safe
- No history rewriting
- Recommended for shared branches like `main`

---

## Common Use Cases

### Undo a bad commit on shared branch

Example:

- Wrong feature added
- Bug introduced
- Incorrect configuration committed

---

## Advantages

- Safe for collaboration
- Team members are not affected
- No force push required

---

# Git Revert Example Explained

`git revert` is used to safely undo a commit by creating a new commit that reverses the changes of the previous commit.

It does NOT delete commit history.

---

# Scenario

Suppose we have a simple project.

---

# Step 1: Initial Commit

Create a file and commit it.

```bash
echo "Hello World" > app.txt
git add app.txt
git commit -m "Initial commit"
```

---

# Step 2: Add a New Feature

Now we add a login feature.

```bash
echo "Login Feature Added" >> app.txt
git add app.txt
git commit -m "Added login feature"
```

---

# Current Commit History

Run:

```bash
git log --oneline
```

Output:

```text
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# Problem

Suppose the login feature contains bugs and we want to remove it safely without deleting Git history.

---

# Solution: Use `git revert`

Run:

```bash
git revert HEAD
```

---

# What Happens?

Git creates a NEW commit that reverses the changes made in the previous commit.

---

# New Commit History

Run:

```bash
git log --oneline
```

Output:

```text
k7l8m9n Revert "Added login feature"
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# File Content Before Revert

```text
Hello World
Login Feature Added
```

---

# File Content After Revert

```text
Hello World
```

The line added by the previous commit has been removed.

---

# Important Observation

Notice the following:

- Old commit is NOT deleted
- Git history remains preserved
- A new revert commit is created
- Safe for team/shared repositories

---

# Visual Representation

Before revert:

```text
A ---> B
```

Where:

- `A` = Initial commit
- `B` = Added login feature

---

After revert:

```text
A ---> B ---> C
```

Where:

- `C` = Revert commit

---

# Why `git revert` is Safe

`git revert` is preferred in shared repositories because:

- It does not rewrite history
- No force push is required
- Other developers are not affected

---

# Revert a Specific Commit

You can also revert a specific commit using its commit ID.

Example:

```bash
git revert a1b2c3d
```

Git will reverse the changes introduced by that commit.

---

# Best Use Cases of `git revert`

Use `git revert` when:

- A bad commit has already been pushed
- You want to safely undo changes
- You are working in a team environment
- You want to preserve commit history

---

# Key Point to Remember

`git revert` does NOT remove commits.

It creates a new commit that undoes the changes introduced by an older commit.

# 3. `git reset`

## Purpose
Move HEAD to a previous commit.

It can modify commit history.

---

# Types of `git reset`

---

## A. Soft Reset

### Syntax

```bash
git reset --soft HEAD~1
```

### What Happens?

- Last commit removed
- Changes remain staged

---

### Flow

Before:

```text
A ---> B ---> C
```

After:

```text
A ---> B
```

Changes from `C` remain in staging area.

---

## B. Mixed Reset (Default)

### Syntax

```bash
git reset HEAD~1
```

---

### What Happens?

- Last commit removed
- Changes remain in working directory
- Changes become unstaged

---

## C. Hard Reset

### Syntax

```bash
git reset --hard HEAD~1
```

---

### What Happens?

- Last commit removed
- All changes permanently deleted

---

## Warning

`git reset --hard` is dangerous because deleted changes may not be recoverable easily.

---

# Common Use Cases of `git reset`

---

## Local commit cleanup

Example:

- Wrong commit message
- Multiple unnecessary commits
- Reorganizing commits before push

---

## Remove local changes completely

```bash
git reset --hard
```

---

# Main Difference Summary

| Command | Purpose | Changes History? | Creates New Commit? | Safe for Shared Branch? |
|---|---|---|---|---|
| `git rm --cached` | Stop tracking file | No | Yes (after commit) | Yes |
| `git revert` | Undo commit safely | No | Yes | Yes |
| `git reset` | Move HEAD backward | Yes | No | Use carefully |

---

# When Should We Use These Commands?

---

## Use `git rm --cached`

When:

- You accidentally committed sensitive files
- You want Git to stop tracking a file
- You are using `.gitignore`

### Example

```bash
git rm --cached .env
```

---

## Use `git revert`

When:

- You want to safely undo a commit
- Commit is already pushed
- You are working in a team/shared repository

### Example

```bash
git revert HEAD
```

---

## Use `git reset`

When:

- You want to rewrite local commit history
- You want to remove local commits
- You want to clean up commits before pushing

### Example

```bash
git reset --soft HEAD~1
```
# Git Reset Example Explained

`git reset` is used to move HEAD to a previous commit.

Unlike `git revert`, `git reset` can modify Git history.

It is commonly used for local commit cleanup and history rewriting.

---

# Scenario

Suppose we have a simple project.

---

# Step 1: Initial Commit

Create a file and commit it.

```bash
echo "Hello World" > app.txt
git add app.txt
git commit -m "Initial commit"
```

---

# Step 2: Add Login Feature

```bash
echo "Login Feature Added" >> app.txt
git add app.txt
git commit -m "Added login feature"
```

---

# Step 3: Add Payment Feature

```bash
echo "Payment Feature Added" >> app.txt
git add app.txt
git commit -m "Added payment feature"
```

---

# Current Commit History

Run:

```bash
git log --oneline
```

Output:

```text
c3d4e5f Added payment feature
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# Problem

Suppose the payment feature commit was created by mistake and we want to remove it.

---

# 1. Soft Reset Example

Run:

```bash
git reset --soft HEAD~1
```

---

# What Happens?

Git removes the last commit but keeps the changes staged.

---

# Commit History After Soft Reset

```text
a1b2c3d Added login feature
x9y8z7w Initial commit
```

The commit is removed.

---

# File Content After Soft Reset

```text
Hello World
Login Feature Added
Payment Feature Added
```

The changes still exist.

---

# Git Status After Soft Reset

```bash
git status
```

Output:

```text
Changes to be committed:
```

Meaning:

- changes are still staged
- ready for recommit

---

# Use Case of Soft Reset

Use when:

- commit message was wrong
- you want to combine commits
- you want to recommit changes

---

# 2. Mixed Reset Example (Default)

Run:

```bash
git reset HEAD~1
```

---

# What Happens?

- Last commit removed
- Changes remain in working directory
- Changes become unstaged

---

# Git Status After Mixed Reset

```text
Changes not staged for commit:
```

---

# File Still Contains

```text
Hello World
Login Feature Added
Payment Feature Added
```

But now changes are unstaged.

---

# Use Case of Mixed Reset

Use when:

- you want to edit files again
- you want to selectively stage changes

---

# 3. Hard Reset Example

Run:

```bash
git reset --hard HEAD~1
```

---

# What Happens?

- Last commit removed
- Changes permanently deleted
- Working directory cleaned

---

# Commit History After Hard Reset

```text
a1b2c3d Added login feature
x9y8z7w Initial commit
```

---

# File Content After Hard Reset

```text
Hello World
Login Feature Added
```

The payment feature is completely removed.

---

# Warning

`git reset --hard` is dangerous because deleted changes may not be recoverable easily.

Use carefully.

---

# Visual Understanding

---

## Before Reset

```text
A ---> B ---> C
```

Where:

- `A` = Initial commit
- `B` = Login feature
- `C` = Payment feature

---

## After Reset

```text
A ---> B
```

HEAD moves backward and commit `C` is removed.

---

# Difference Between Soft, Mixed, and Hard Reset

| Reset Type | Commit Removed | Changes Kept | Changes Staged |
|---|---|---|---|
| `--soft` | Yes | Yes | Yes |
| `mixed` | Yes | Yes | No |
| `--hard` | Yes | No | No |

---

# Best Use Cases of `git reset`

Use `git reset` when:

- cleaning local commits
- fixing commit mistakes
- rewriting local history
- reorganizing commits before push

---

# Important Recommendation

Avoid using `git reset` on already pushed/shared commits unless you fully understand the consequences.

For shared repositories, `git revert` is usually safer.

---

# Key Point to Remember

`git reset` changes Git history by moving HEAD backward.
---

# Best Practice Recommendation

| Situation | Recommended Command |
|---|---|
| Undo pushed commit | `git revert` |
| Remove file from tracking | `git rm --cached` |
| Cleanup local commits | `git reset` |
| Shared branch work | Prefer `git revert` |
| Dangerous history rewrite | Use `git reset` carefully |

---

# Easy Memory Trick

| Command | Memory Trick |
|---|---|
| `git rm --cached` | Stop tracking |
| `git revert` | Safe undo |
| `git reset` | Move backward in time |

---

# Final Conclusion

- `git rm --cached` is used to stop tracking files.
- `git revert` is the safest way to undo commits in shared repositories.
- `git reset` is powerful for local history rewriting but should be used carefully, especially after pushing commits.

