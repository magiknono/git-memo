# MEMO GIT
release 0.1

##**Best practices** :

> Only commit small changes from a topic! no big feature or mixed topics 

> Only commit commit completed work  (feature implementation...) 

> Only commit tested code that works 

> Commit often! Push often ! 

> A new branch for every new feature or bugfix 

>An experimental local branch for testing stuffs 

A long running branch dev(optional)

###- Configure Git
```
git config --global user.name "Prenom Nom"
git config --global user.email "prenom.nom@monemail.fr"
git config --global color.ui auto
```

###- Starting with an unversionned project
```
cd myproject/folder
git init
```
###- Starting with an existing project on a server
```
cd your/folder
git clone https://github.com/magiknono/git-memo.git (prefixed with https / ssh / git)
```
###- Add and Commit
```
git add . (all files in the directory will have changes to be commited)
git add nomdufichier folder/* (selected files will have change to be commited)
git commit -m "Initial commit"
```
###- Remote repo - establish relations without dl
```
git remote add nom-repo url
git remote -v (list)
```
###- For ssh, need a public rsa key
```
ls ~/.ssh (if existing)
ssh-keygen -t rsa -C "nom.prenom@monmail.com" (to generate)
```
###- status
```
git status (display changes not staged for status / changes to be committed / untracked files)
```
###- remove a tracked file for the next commit
```
git rm nomdufichier.ext
```
###- project's commit history
```
git log # -p for the detailed changes of each commit
```
###- Branches : differents working contexts !
```
git branch git-memo (create a new branch)
git branch -v       (list all branches with more details -va)
git checkout git-memo  (switch to the branch)
git checkout -b git-memo   (create a branch and switch to this branch)
```
###- Stach : saving changes temporarily (no commiting) !
```
git stash          (save a stash)
git stash list     (list all current stash)
git stash pop      (apply the newest stash and clear it from stash dashboard)
git stash apply <stashname> (apply the stash but it remains saved)
git stash drop <stashname>  (remove a stash saved)
```
tips : apply the newest stash when no arguments with this 3 laters cmd

**STASH is helpful to get a clean working copy**

 *before checking out a different branch...*

 *before pulling remote branch...*

 *before merging or rebasing a branch...*


###- Merging : integrate a feature branch in prod branch or integrate features branch in your branch (much changes)


####-Integrate to master
```
1.git checkout master
2.git merge git-memo
3.git log
```
####Merge conflict
```
1.detect with git statuts > see unmerged paths
2.clean up the file in editor or using a merge tool
3.git add filename
```
####Undo a merge
```
git merge abort
```
####Rollback to the commit before and start again
```
git reset --hard
```
###- others basics
```
git fetch nomrepo (read)(after made a git remote add repo branchname)
git checkout --track repo-name/branch-name (create a new local branch based on it)
git push
git push name-repo branch-name
```
###- integrate remote changes
```
git fetch origin
git log origin/master
git pull origin master  = fetch (dl data) + merge (integrates data in working copy)
```
###- Pushing a local branch
```
git checkout branch-name (select)
git push -u origin branch-name (push and -u make a relation between local and remote branch)
git branch -d branch-name (delete branch also -dr delete local and remote)
```
###- Fixing the LAST commit (NEVER amend a commit that has been pushed to a remote repo)
```
git commit --amend "the correct message"
```
OR
```
1.git add filenamethathaschanged
2.git commit --amend -m "commit message"
```
###- UNDOING LOCAL CHANGE
```
git checkout -- file/to/restore.ext (restore to its last commited version)
git reset --hard HEAD (discard all current changes in your working copy and restore the last commited version of your complete project)
git reset HEAD^  (reset one commit before HEAD)
```
###- UNDOING COMMITED CHANGE
```
git revert 2b45b2 (undo with the hash you want to revert)
git reset --hard 2b4b5 (rolling back/restore to an older revision, commits after are lost)
```
###- Differences
```
git diff
git log -p
git diff master..git-memo  (compare master with memo-git)
```
