# Git Command Reference
Commands that to work with repositories in the local environment and across the network (i.e. working with remote repositories on GitHub)
[Git Command Reference](https://git-scm.com/docs)

## Getting and Creating Repositories
- **`clone`** copies a _remote repository_ from github to the specified location
- **`init`** initializes a _local repository_ on your desktop; adds `.git` folder to index and track changes
![.git directory img](https://github.com/NicholasBoeke/git_notes/blob/main/images/dot_git_folder.png)

## Basic Snapshotting
- **`add`** Adds an object to the local repository's index / working tree, so git knows to track changes to that object in preparation for the next commit.  The object added could be a file, list of files or an entire directory, or list of directories.
- **`commit`** Saves the current snapshot to the local repository's (or branch's) history with a message describing the changes.  Anything that was added using `git add` will become part of the current snapshot.

## Branching and Merging
- **`branch`** list, create or delete branches; If creating a new branch, it will create a branch with a head named `branchname` which points to the current HEAD, or `start-point` if given.  For example, A is the origin and is the HEAD of master; commit B is the start of a branch, the branch having HEAD at D.  Development of the master continued with commits C and G, so the branch was behind the master.
```
        D---E---F topic
       /
  A---B---C---G master
```

      
- **`checkout`** use `git switch` instead; 
checkout lets you navigate between the branches created by `git branch`. Checking out a branch updates the files in the working directory to match the version stored in that branch, and it tells Git to record all new commits on that branch.
- **`switch`** Switch to a specified branch. The working tree and the index are updated to match the branch. All new commits will be added to the tip of this branch.
- **`merge`** Join two or more development histories together. Incorporates changes from the named commits (since the time their histories diverged from the current branch) into the current branch. This command is used by git pull to incorporate changes from another repository and can be used by hand to merge changes from one branch into another.



      
## Sharing and Updating Repositories
- **`fetch`** checks the remote repository for any commits (on any branches) that are not part of your local repository (in a sense 'staging' them for you pull those changes locally). The `fetch` will also pull any objects from the remote that are necessary to complete the local history.  You can fetch from a single repo or multiple repos simultaneously. e.g. `git fetch origin` copies all branches from the remote refs/heads/ namespace and stores them to the local refs/remotes/origin/ namespace.
- **`pull`** if any commits exist on any branch in the remote repository (e.g. from a colleague) updates the local line of development environment to reflect those changes.  This is actually a combination of `git fetch` + `git merge`
- **`push`** updates the remote repository with any commits made locally to a branch.



### Workflow Example: contribute to an existing branch on GitHub
This example assumes that you already have a project called repo on the machine and that a new branch has been pushed to GitHub since the last time changes were made locally.
```
# change into the `repo` directory
cd repo

# update all local tracking branches from the remote, including the currently checked out branch
git pull

# change into the existing branch called `feature-a`
git checkout feature-a

# make changes, for example, edit `file1.md` using the text editor

# stage the changed file
git add file1.md

# create a snapshot of the local staging area
git commit -m "edit file1"

# push changes to the remote repo on github
git push
```


# GitHub Reference
[GitHub Docs](https://docs.github.com/en)
**`Fork`** If you want to contribute to an existing project to which you don’t have push access, you can “fork” the project. When you “fork” a project, GitHub will make a copy of the project that is entirely yours; it lives in your namespace, and you can push to it.  This way, projects don’t have to worry about adding users as collaborators to give them push access. People can fork a project, push to it, and contribute their changes back to the original repository by creating what’s called a Pull Request


