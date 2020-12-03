# Quick Reference

## Git

Source: [link](https://www.freecodecamp.org/news/10-important-git-commands-that-every-developer-should-know/)

| Task      | Command |
| :---        | :---        |
| Download existing source code from a remote repository  | git clone remote-path |
| Create a new branch | git branch branch-name |
| Push the new branch into the remote repository | git push -u remote branch-name |
| View branches | git branch or git branch --list |
| Delete a branche | git branch -d branch-name |
| Switch to branch | git checkout name-of-your-branch |
| Create and switch to a branch at the same time | git checkout -b name-of-your-branch |
| Get all information about current branch | git status |
| Add a single file | git add file |
| Add everything at once | git add -A |
| Save changes | git commit -m "commit message" |
| Send changes to the remote server | git push remote branch-name |
| Send changes to the remote server (if your branch is newly created) | git push --set-upstream remote name-of-your-branch |
| | git push -u origin <branch_name> |
| Get updates from remote repo | git pull remote |
| Undo commit hashcode | git revert # |
| Switch to dev branch | git checkout dev |
| Update local branch before merge | git fetch |
| Merge feature branch into dev | git merge branch-name |
