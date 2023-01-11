---
layout:     page
title:      Git for Pairs
permalink:  git-for-pairs
---

# Git for Pairs

## Learning Goals
  * 

## Vocabulary
  * Pull Request (PR)
  * Clone repo
  * Fork repo

## Review
> If necessary, review the following video lessons from Version Control with Git/Github
  >1. [Create A Project and Initialize a Git Repository](https://www.loom.com/share/d3af392e059147a699ce6ac1af65d251)
  >1. [Add Commits to the Git Repository](https://www.loom.com/share/b7373e5aaad646c790965422719bb993)  
  >1. [Creating and Pushing to a Github Repository](https://www.loom.com/share/dba188a5f13e43059d9a84b630280c53)


## Paired Process
In this scenario, a developer (we'll call them **Player 1**) is creating a repository about the 50 U.S. states. Player 1 recruits another developer (let's call them **Player 2**) to assist.

> 1. P1: Create new local repo
> 1. P1: Add collaborator in Github
> 1. P1: Create new branch

| Player 1 | Player 2 |
| -------- | -------- |
| Create new local repo: `US_States`<br>Add `all_states.txt` file<br>Add title to `all_states.txt` file<br>`git add` , `git commit` , `git push` | |
| Add collaborator in GitHub | |
| Checkout new branch: `north_carolina`<br>Add `north_carolina.txt` file<br>Add "North Carolina" to `all_states.txt` file<br>`git add` , `git commit` , `git push`


### Adding collaborators

We've added a new step to the process: adding a collaborator. Player 1 has invited Player 2 to contribute to the repo. There are several options when adding a collaborator; in this case, we want both developers to have equal access and rights to the repository. 

> 4. P2: Accept GitHub invitation
> 1. P2: Create new branch

| Player 1 | Player 2 |
| -------- | -------- |
| | Accept invitation on GitHub<br>Clone `US_States` repo to local
| | Checkout new branch: `colorado`<br>Add `colorado.txt` file<br>Add "Colorado" to `all_states.txt` file<br>`git add` , `git commit` , `git push`

### Cloning a repository

Player 2 has performed two important tasks. First, they have cloned the repo created by Player 1. To clone a repository means to copy a remote Github repository to your local computer using the following command:

```
git clone <SSH KEY for repository>
```

When you clone a repository, you interact with that repository by pushing and pulling branches. Therefore, when you are working with teammates, i.e. in a group project, you all need to clone the same repository so that you are all working in the same code base.
