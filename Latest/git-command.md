
# Git Command                   Description 

git add                       This command adds all the new files to the initialize repository 
git archive                   This command can create a zip or tar file of the content from your repository. 
git branch                    This command print all the branch linked to that repository. 
git branch branch_name        This command will add a new branch to the repository with name branch_name 
git checkout                  With checkout command, we can switch from one branch to another branch 

git clone
example:

git clone [urls]
                              Using this command you can clone an existing repository or directory to your system. 
git commit –m “message”       The commit command record the file in the previous version 

git config
example:

git config –global user.name “Username”
git config –global user.email “useremail@”
                            This command is used to set the author’s username and email address when the commit is done. 
git diff                    The diff command is used to show the difference of the files which are not staged 
git fetch [url]             Download object from another repository 
git –help                   Print the most commonly used commands 

git init
example:

git init [directory name]
                          This command is used to initialize a new directory or repository to the git. 
git log                   This command is used to print the list of all the version history 
git merge                 This command can be used to merge any branch with the current branch. 
git mv filename           This command is used to move or rename any file, directory or a symlink 
git pull repository_url   This command is work just opposite of push command, with this command you can bring the changes in your local                           repository if anyone had made changes on the remote repository. 
git push
example:
git push origin master
                        With push command we can push or commit changes in the master branch, that will reflect on your remote                                    repository. 
git remote              This command can connect your repository with the remoter server. 
git reset               The reset command is the opposite of commit command and undoes the commit statements. 
git rm filename         The rm stands for removal, and this command is used to remove a specific file from the repository. 
git show                This command is used to show all the objects of the directory, it simply shows all present code. 
git status              The status command used to list all the files which have been committed. 
git tag commit_ID       With tag command, we can tag some specific commits. 
git –version            Show the git suite version. 
git-add                 Add a net content to the index 


# To set a repository
◾ git init

◾ git clone

# To make changes on the files

◾git add
```
git add -p

/* Rather than git add everything or individual files, this -p will allow you to step through each change, or hunk, and decide if you’d like to commit it. */

```
◾ git mv

◾bgit reset

```
git reset --soft HEAD~3

/*
A soft reset will keep your changes but allow you to “uncommit” something.

Instead of doing a squash, Dan prefers to dial back HEAD any number of commits and then add & commit everything into a single commit.



*/

```

◾ git rm

# To check the history
◾ git bisect

◾ git grep

◾ git log


```
git log -5 --pretty --oneline

/* View your last 5 latest commits each on their own line. */

e.g 

$ git log -5 --pretty --oneline
70842e4 (HEAD -> feature/UI_UX-research, origin/master, origin/feature/UI_UX-research, origin/HEAD) unit test
3e244df added environment variable
a045149 unit test errors
ffcf69e refactored
ab00a75 factory implementation



$git log --all --graph --decorate --oneline --simplify-by-decoration

* 70842e4 (HEAD -> feature/UI_UX-research, origin/master, origin/feature/UI_UX-research, origin/HEAD) unit test
| * 8b7524b (refs/stash) WIP on UI_UX-research: ab00a75 factory implementation
|/
* 358a7a7 (master) removed bootstrap
| * c9f8e23 (origin/feature/TAG-7675-implement-ui-ux-framework) added client enum
|/
| * 495b739 (origin/TAG-7490-7479) TAG-7490 Basic UI creating
|/
* 437db94 (origin/TAG-7447-7) added scss styling to header component
* af976b4 (origin/TAG-7447-fix-cloudfront-dis-2) Merge branch 'master' of ssh://code.devtools.lumeris.com:7999/por/provider-search-app into TAG-7447-fix-cloudfront-dis-2
* e18b3b6 (origin/TAG-7447-fix-cloudfront-dist) Fix Cloudfront alias
* edcaeb9 (origin/TAG-7447-4) added common tag and modified environment specific tags
* f93fff2 (origin/TAG-7447-2) add junit reporter
* 89dda62 (origin/TAG-7447) updated parameters and added uat
* c58370b Initial commit

```

◾ git shortlog

```
git shortlog -sn

/*Quickly get a list of contributors and see how many commits each person has.
e.g $ git shortlog -sn
    43  Sirajuddin Shaik
    17  *****
     8  ******
     2  ****
     1  ***
     1  *

*/
```

◾ git show

◾ git status


# To grow and mark the changes or history
◾ git branch

◾ git checkout


```
git checkout pr/123

/* Quickly check out a remote for pull request review. You’ll need to set it up like this.     */

git checkout -

/*   jump back to to your last branch.        */
````
◾ git commit

◾ git diff


```
$ git diff --shortstat "@{1 day ago}"
 29 files changed, 227 insertions(+), 166 deletions(-)
 /* See how many lines of code you have written last day      */
```
◾ git merge

◾ git tag


# To work in collaboration
◾ git push

◾ git pull

◾ git fetch

◾ git reflog

```
“Don’t worry, it’s probably saved somewhere”. Git reflog allows you to see every step you have made with git allowing you to retract and reinstate your steps.

```

