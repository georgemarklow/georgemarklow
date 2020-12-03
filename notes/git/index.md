# Git

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

![](https://i.redd.it/nm1w0gnf2zh11.png)

## Useful links

- [Reference](https://git-scm.com/docs)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Git branching model](https://git-scm.com/about)
- [Gitflow Workdlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [A Beginners Guide to Git](https://www.fir3net.com/UNIX/Linux/a-beginners-guide-to-git.html)
- [Using Git with Visual Studio 2019: The Ultimate Guide](https://yourbrainoncomputers.com/using-git-with-visual-studio-2019-the-ultimate-guide/)

## Best Practices

- [6 best practices for teams using Git](https://opensource.com/article/20/7/git-best-practices)

## Summary

### Basics

| Task      | Command |
| :---        | :---        |
| Create a git repository      | git init       |
|  View the status of each file in the repository  |   git status      |
| Stage a file for the next commit | git add [file] |
| Commit the staged files with a descriptive message | git commit -m "message" |
| View repository commit history | git log (--oneline) |
| Define the author name to be used in all repositories | git config --global user.name "name" |
| Define the author email to be used in all repositories | git config --global user.email "email" |

### Undoing Changes

| Task      | Command |
| :---        | :---        |
| View a previous commit | git checkout commit-id |
| Create an annotated tag pointing to the most recent commit | git tag -a tag-name -m "description" |
| Undo the specified commit by applying a new commit | git revert commit-id |
| Reset tracked files to match the most recent commit | git reset --hard |
| Remove untracked files | git clean -f |
| Permanently undo uncommited changes | git reset --hard/git clean -f |

### Branching Part I

| Task      | Command |
| :---        | :---        |
| List all branches | git branch |
| Create a new branch using the current working directory as its base | git branch branch-name |
| Make the working directory and the HEAD match the specified branch | git checkout branch-name |
| Merge a branch into the checked-out branch | git merge -d branch-name |
| Delete a branch | git branch -d branch-name |
| Remove a file from the working directory and stop tracking the file | git rm file |

### Branching Part II

| Task      | Command |
| :---        | :---        |
| Stage all tracked files and commit the snapshot using the specified message | git commit -a -m "message |
| Force the removal of an unmerged branch | git branch -D branch-name |

### Rebasing

| Task      | Command |
| :---        | :---        |
| Move the current branch's commits to the tip of new-base, which can be either a branch name or commit ID | git rebase new-base |
| Add staged changes to the most recent commit instead of creating a new one | git commit --amend |
| Continue a rebase after amending a commit | git rebase --continue |
| Abdondon the current interactive rebase and return the repository to its former state | git rebase --abort |
| Force a merge commit even if Git could do a fast-forward merge | git merge --no-ff branch-name |

### Rewrite History

| Task      | Command |
| :---        | :---        |
| Display the local chronological history of a repository | git reflog |
| Move the HEAD backwards n commits but don't change the working directory | git reset --mixed HEAD~n |
| Move the HEAD backwards n commits and change the working directory | git reset --hard HEAD~n |
| Display the commits reachable from until but not from since (params either commit IDs or branch names | git log since..until |
| Include extra information about altered files in the log output | git log --stat |

### Remotes

| Task      | Command |
| :---        | :---        |
| Create a clone of a remote Git repository | git clone remote-path |
| List remote repositories | git remote |
| Add a remote repository | git remote add remote-name remote-path |
| Download remote branch information, but do not merge anything | git fetch remote-name |
| Merge a remote branch into the checked-out branch | git merge remote-name/branch-name |
| List remote branches | git branch -r |
| Push a local branch to another repository | git push remote-name branch-name |
| Push a tag to another repository | git push remote-name tag-name |

### Patches

| Task      | Command |
| :---        | :---        |
| Create a patch for each commit contained in the current branch but not in branch-name | git format-patch branch-name |
| Apply a patch to the current branch | git am patch-file |

### Tips and Tricks

| Task      | Command |
| :---        | :---        |
| Stash changes to make a clean working directory | git stash |
| Re-apply stashed changes to the working directory | git stash apply |
| View the difference between two commits | git diff commit-id..commit-id |
| Difference between the working directory and the staging area | git diff |
| View the difference between the staging area of the most recent commit | git diff -- cached |
| Unstage a file, but don't alter the working directory or move the current branch | git checkout commit-id file |
| Create a shortcut for a command and store it in the global configuration file | git config --global alias.alias-name git-command |
