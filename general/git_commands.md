# Git Commands Reference

This document is a quick reference for common Git commands used in day-to-day development workflows, including setup, version control, branching, and more.

## Table of Contents

- [Setting Up Git](#setting-up-git)
- [Basic Git Operations](#basic-git-operations)
- [Branching and Merging](#branching-and-merging)
  - [Create a Remote Branch Locally](#create-a-remote-branch-locally)
  - [Switching Branches](#switching-branches)
  - [Deleting a Local Branch](#deleting-a-local-branch)
  - [Pulling a Remote Branch](#pulling-a-remote-branch)
  - [Fetch All Remote Branches](#fetch-all-remote-branches)
  - [List All Remote Branches](#list-all-remote-branches)
  - [Pushing to a Remote Branch](#pushing-to-a-remote-branch)
  - [Prune Remote Branches](#prune-remote-branches)
- [Git Workflow](#git-workflow)
- [Stashing](#stashing)
- [Working with Remotes](#working-with-remotes)
- [Tagging](#tagging)
- [Logs and History](#logs-and-history)

## Setting Up Git

```bash
# **Configure user information for all local repositories**
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

## Basic Git Operations

```bash
# Initialize a new Git repository
# To create a new Git repository in your current directory, use the following command:
git init
```

## Branching and Merging

##### Create a Remote Branch Locally
```bash
# Uses the newer switch command
git switch -c <local-branch-name> origin/<remote-branch-name>
```

##### Deleting a Local Branch
```bash
# Deleting a Local Branch
# Delete a branch on your local filesystem
# _Note: Use -D instead of -d to force delete the branch if it has unmerged changes._
git branch -d <branch_name>
```

##### Pulling a Remote Branch

```bash
# Pull a branch from your remote repo
# _Note: This command will create a new local branch that tracks the remote branch._
git checkout -b <local-branch-name> origin/<remote-branch-name>
```

```bash
# _Note: If the remote branch has been updated since you last fetched or checked out the branch, you may want to pull the latest changes._
git pull origin <remote-branch-name>
```

##### Fetch All Remote Branches

```bash
# This will update your local copy of the remote branches without checking them out
git fetch --all

```

##### List All Remote Branches
```bash
# This will update your local copy of the remote branches without checking them out
git branch -r
```

##### Pushing to a Remote Branch
```bash
# This will update your local copy of the remote branches without checking them out
git fetch --all
```

##### Prune Remote Branches

```bash
# In the terminal, run the following command to prune remote-tracking branches that no longer exist on the remote:
git fetch --prune
```

```bash
# To confirm that the branch is gone locally, you can list the branches with:
git branch -r
```

```bash
# If you need to remove a specific remote branch manually, use the following command:
git branch -dr origin/branch-name
```

## Git Workflow

```bash
# Keeping Your Branch in Sync with Origin Branch (Rebase & Force Push)

git fetch origin  # Get the latest changes from the remote repository; Fetch latest changes from remote (doesn't modify your branch yet)

git rebase origin/main  # Replay your commits on top of the latest main branch; Rebase your local branch onto the updated main branch to keep a linear history

git push --force-with-lease origin <your branch name>  # Update the remote branch after rebase (safely force push); Push rebased branch, overwriting remote changes safely (protects others' work)
```

```bash
# update local repo
git pull
```
```bash
# display the state of the working directory and the staging area
git status
```
```bash
# create/checkout new branch
git checkout -b <new branch name>
git status
```
```bash
# adds a change in the working directory to the staging area
git add .
git status
```
```bash
# captures a snapshot of the project's currently staged changes
git commit -m "comments go here"
git status
```
```bash
# push branch to origin
git push origin <new branch name>
git status
```
#### AFTER MERGE
```bash
# switch to the main branch and update local repo
git checkout main
git pull
git branch --delete <branchname>
```
