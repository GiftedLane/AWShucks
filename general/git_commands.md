# Git Commands Reference

This document is a quick reference for common Git commands used in day-to-day development workflows, including setup, version control, branching, and more.

## Table of Contents

- [Setting Up Git](#setting-up-git)
- [Basic Git Operations](#basic-git-operations)
- [Branching and Merging](#branching-and-merging)
  - [Creating a Branch](#creating-a-branch)
  - [Switching Branches](#switching-branches)
  - [Deleting a Local Branch](#deleting-a-local-branch)
  - [Pulling a Remote Branch](#pulling-a-remote-branch)
  - [Pushing to a Remote Branch](#pushing-to-a-remote-branch)
- [Stashing](#stashing)
- [Working with Remotes](#working-with-remotes)
- [Tagging](#tagging)
- [Logs and History](#logs-and-history)

## Setting Up Git

**Configure user information for all local repositories**

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

## Basic Git Operations

### Initialize a new Git repository

To create a new Git repository in your current directory, use the following command:

```bash
git init
```

## Branching and Merging

### Deleting a Local Branch

Delete a branch on your local filesystem

```bash
git branch -d <branch_name>
```
_Note: Use -D instead of -d to force delete the branch if it has unmerged changes._

### Pulling a Remote Branch

Pull a branch from your remote repo

```bash
git checkout -b <local-branch-name> origin/<remote-branch-name>
```
_Note: This command will create a new local branch that tracks the remote branch._

```bash
git pull origin <remote-branch-name>
```
_Note: If the remote branch has been updated since you last fetched or checked out the branch, you may want to pull the latest changes._

### Pushing to a Remote Branch

```bash
git push <remote-name> <local-branch-name>:<remote-branch-name>
```
_Example: git push origin feature:develop_
