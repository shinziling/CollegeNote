# What is Git?
Git is a open source version-control system(VCS) to help manage code and files for a specific project.
- Often used in a collaboration environment where multiple people are working on the same project.
- Some cloud-based platforms such as Github or Gitlab allow the usage of git to backup project to a user repository on their website.  

# Getting Started
>[!info]
>This article will go over the basic function of git, it will go over the basic terminal based commands with a test repository I've created on Github. You can use any terminal of your choice but I recommend using a terminal that runs on UNIX command line terminal. You can always  run `git help` any time in the terminal to get a list of git commands.
-  First make sure that git is properly install on your local machine run the command
```bash 
git -v
```
It should pop up something along line of `git version [verison number]` if not, go to this [link](https://git-scm.com/downloads) to download it. 

## Now to initialize a local git repository
- First create a folder/directory where you would initialize git
	- You can create a folder using the terminal if you would like with the following command then `cd` into the folder you just made
```bash 
mkdir [folder_name] # Make a directory
cd [folder_name]    # change directory 
```
- Now run this command inside the folder/directory you just made
```bash 
git init
```

>To check if you properly initialize git run `ls -a` you should see a `.git` file listed

To configure your user information for the current repository you're in run 
```bash 
git config user.name "Some name goes here"
git config user.email "Some email goes here"
```

>To configure your information for all repo use `--global` after `config`

>[!note]
>Now note this is only a local repository generally speaking we would like to link a remote repository to the local repository this way we can always push any changes made on the local repo to the remote repo. This allows us to have a backup of our project we can always clone from.
## Linking a remote repository 

To link a remote repository run the following command in your local repository
```bash
git remote add origin [remote_repo_url]
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
>If you see something like this then you have successfully link the repo.
>` origin  https://github.com/shinziling/testRepo.git (fetch)`
>`origin  https://github.com/shinziling/testRepo.git (push)`




