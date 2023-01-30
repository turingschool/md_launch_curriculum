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

### Merge and Update Main Branch

> P2: Merge PR and Update `main` branch

| Player 1 | Player 2 |
| -------- | -------- |
| | Review and comment on Player 1's PR<br>Merge Pull Request

Let's answer a question before it's asked: **YES**, even though Player 1 owns this repo, they also make pull requests so that their changes are reviewed by the other collaborators. And **YES**, the process for Player 2 is the same.

> P1 & P2: Sync local repo

| Player 1 | Player 2 |
| -------- | -------- |
| Checkout main branch<br>git pull origin main | |
| | Checkout main branch<br>git pull origin main

The changes from both Player 1 and Player 2 have been merged. However, neither developer have ALL of the changes on their own local machine. Let's fix that.

Player 1 will check out their `main` branch, then pull down the `main` branch from GitHub. Then Player 2 will do the same thing. Or maybe Player 2 does it first, then Player 1. Maybe they do it at the same time.


### The Reality

For the sake of education, this process was presented as a linear process: Player 1 does something while Player 2 waits. Then Player 2 does something while Player 1 waits. It's like a relay race.

However, that's not usually the case. 

| Player 1 | Player 2 |
| -------- | -------- |
| Create new local repo: `US_States`<br>Add `all_states.txt` file<br>Add title to `all_states.txt` file<br>`git add` , `git commit` , `git push` | |
| Add collaborator in GitHub | Accept invitation on GitHub<br>Clone `US_States` repo to local
| Checkout new branch: `colorado`<br>Add `colorado.txt` file<br>Add "Colorado" to `all_states.txt` file<br>`git add` , `git commit` , `git push`| Checkout new branch: `north_carolina`<br>Add `north_carolina.txt` file<br>Add "North Carolina" to `all_states.txt` file<br>`git add` , `git commit` , `git push`<br>Create PR on GitHub |
| Review and comment on Player 2's PR<br>Merge Pull Request<br>Pull `main` branch<br> Fix Merge Conflict<br>Add, Commit, Push<br>Create PR | |
| | Review and comment on P1's PR<br>Merge Pull Request |
| Checkout main branch<br>Pull `main` branch | Checkout main branch<br>Pull `main` branch |

Once Player 1 invites Player 2 as a collaborator, much of the process happens simultaneously. There's little reason to "wait" for other developers to finish before working on a new task. In fact, either developer could move onto a new branch (perhaps `virginia` or `new_york`) while the other continues working. Making pull requests and fixing conflicts along the way is par for the course.

### Rules of Engagement

You will practice this often when working in pairs and groups throughout your time at Turing and in your new career. There are a few basic rules you should follow:
  1. **_NEVER_** work directly on the `main` branch. **NEVER** *EVER* *EVER* **_EVER_**.
  1. Always checkout a new or existing branch. If there is an open Pull Request and you need to add or change something related to that content, checkout the existing branch. Otherwise, create/checkout a new branch.
  1. A good habit is to prefix the branch you're working on with your initials: e.g. `rt/north_carolina` , `zf/colorado`. This easily informs all collaborators of the branch's author.
  1. Did we mention to never work on the `main` branch?
