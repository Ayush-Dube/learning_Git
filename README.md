if you delete a repository .....it will also delete your "activity history" of that repo. 

# ⚡Welcome to mastering Git

### git
- save and manage different versions of your files and code.
    - work with others
    -  keep track of changes
    -  and undo mistakes.

####  keywords
- Repository
- clone 
- stage
- commit
- branch
- merge
- pull 
- push

#### `Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!`

- Developers can work together from anywhere in the world.
- Developers can see the full history of the project.
- Developers can revert to earlier versions of a project.

```bash
git --version
brew upgrade git or sudo apt-get upgrade git
```


`git config --global user.name "Your Name"`  
- Note: If you make a typo or mistake, just run the command again with the correct value.  
  The new setting will overwrite the old one.


`git config --global user.email "you@example.com"`  

```
Use --global to set the value for every repository on your computer.
Use --local (the default) to set it only for the current repository.
```
#### Git uses your name and email to label your commits.

```
-git config --list
user.name=Your Name
user.email=you@example.com
core.editor=code --wait
alias.st=status
init.defaultbranch=main
```


To change a value, just run the git config command again with the new value.

To remove a setting, use --unset:



### Default Branch Name

Set the default branch name for new repositories (for example, main instead of master(old practice)):


```
git config --global init.defaultBranch main
```

#### Configuration Levels
There are three levels of configuration:  
```
System (all users): git config --system   
Global (current user): git config --global
Local (current repo): git config --local
The order of precedence is:
```
Local (current repo)  
Global (current user)  
System (all users)  

The reason to use the different levels is that you can set different values for different users or repositories.

This can be used for example to set different default branches for different repositories and users.
???????



#### Lets create our first repository

1. Start by creating a new folder for our project:
    - mkdir myproject  
      cd myproject

open the gitbash inside this freshly made folder

2. git init  
- What Happens When You Run git init?  
  - Git creates a hidden folder called .git inside your project.
  - This is where Git stores all the information it needs to track your files and history.

```bash
ls -a
.  ..  .git
```

3. create a index.html file
```
ls
indedex.html

git status 

 => git status
	On branch master

	No commits yet

	Untracked files:
  		(use "git add ..." to include in what will be committed)
    		index.html

	nothing added to commit but untracked files present (use "git add" to track)
```		



### Unntracked Fiiee
    An untracked file is any file in your project folder that Git is not yet tracking.
    These are files you've created or copied into the folder, but haven't told Git to watch.


#### What is a Tracked File?
A tracked file is a file that Git is watching for changes.

To make a file tracked, you need to add it to the staging area (covered in the next chapter). 

add . 
--------------------------
git add
  - git add index.html


git add . vs git add -all/git add -A

from present directory |  from the whole repo 
------------------------

How to Unstage a File
If you staged a file by mistake,
git restore --staged index.html

----------------------

What is a Commit?


A commit is like a save point in your project.
It records a snapshot of your files at a certain time, with a message describing what changed.

git log

see commit history

till here a history of ur code is created in ur computer , but still not on remote guthub account for that u have to git push origin main.

git commit -m "First release of Hello World!"


Commit All Changes Without Staging (-a)
You can skip the staging step for already tracked files with git commit -a -m "message".

This commits all modified and deleted files, but not new/untracked files.

samjh gya i dont have to add again and again that files that are alredy being tracked .

suppose agr koi nayi file banayi hai tb u have to add them and make them tracked 
other wise jo file already ek baar tracking list mei aa gayi usse baar baar track krne ki jarurt nahi 

----------------
If you just type git commit (no -m), your default editor will open so you can write a detailed, multi-line message:
---------------

git log
git log --online

git log --stat
------------

git tag

git tag <tagname> - Create a lightweight tag
git tag -a <tagname> -m "message" - Create an annotated tag
git tag <tagname> <commit-hash> - Tag a specific commit
git tag - List tags
git show <tagname> - Show tag details


A lightweight tag is just a name for a commit.
git tag v1.0

annotated tag 
git tag -a v1.0 -m "Version 1.0 release"

You can tag an older commit by specifying its hash:
git tag v1.1 1a2b3c4d

list all tags in repo
git tag

u will show list of tag code 

after this 
 git show tagCode

git show v1.0


Push Tags to Remote
By default, tags exist only on your local computer.

If you want others to see your tags, you need to push them to your remote repository.

If you don't push your tags, only you will see them, and only locally.

To push a single tag to your remote repository (for example, after creating a release tag):

git push --tags


delete tag locally

git tag -d v1.0

delete tag from remote repo

git push origin --delete tag v1.0


Use tags to mark releases, major milestones, or stable points in your project.
Always use annotated tags (with -a -m) for anything public or shared.
Create tags after passing all tests or before deploying/releasing code.


-------------------
git stash is not so easy.


