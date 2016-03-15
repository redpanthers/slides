---
layout: slide
title: Advanced Git
description: A presentation slide for how to use Git
theme: black
transition: slide
permalink: /Advanced-git
author: Aparna V
post_thumbnail: /slides/images/git-advanced.jpg
profile_image: /slides/profiles/aparnav.jpg
---

<section data-markdown>
## Advanced Git

March 14 2016
</section>

<section>
  <h2>Aparna V</h2>
  <p>
    Ruby Developer Trainee @RedPanthers
  </p>
</section>

<section data-markdown>
### Introduction
What is GIT?
- Distributed Version Control System.  
The basic Git workflow:
* Modify files in your working directory.
* You stage the files, adding snapshots of them to your staging area.
* You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory.
</section>

<section data-markdown>
### Git merge
git-merge - Join two or more development histories together.
</section>

<section data-markdown>
### Merge with --ff and --no-ff  
--ff  
When the merge resolves as a fast-forward, only update the branch pointer, without creating a merge commit. This is the default behavior.  

--no-ff  
Create a merge commit even when the merge resolves as a fast-forward. This is the default behaviour when merging an annotated (and possibly signed) tag.  
</section>

<section data-markdown>
###FAST-FORWARD MERGE
Often the current branch head is an ancestor of the named commit. This is the most common case especially when invoked from git pull: you are tracking an upstream repository, you have committed no local changes, and now you want to update to a newer upstream revision. In this case, a new commit is not needed to store the combined history; instead, the HEAD (along with the index) is updated to point at the named commit, without creating an extra merge commit.
This behavior can be suppressed with the --no-ff option.
</section>

<section data-markdown>
### Rebase
As an alternative to merging,rebase the feature branch onto master branch using the following commands:
git checkout feature
* git rebase master
This moves the entire feature branch to begin on the tip of the master branch, effectively incorporating all of the new commits in master. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch.
</section>

<section data-markdown>
### Interactive Rebasing
Interactive rebasing gives you the opportunity to alter commits as they are moved to the new branch. This is even more powerful than an automated rebase, since it offers complete control over the branch’s commit history. Typically, this is used to clean up a messy history before merging a feature branch into master.

To begin an interactive rebasing session, pass the i option to the git rebase command:

git checkout feature
* git rebase -i master
</section>

<section data-markdown>
###The Golden Rule of Rebasing
 The golden rule of git rebase is to never use it on public branches.
</section>

<section data-markdown>
### Git-cherry-pick
* Apply the changes introduced by some existing commits.
What git cherry-pick does, basically, is take a commit from somewhere else, and "play it back" wherever you are right now.
git cherry-pick commit-hash

</section>

<section data-markdown>
### Git rerere
* The name stands for "reuse recorded resolution" and as the name implies, it allows you to ask Git to remember how you've resolved a hunk conflict so that the next time it sees the same conflict, Git can automatically resolve it for you.

</section>



<section data-markdown>
### Git rerere --contd

* To enable the rerere functionality, you simply have to run this config setting:

* $ git config --global rerere.enabled true
* You can also turn it on by creating the .git/rr-cache directory in a specific repository, but I think the config setting is clearer, and it can be done globally.

</section>

<section data-markdown>
### Rebasing Vs Merging
Rebasing a branch on master:
* provides an incorrect idea of how commits were created  
* pollutes master with a bunch of intermediate commits that may not have been well tested
* makes finding good places in master to checkout difficult.
* Causes the timestamps on commits to not align with their chronological order in the tree.
</section>

<section data-markdown>  
Merging a branch on master:
* preserves history of where topic branches were created, including any merges from master to the topic branch to help keep it current. You really get an accurate idea of what code the developer was working with when they were building.
* master is a branch made up mostly of merges, and each of those merge commits are typically 'good points' in history that are safe to check out because that's where the topic branch was ready to be integrated.
</section>

<section data-markdown>
### Reference

* https://git-scm.com/docs/git-merge
* https://git-scm.com/docs/git-cherry-pick
* https://git-scm.com/book/en/v2/Git-Branching-Rebasing
* https://www.git-tower.com/blog/understanding-rebase-merge-in-git/
* https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
* https://git-scm.com/blog/2010/03/08/rerere.html
* https://www.atlassian.com/git/tutorials/advanced-overview

</section>

<section data-markdown>
## Thank you
</section>
