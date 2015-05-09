# MEMO GIT


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
