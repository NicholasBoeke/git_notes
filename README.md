# Git Command Reference
[Git Command Reference](https://git-scm.com/docs)

## Getting and Creating Repositories
- **`clone`** copies a _remote repository_ from github to the specified location
- **`init`** initializes a _local repository_ on your desktop; adds `.git` folder to index and track changes
![.git directory img](https://github.com/NicholasBoeke/git_notes/blob/main/images/dot_git_folder.png)

## Basic Snapshotting
- **`add`** Adds an object to the local repository's index / working tree, so git knows to track changes to that object in preparation for the next commit.  The object added could be a file, list of files or an entire directory, or list of directories.
- **`commit`** Saves the current snapshot to the local repository's (or branch's) history with a message describing the changes.  Anything that was added using `git add` will become part of the current snapshot.

## Branching and Merging
- **`branch`** list, create or delete branches; If creating a new branch, it will create a branch with a head named <branchname> which points to the current HEAD, , or <start-point> if given.  For example, D is the origin and is the HEAD of master; commit A is the start of a branch with HEAD at E.
```
      	A---B---C master on origin
    	 /
  D---E---F---G master
  	  ^
  	  origin/master in your repository
```
  
- **`checkout`** 
- **`switch`** 
- **`merge`** 

## Sharing and Updating Repositories
- **`fetch`** checks the remote repository for any commits (on any branches) that are not part of your local repository (in a sense 'staging' them for you pull those changes locally). The `fetch` will also pull any objects from the remote that are necessary to complete the local history.  You can fetch from a single repo or multiple repos simultaneously. e.g. `git fetch origin` copies all branches from the remote refs/heads/ namespace and stores them to the local refs/remotes/origin/ namespace.
- **`pull`** if any commits exist on any branch in the remote repository (e.g. from a colleague) updates the local line of development environment to reflect those changes.  
- **`push`** updates the remote repository with any commits made locally to a branch.



### Example: contribute to an existing branch on GitHub
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
  


