---
title: Git Command Cheat Sheet
description: Essential Git commands and workflows for daily use, from basic operations to advanced techniques.
category: development
pubDatetime: 2024-03-15T15:30:00Z
tags: ["git", "development", "cheatsheet"]
---

# Git Command Cheat Sheet

A collection of commonly used Git commands and workflows. Keep this handy for your daily development tasks.

## Basic Commands

### Repository Setup
```bash
# Initialize a new repository
git init

# Clone an existing repository
git clone <repository-url>
```

### Daily Workflow
```bash
# Check status
git status

# Stage changes
git add <file>
git add .  # Stage all changes

# Commit changes
git commit -m "Your commit message"

# Push changes
git push origin <branch-name>

# Pull changes
git pull origin <branch-name>
```

## Branch Operations

### Managing Branches
```bash
# List branches
git branch  # Local branches
git branch -r  # Remote branches
git branch -a  # All branches

# Create new branch
git branch <branch-name>
git checkout -b <branch-name>  # Create and switch

# Switch branches
git checkout <branch-name>
git switch <branch-name>  # Git 2.23+
```

### Merging
```bash
# Merge branch into current branch
git merge <branch-name>

# Abort merge
git merge --abort
```

## Advanced Operations

### Stashing
```bash
# Stash changes
git stash
git stash save "message"

# List stashes
git stash list

# Apply stash
git stash apply
git stash pop  # Apply and remove
```

### History and Logs
```bash
# View commit history
git log
git log --oneline
git log --graph

# Show changes
git show <commit-hash>
```

## Tips and Tricks

### Useful Aliases
```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

### Common Workflows

1. Feature Branch Workflow
   ```bash
   git checkout -b feature/new-feature
   # Make changes
   git add .
   git commit -m "Add new feature"
   git push origin feature/new-feature
   ```

2. Fixing Mistakes
   ```bash
   # Undo last commit
   git reset --soft HEAD~1
   
   # Amend last commit
   git commit --amend
   ```

Remember to always be careful with commands that rewrite history (`reset`, `rebase`, etc.) on shared branches!
