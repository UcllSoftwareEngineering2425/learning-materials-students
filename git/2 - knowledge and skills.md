# Git

## Knowledge

### General Git Questions

* Explain why using Git is better than using, for instance, Google Drive or OneDrive.
* How does Git track changes in files, and what is the purpose of the staging area?
* What is a commit in Git, and what information does it contain?
* What is the difference between a branch and a commit in Git?
* What is the difference between a branch and a tag in Git?
* What happens when you create a new branch? How does Git internally track branches?
* Explain the 'three trees' in Git: the working directory, the staging area and the commit history.
* What is the difference between a local repository and a remote repository in Git?
* How can you add a new remote repository, and why might you need multiple remotes?

### Git Commands Questions

* Explain the difference between `git fetch` and `git pull`.
* Explain the difference between merging and rebasing. When should each be used?
* What does `git reset` do, and how does it differ from `git revert`?
* What are the three different modes of `git reset` (`--soft`, `--mixed`, `--hard`), and how do they affect the working directory, staging area, and commit history?
* Explain how `git rebase` lets you 'rewrite history'.
* What is `git stash`, and why is it useful?
* How does `git stash` differ from `git reset` and `git restore` when dealing with uncommitted changes?

### Git Workflow Questions

* Explain the difference between the following 'branching models': trunk-based development and feature branches.
* Explain how a workflow with Pull Requests looks like.
* Why is working with Pull Requests so encouraged?

### Git Best Practices Questions

* Why should you use .gitignore, and how do you set it up?
* Why is it a bad practice to commit large, unrelated changes in a single commit?
* What does it mean to "rewrite history" in Git, and why would you want to do it?
* What are the risks of rewriting history, especially in shared repositories?
* Explain why reverting an unwanted commit (eg, committing a password) does not make that mistake invisible. 

## Skills

* Use git from a command-line interface.
* Be able to use the following git commands:
  * Basic Commands
    * `git init`
    * `git status`, `git add` and `git restore`
    * `git commit` and `git revert`
    * `git push`, `git fetch` and `git pull`
    * `git log`
  * Branching and Merging
    * `git branch` and `git switch`
    * `git merge` and `git rebase`
  * Working with your Repository
    * `git stash`
    * `git reset`
    * `git reflog`