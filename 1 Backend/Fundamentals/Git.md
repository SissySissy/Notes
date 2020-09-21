# Git

https://danielkummer.github.io/git-flow-cheatsheet/

## getting started



1. initialize a repository `git init`
2.  check what is there `git status`
3. stage changes `git add <filename>`, to unstage `git rm --cached <file>`
4. commit changes `git commit -m "your message in brackets"`
5. create a new branch, and move into that `git checkout -b <my branch> `
6. check what branches are there `git branch `
7. create a repo through github interface
8. connect that repo to what you are doing `git remote add origin https://github.com/cubeton/mynewrepository.git`
9. Push the local repo to online repo `push -u origin master`
10. Now push the recent commit, git will create automatically the new branch on the online repo `git push origin <my branch> `
11. get the most recent updates `git pull origin master`
12. check the history with `git log`
13. to switch back to the master branch do `git checkout master`



### pull request

A pull request (or PR) is a way to alert a repo's owners that you want to make some changes to their code. It allows them to review the code and make sure it looks good before putting your changes on the master branch.

git commit -a -m (message)

git config --global username and email

git log

git push origin??

got add . (x nuovi files)



add is staging, commit, then push

-a se tutto automatic

Gh-pages to have simple pages to see online



## Starting new feature

1. create a new branch on Jira kanban

2. git flow init (for new projects)

3. git flow feature start NOEZL-11-footer

4. git status (check where you are)

5. npm run dev

6. on atom click fetch, check updates, stop gulp process

7. in the theme folder cd/ git check out -b

8. Wp-database import, wp database update, wp user create, login with new wordpress admin

9. wp_cli commands?

10. git fetch, starting progress, feature finish NAMe-footer

11. Commit message NAME #progress

12. restart gulp

    

## Viewing project history

At any point you can view the history of your changes using

```
$ git log --oneline
```

If you also want to see complete diffs at each step, use

```
$ git log -p
```

Often the overview of the change is useful to get a feel of each step

```
$ git log --stat --summary
```



# Create new branch

`git branch namebranch` creates a new branch

git knows that after `-b` every word will be part of the branch's name until another parameter (or end of line) is found.

Specifying -b causes a new branch to be created as if git-branch were called and then checked out.

It first creates the new branch and then automatically checks you out to that branch so that you can start working within that branch.

```
$ git checkout -b myFeature dev
```

`git branch -a` shows branches

`git checkout branch name`to switch to another branch

`git --help`