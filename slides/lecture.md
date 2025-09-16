---
marp: true
title: Git & GitHub Lecture
paginate: true
theme: cake
#header: hello
#footer: goodbye
---

<!-- _paginate: skip -->
# Git & GitHub

### Version control with Git

<!-- This is a speaker note for the first page -->

👩‍🏫 Helen Kershaw
📅 Crocodile Workshop October 2025

---
# Why should I care about version control?

* You can recover previous versions of your project
* Multiple people can work on the same project 
* You can tag a version of code that was used with a particular paper
* Using version control is a great skill to have as you develop code, scripts, and figures 
*  *Anything* that you edit can benefit from version control

---

---

<div class="note" markdown="1">

Roughly 15,600 developers from more than 1,400 companies have contributed to the Linux kernel since 2005, when the adoption of Git made detailed tracking possible
The Linux Foundation

</div>

---
# Goals

- Understand Git basics
- Learn GitHub workflows  
- Practice branching, merging, and pull requests  

---

#  What is Git?

---

<!--
From original revision of git: 
-->

<small>

"git" can mean anything, depending on your mood.

 * random three-letter combination that is pronounceable, and not
   actually used by any common UNIX command.  The fact that it is a
   mispronounciation of "get" may or may not be relevant.
 * stupid. contemptible and despicable. simple. Take your pick from the
   dictionary of slang.
 * "global information tracker": you're in a good mood, and it actually
   works for you. Angels sing, and a light suddenly fills the room. 
 * "goddamn idiotic truckload of sh*t": when it breaks


https://github.com/git/git/blob/e83c5163316f89bfbde7d9ab23ca2e25604af290/README

</small>

