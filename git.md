<div dir='rtl'>بنام خدا</div>
<div dir='rtl'>خلاصه ای بر گیت</div>
###### top


- [Some Sequence Code](#some-sequence-code)
- [Stach](#stach)
- [Deletion](#deletion)

[top](#top)
### Some Sequence Code
```bash
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
### Stach Working
```vala
git stash //Save all changes in Memory, it is needed before changiing Brach when you did not commit changes.
git stash --keep-index //the same only tell GIT: do stash only which in stage
git stash -u //Git will also stash any untracked files you have created.
git apply //apply stash on current Branch
git apply --index //the same with affect on stage
git stash branch NewBranchName //create, switch into and pop stash into NewBranchName
//it may we stash more than one changes.
git stash list
git stash drop stash@(No.)
git clean -f -d(->subDir) -i(->Interactive flag) -n(->Verbose) -x(->fully clean)

```
flow between versions
```vala
  git log --> in result you should find commit number of wich version you would.
  git checkout CommintSerialNumber --> Now you where there.
  git checkout -b NewBranchNameForOldVersion CommitSerialNumber --> your mentioned version would on NewBranchNameForOldVersion.enjoy it.
```
Merge Or Rebase?
* merge will merge current branch with BranchName , keep BranchName, the flow isn't linear.
* rebase will merge current branch with BranchName , you are free to delete BranchName, 

- Connect to None-trusted git-server : 
  ```vala
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
 some times may you push dangerous data, so you could delete it:
 ```bash
  git checkout --orphan latest_branch
  git add -A
  git commit -am "commit message"
  git branch -D master
  git branch -m master
  git push -f origin master
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
