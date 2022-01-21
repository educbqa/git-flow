# Git Flow

## Commit & rebase

### 1. Commit our local changes with ``commit`` command
### 2. Do a rebase with ``git pull --rebase origin (remote branch)``
- ``origin`` means the pull comes from our local feature branch. Like ``feature-tc10-login``
- ``(remote branch)``  is the branch on the git remote repository. Usually is the ``staging`` or ``dev``. The ``master`` or ``main`` branch is rare to use to submitt a change.

### 3.  After we did the rebase we have two possibilities:
- If the rebase is complete, we can jump to step 4.
- If the branch has conflicts in order to resolve these, we need to go to the IDE and resolve it manually.
    ```idea
    Project Root > Git > Resolve Conflicts
    ```
- When we already resolved the conflicts then we execute the following command:
	```git
	git rebase --continue
	```
	
### 4. The rebase is already complete. Then we need to push
```git
git push origin your-branch
```
or (only if we have to force the push)
```git
git push -f origin your-branch
```
- ``origin`` is the local brand where we are working
- ``your-branch`` is your repository branch. Is important to know that **never** put this value as ``master-branch`` because we can overwrite the main-project and lose some changes.
- ``-f`` is for force the push

### 5. If we did more than one commit and thus branch is 2 commits ahead, we have to merge the commits with ``git rebase -i HEAD~2``
- For this case the number 2 is the number of commits that our branch is ahead of the master branch or the branch we want to rebase.
```
git rebase -i HEAD~X
```
- ``X`` represents the number of commits ahead of the master branch

- Finally, we need to repeat the step 4 