<!--
[Git README](https://github.com/git/git/blob/master/README.md)
-->

---

# What is Git?



<div class="box-container">
   <div class="box" style="width: 40%;" markdown="1">

- Version control system  
- Tracks <span class="highlight">changes</span> in files  
- Supports collaboration  

   </div>

   <div class="box-no-border" style="width: 40%;" markdown="1" data-marpit-fragment markdown>

    The <span class="highlight">commit</span> is the unit of change

   </div>

</div>



---

# Git concepts

* **Repository** - a place to store all the changes to your project over time
* **Remote** - a repository that is hosted somewhere else, for example on Github

---

# Git concepts

working with git follows this pattern:

Edit / add / commit

- Edit your files with your new amazing science (this bit is up to you).
- git add - add a change to the staging area.
- git commit - take a snapshot of the project

<div data-marpit-fragment markdown="1">

The **commit** is what is saved in your git repository

<div>

---

## GitHub

Github is a place to store your git repositories online, with some social media aspects. 
There are other services you can use, for example <span class="highlight">Bitbucket</span> and 
<span class="highlight2">GitLab</span>.

---

# Git concepts

pull / push

  git pull -  get the latest updates from a remote repository
  git push - push your changes to the remote repository

---

# Getting started

Let’s set up your git environment
we’ll set up
- the name and email you want to use with git 
- the editor you want to use for writing git commit messages

---

# Setting up your git environment

Set your username and email that you want to be linked with git.  
What you select here will be the ‘author’ information for your commits.

```
git config --global user.name “Margaret Hamilton”
git config --global user.email mhamilton@nasa.gov
```

---

# Setting up your git environment

Set the editor you want to use for commit messages, vim, nano, emacs, notepad++, whatever your favorite editor is.

In this example, I am setting my editor for commit messages to vim. 


`git config --global core.editor vim`

Note this doesn’t mean you have to edit all code with vim. 
This just means git will open vim when it wants you to write a commit message

---

# Setting up your git environment

To display what your git settings are use:

`git config --list`

---

# Exercise 1: create a repository

```
mkdir my-first-repo   
cd my-first-repo      
```

Create a .gitignore file to tell git which files to ignore.  
See the next slide for an example .gitignore file

`git init`

Check the status of your repository:

`git status`

Add your .gitignore file to your repository. 

`git add .gitignore`

---

# Example. gitignore file

<div class="box-container">
   <div class="box" style="width: 40%;" markdown="1">

```
# files for git to ignore. 
*.log 
*.o
*.mod 
*.pyc
```

   </div>

   <div class="box" style="width: 40%;" markdown="1">
   It is useful to set up a .gitignore file when you start a project to prevent accidentally adding giant files to your repository

   </div>
</div>

<div class="fragment" markdown="1">

This .gitignore file means that in this repository, any files that end in .log, .o, .mod or .pyc will not be tracked.   This makes life easier because you can add whole directories without worrying about adding files you don’t want to track, 
`git add .`

</div>

---

<div class="note" markdown="1">

⚠️ **Important:** This content is highlighted in a box.

</div>

---

# Writing good commit messages

one line short summary of the change

more detail if needed on why you changed what

```
Place ring in Mount Doom

Ring is destroyed, Sauron loses his power forever. All he created collapses, 
the Nazgûl perish, and his armies are thrown into such disarray that 
Aragorn's forces emerge victorious.
```
---

# Viewing the status of your repository

To see which files have been edited, which have been added to the staging area and any files that are not being tracked by git, use git status

---

# Undoing changes

Checkout an earlier version of a file

`git checkout hash filename`

For example:

`git checkout 73eba0ddb Money`

---

# Undoing changes

Undoing an add - use this if you accidentally added some changes you don’t want to commit
git reset HEAD filename
This won’t undo your changes to the file, it only takes the changes out of the ‘to be committed’ area. 

To undo (discard) your changes to a file
git checkout -- filename

Note: Changes that are not committed are lost


---

The output from `git status` gives the instructions for unstaging and 
discarding changes:



---

# Exercise 2: Clone a repository from GitHub

Explore a repository on Github, here are a couple of examples 

https://github.com/hkershaw-brown/poems
https://github.com/ESCOMP/CESM

Have a look at the commits and the contributors. 

Clone - download a copy of the repository to your machine
git clone https://github.com/hkershaw-brown/poems.git

Checkout an earlier version of the repository git checkout #hash

---

# Exercise 3: Fork a repository on GitHub

Fork vs. Clone

<div data-marpit-fragment markdown="1">

**Cloning** is copying a repository.  For example, to run someone else’s code you can clone their repository.  git clone repository-address downloads the code to your machine.  You can use git locally, but if you want to push your changes to github you will need permission to write to the repository on github.

</div>

<div data-marpit-fragment>

**Forking** is creating your own version of the code on github.  You can now change the code and push those commits to github.  

</div>

---

# Exercise 3: Fork a repository on GitHub

Pick a repository on github and create your own fork of that repository




---

# Working with remote repositories

To list the remote for the repository
git remote show origin

To get changes from the remote repository
git pull 

# Working with remote repositories

Storing local changes while you pull from a remote repository
Sometimes the changes you pull from a remote repository will conflict with your local changes. You can stash your local changes, pull the new changes from the remote repository, then pop your changes back.
git stash
git pull
git stash pop

---

# Working with remote repositories

Here is an example message when pulling changes conflicts with your local changes


---

# Exercise 4: Putting your repository on Github

You can use the repository from Exercise 1 or use your own code if you have some. For your own code, think about whether you want the repository to be public or private. You can share private repositories with other people if you choose. Public repositories are visible to the world.


Extra credit fun with a friend:
Partner up with someone and invite them to be a collaborator on your repository.  What happens when you both make changes to the same file.  What happens when you try and push these changes to the repository.  Can you sort out any conflicts?



---

# Next steps

Once you are comfortable with git and tracking changes through time, you may want to do some of the following: 

- Use branches to work on new features
- Use tags to identify versions of your code
- Make DOIs for your code on github for you published papers
- Think about what license you should choose for your code
- Submit pull requests to contribute to other projects 
- Use github issues for your code todo lists
- Find your favorite tools for working with Git
- Share your wisdom with your labmates

---


# Have Questions? Need Help?

