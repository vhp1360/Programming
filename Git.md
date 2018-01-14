<div dir='rtl'>بنام خدا</div>
<div dir='rtl'>خلاصه ای بر گیت</div>

###### top

- [Config Git](#config-git)
- [Some Sequence Code](#some-sequence-code)
- [Stash](#stash)
- [Deletion](#deletion)
- [Common Errors](#common-errors)
- [Forkinf and Rebasing](#forking-and-rebasing)


[top](#top)
### Config Git
at first time when you want connect source to existing repository:
```vim
  git init
  git add .
  git config --global user.name "Full UserName"
  git config --global user.email "Your Email"
  git remote add RemoteName ssh://git@IP/UserRrepoName/RrepoName.git
  git stash .
  git pull ssh://git@IP/UserRrepoName/RrepoName.git
  git reset --merge <-- if you faced needs merge error: you need to resolve your current index first
  git stash branch NewBrach <-- if you'd like or
  git commit -m "Message"
  git push -f RemoteName <-- if you faced Updates were rejected because the tip of your current branch is behind
  git reset --hard <sha1-commit-id>
```


### Some Sequence Code
```vim
  git init
  git status
  git add
  git commit -m "message"
  git log
  git remote add origin Url/repository.git
  git push -u origin master //The -u tells Git to remember the parameters, so that next time we can simply run git push
  git push origin master
  git diff  //take a look at what is different from our last commit
  git diff --staged //look at what files changed in stages
  git reset  //unstage a file
  git checkout -- 
  git branch Name //New branch
  git checkout BranchName //switch to branch
  git rm //remove files
  git merge BranchName //merege BranchName with this Branch
  git branch -d BranchName  //delete BranchName
  git pull 
  git hist
  git branch //list of branch
  git ls-tree BranchName //show files in BranchName
  git branch -m <oldname> <newname> //Rename Branch

```

[top](#top)
### Stash Working
#### Why Stash?
Imagine you are in below state, what will you do?:
  - 1. You do not want to commit your unfinished work but need to switch to a new branch to start some new work immediately.
  - 2. A git pull results in conflicts however you do not want to commit local changes yet.
  - 3. You realize you have worked in the wrong branch and want to move your uncommitted work to the right branch.
the _Stash_ is solution. __It saves the working directory and index to a safe temporary place (the latest stash is usually at .git/refs/stash).__
```vim
git stash //Save all changes in Memory, it is needed before changiing Brach when you did not commit changes.
git stash --keep-index //the same only tell GIT: do stash only which in stage
git stash -u //Git will also stash any untracked files you have created.
git apply //apply stash on current Branch
git apply --index //the same with affect on stage
git stash branch NewBranchName //create, switch into and pop stash into NewBranchName
//it may we stash more than one changes.
git stash list
git stash pop stash@{No.}
git stash drop stash@{No.}
git stash clear
git clean -f -d(->subDir) -i(->Interactive flag) -n(->Verbose) -x(->fully clean)
```
flow between versions
```vim
  git log --> in result you should find commit number of wich version you would.
  git checkout CommintSerialNumber --> Now you where there.
  git checkout -b NewBranchNameForOldVersion CommitSerialNumber --> your mentioned version would on NewBranchNameForOldVersion.enjoy it.
```
Merge Or Rebase?
* merge will merge current branch with BranchName , keep BranchName, the flow isn't linear.
* rebase will merge current branch with BranchName , you are free to delete BranchName, 

- Connect to None-trusted git-server : 
  ```vim
    git config --global user.name "YourName"
    git config --global user.mail "Email"
    git init
    git add .
    git commit -m "Some Message"
    git remote add origin {https://Server-Name:Port/YourName/YouRepoName.git|git@Server-Name:YourName/YourRepoName.git}
    git clone {https://Server-Name:Port/YourName/YouRepoName.git|git@Server-Name:YourName/YourRepoName.git}
    export GIT_SSL_NO_VERIFY=true
    git push -u origin master 
  ```
 
 [top](#top)
 ### Deletion
 - some times may you push dangerous data, so you could delete it:
 ```vim
  git checkout --orphan latest_branch
  git add -A
  git commit -am "commit message"
  git branch -D master
  git branch -m master
  git push -f origin master
```
- Delete commits from a branch in Git
```vim
  git reset --hard HEAD  <- delete current Work and get back you to most recent commit.
  git reset --hard HEAD~1 <- will back you to previous Commit
  git push origin HEAD --force  <- remove current 
  git revert ...   <- if you push it already
  git reset --hard <sha1-commit-id>
```

[top](#top)


### Common Errors
- Git refusing to merge unrelated histories:
  - During git rebase origin/development following error message is shown from git:
  ```vim
    fatal: refusing to merge unrelated histories
    Error redoing merge 1234deadbeef1234deadbeef
  ```
  then should:
  ```vim
    git pull origin master --allow-unrelated-histories
    git merge origin origin/master
    ... add and commit here...
    git push origin master
  ```

[top](#top)
### Forkinf and Rebasing
[According this Doc](https://help.github.com/articles/fork-a-repo/), 
```vim
  git clone https://github.com/YOUR-USERNAME/Repo.git
  git remote add upstream https://github.com/octocat/Repo.git
```
  - Keep Fork Up2Date:
  ```vim
    git fetch upstream
    git merge upstream/master
  ```
  



[top](#top)
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
