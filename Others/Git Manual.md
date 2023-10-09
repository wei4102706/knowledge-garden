#### Template
Issue #1:
问题：
原因： 
解决方法：
1. 

Issue #1:
问题： 更新被拒絕，因為您目前分支的最新提交落後於其對應的遠端分支
原因： local branch is behind the remote branch
解决方法：
1. `git stash` to keep local changes
2. `git pull origin main` to pull the latest changes from the remote repository
3. `git stash apply` to apply the changes stashed earlier. * may encounter conflicts that you'll need to resolve manually. Open the conflicting files, look for the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), and resolve the conflicts.
4. `git add . git commit -m "Resolved merge conflicts and added my changes"` 
5. `git push origin main` to push your changes to the remote repository.

Issue #2:
问题： committed changes using the wrong Git account
解决方法：
1. Configure Git User for the Repository
```
git config user.name "wei4102706"
git config user.email "kathylo0706@gmail.com"
```
2.  Amend the Last Commit
```
git commit --amend --reset-author
```
3.  Force Push (Caution)
```
git push origin main --force-with-lease

```
**Optional: Global Configuration**
Set current user as the default for all repositories:
```
git config --global user.name "wei4102706"
git config --global user.email "kathylo0706@gmail.com"
```

Check current config:
```
git config user.name
git config user.email
```
add `--global` for checking global config