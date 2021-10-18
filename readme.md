# 	git study command basic



## check git config flie

```bash
# use follow commands can check your git config file (include user.name and  user.email)
git config --global # use global config file.
git config --local # use repository config file.
```

## create your git repository

```bash
cd [your develop content path] # switch to your dev folder
git init # create an empty git repository or reinitlize.
# and you can use .gitignore profile to let git ignore the file or dictionary	
```

## add file to git repository

``` bash
git add <filename> 
git commit -m "your commit message" # commit your last add status
```

## log and status

``` bash
git log [--graph] [--pretty=oneline] # check your log history use --pretty=oneline to show each log oneline.
git status # use this command can check the difference between current working directory and your git repositry. (if the print information is red, you must use git add or git rm <filename> to add or remove <filename> to the git stage; else is green that metion you need commit this status to your current git branch.)
```

> If the workflow is **the first modify -> `git add` -> the second modify -> `git commit`** . in this scene, git will just commit the first modify to yout repository, becasuse Git manage modify only. After use `git add`, git put your modify status to a temperory space which prepare to commit, but the second modify dose not excute `git add `  command, so it dose not deliver to the git control.

## reset

```bash
git reset --hard HEAD # reset the last version. you can use HEAD^, HEAD^^ ... to reset your git to last n version, if the version is too old you can use HEAD~[number] to a assign last version. and also use git log to find your target version id, then use [git reset --hard [version id]] to reset to the version you want.
```

> One more thing that must mentioned : if you operate in a wrong way that cause you can't find the wanted version id. Never mind, Git offer a command `git relog` which stores all commit id you operated.

## branch

> When you in a group, your boss appeal all of you to use git to control the current project. You need to do your programming in your own branch. After your work done, merge it to the master branch that will make the project workflow clean.

```bash
git branch # browser all branches
git branch <branch name> # create your branch
git branch --delete <branch name> # delete <branch name>
git switch [-c] <beanch name> # switch to your branch. [-c] can create new branch if branch not exist.
git merge <branch name> # merge the <branch name> to current branch
```



## remote 

> Git can remote your local repository to a center repository.
>
> After 2021.8.13 GitHub can not authentic email and password, instead use token. The location is home -> Settings ->  Developer settings -> Personal access tokens. you can generate your personal token here.  and use 
>
>  `git remote set-url origin https://<your personal token>@github.com/<username>/<remote repository>.git `
>
> to authentication.

```bash
# use following commands to push your existing repository from the command line.
git remote add origin https://github.com/<username>/<remote repository>.git
git branch -M main # The Github default branch is main now, you can modify it to master in Github.
git push -u origin main
```

## tag

> Learn by yourself.