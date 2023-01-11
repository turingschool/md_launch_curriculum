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

### Pull Request

Second, Player 2 has created content in a separate branch, but it not yet merged with the `main` branch. We've discussed how to merge branches, but we want one additional step to ensure that both developers agree on the content.

To that end, Player 2 will create a Pull Request (PR). A **Pull Request** informs all collaborators of the changes made to a branch and the desire to merge this branch with another branch (usually the `main` branch).

> 6. P2: Create Pull Request on GitHub

| Player 1 | Player 2 |
| -------- | -------- |
| Review and comment on Player 2's PR<br>Merge Pull Request | |

Player 1 can review, comment, and merge the Pull Request. Player 2 can also add commits to the PR. There can be several rounds of reviews, comments, and additional commits before it is merged.

> 7. P1: Fix Merge Conflict

| Player 1 | Player 2 |
| -------- | -------- |
| Still on `north_carolina` branch<br>`git pull origin main`<br>Fix Merge Conflict<br>`git add` , `git commit` , `git push` | |
| Create Pull Request on GitHub | |

There's **Good News** and _Bad News_. The **Good News** is that Player 2's content has been successfully merged into the shared repo. The _Bad News_ is that when we integrate those changes into our current branch, we encounter a pesky Merge Conflict. But there's more **Good News**: fixing a Merge Conflict when working with a collaborator is no more difficult than working solo.

Once Player 1 fixes the Merge Conflict, they will update their branch and author a Pull Request of their own.
