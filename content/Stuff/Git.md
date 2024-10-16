# What is Git?
Git is a open source version-control system(VCS) to help manage code and files for a specific project.
- Often used in a collaboration environment where multiple people are working on the same project.
- Some cloud-based platforms such as Github or Gitlab allow the usage of git to backup project to a user repository on their website.  

# Getting Started
>[!info]
>This article will go over the basic function of git, its basic command line terminal. You can use any terminal of your choice but I recommend using a terminal that runs on UNIX command line terminal. You can always  run `git help` any time in the terminal to get a list of git commands.
-  First make sure that git is properly install on your local machine run the command
```bash 
git -v
```
It should pop up something along line of `git version [verison number]` if not, go to this [link](https://git-scm.com/downloads) to download it. 

## Now to initialize a local git repository
1. First create a folder/directory where you would initialize git
	- You can create a folder using the terminal if you would like with the following command then `cd` into the folder you just made
```bash 
mkdir [folder_name] # Make a directory
cd [folder_name]    # change directory 
```
2. Now run this command inside the folder/directory you just made
```bash 
git init
```
>[!note]
>You can run `git init` in any folder that you would like to track changes it does not have to be an empty folder/directory. Just `cd` into the folder you would like to track changes and run `git init` to set up git in that folder

>To check if you properly initialize git run `ls -a` you should see a `.git` file listed

To configure your user information for the current repository you're in run 
```bash 
git config user.name "Some name goes here"
git config user.email "Some email goes here"
```

>To configure your information for all repo use `--global` after `config`

>[!note]
>Now note this is only a local repository generally speaking we would like to link a remote repository to the local repository this way we can always push any changes made on the local repo to the remote repo. This allows us to create a backup of our project in case any goes wrong.  I will cover this later but for now we just go over basic git command.

## Staging

After creating our local repository we can start using git for real 

1. First in your local repository add some files to your local repo. I will add a README.md file to illustrate this, we can use the terminal to add the file and make changes to the file. Run this command in your local repo.
```bash 
touch README.md # This would create a file with the name README.md
```

Add something to the file with the editor of your choice then run the command 
```bash 
git add README.md # this would add the file changes to the stage environment
```
> You can run `git add .` to add all the files to the stage environment
> To remove a stage change run `git rm [file_name]`



To see all the files in the stage environment run 
```bash 
git status
```

>[!note]
>Note when running `git add .` you may have added file that you do not want to commit if so add a `.gitignore` file in the repo. Then add the the name of files you do not want to be added to the stage environment in the `.gitignore` file

2. After staging all the files we can now commit the change
```bash 
git commit -m "some message goes here"
```
> People often get confuse with the `git commit` command, what commit do is that it create a point in history of the changes you have made in which you can view all the commits that have been made using `git log`. And let say you accidentally stage a change to a file you did not meant to make using the `git add` command you can then revert the change using `git restore` to revert the file to its last commit. Git will generally tell you how to revert the change when you run `git status`. Normally it will probably be something like this: 
> 1. `git restore --staged [file_name]` 
> 2. `git restore [file_name]`
>> Run both command in the order that is listed above

## Branching

Branching is of most utmost importance when it comes to git. Generally, we do not want to make changes directly to the main(sometimes called master) branch, so we would create a new branch off of the main branch or do a fork(covered later). The new branch will be based off of the latest commit that has been made to the main branch at the time the new branch was create; in other words you can have multiple branches off of the main branch at different commit history. 
- This allows us to make any changes we want without modifying the content within main/master branch. 
	- Useful when we want test a new feature we would like to implement to the main branch.
	- And when we want to implement those feature to the main/master branch we can just do a merge.
1. To create a new branch run these command in your local repository
```bash
git branch [name_of_the_branch]    # create the new branch if it didn't already exist
git checkout [name_of_the_branch]  # switch to the new branch
```
> You can also use `git switch` instead of `git checkout` they essentially do the same thing if no unique flags are given. `git switch` is basically a split off command of the `git checkout` command. To further understand these two commands I recommend reading the official git documentation for [switch](https://git-scm.com/docs/git-switch) and [checkout](https://git-scm.com/docs/git-checkout). 

>[!tip]
>You can simplify the process of creating a branch and switching to the branch in one terminal line command. Simply run 
>- `git checkout -b [branch_name]` or
>- `git switch -c [branch_name]`
>> Both command will create and switch to the newly created branch

> To see all existing branch simply run `git branch` and to remove a branch run `git branch -d [name_of_the_branch]`

Now let suppose we edit our README.md in our newly created branch. This change is only present within the newly created branch and not the main branch. If we want to implement the changes to the main branch we would do a merge on the main branch
1. First change back to the main branch 
```bash 
git checkout [name_of_the_main_branch] # most likely to be called master or main
```
2. Now do the merge
```bash 
git merge [name_of_the_other_branch]
```
> This would update the main branch content to match the newly created branch

>[!info]
>There is other ways to merge two branch together such as `git rebase` but on the most basic level a `git merge` would do since that is the one people understand the most. Also, although it is called `merge` they do not actually merge together into one branch, the branch that you did the merge from still exist and you can still work on that branch.

To merge main branch content on to another branch, let say someone did a commit to the main branch and you want to see if that commit still works with the feature you are working on in the current branch, you would do the exact same step as above but instead being in the main branch you would just be in the current branch you are working on and do a `git merge [name_of_the_main_branch]`. 
- You can also do a merge between two branches that is not the main branch
	- Let say you have `branch1` and `branch2` and both branches are not the main branch, but you can still perform a merge on `branch1` from `branch2` and vice versa. 

>[!important]
>A merge conflict may occur when merging two branches together if this happen git will abort the merge and require the user to resolve the conflict before proceeding with the merge again. To see conflict files do a `git status` and after fixing the conflict do a `git add .`  or `git add [name_of_conflicted_files]` (there can be more than one conflicted files) to stage the change and then  `git merge --continue` to continue the merge. Generally speaking you can do `git status` again after resolving the conflict and it will typically tell you what to do to continue the merge.
>>If you're really stuck do a `git merge --abort` to abort the merge completely or do a `git reset --hard` this would reset your branch to its last commit state but do note it will remove all uncommitted changes.


## Three-Way Merge vs Fast-Forward Merge

When performing a `git merge`, without any configuration, git would do either a fast-forward merge or a three-way merge depending on the situation. 
1. A fast-forward merge will occur by default if there is no divergent in its commit history between the two branches. 
2. A three-way merge will occur by default if there is divergent.
Here is a [video](https://www.youtube.com/watch?v=zOnwgxiC0OA) that explains it better with motion graphic. The video also goes into the technical differences between `git rebase` and `git merge`. 
>In Layman's language, a `git rebase` will re-anchor your commits to tip of the latest commit made on the main branch in order to make the commit history linear. This makes the commit history easier to read and understand but it does have a downside of rewriting commit history and makes it hard for other people working in the same branch to merge their commits as it makes it confusing, and makes it a pain to debug and resolve conflict. In other words do not use `git rebase` on a public repository where there are other people working on it, only used it in your own local repository or a private remote repository(we will talk about remote repository later).
>> As long as you follow this quote from the Git official documentation about [rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing) you will be fine
>> - **"Do not rebase commits that exist outside your repository and that people may have based work on."**
# Using Git Hosting Service

> [!info]
> For this section I will be using a test repo I have created on Github. You can use other services if you would like. 
## Linking a remote repository 
1. First we would like to link the remote to our local

To link a remote repository run the following command in your local repository
```bash
git remote add [remote_name] [remote_repo_url]
```
As mentioned above I will be using a test repo I created, so I would run the command like this 
```bash 
 git remote add origin https://github.com/shinziling/testRepo.git
```
Now run
```bash
git remote -v
```
>[!success]
>If you see something like this after the command `git remote -v` then you have successfully link the repo:
>>`origin  https://github.com/shinziling/testRepo.git (fetch)`<br>
>>`origin  https://github.com/shinziling/testRepo.git (push)`
>
>It may not say `origin` for you depending on what you name the remote



>To remove the remote repo just run `git remote rm origin`

## Cloning


## Tracking




