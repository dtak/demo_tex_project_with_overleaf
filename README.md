# demo_tex_project_with_overleaf

Shows how to make a git repository for LaTeX document that has TWO remote locations:
* one on Github (to easily share .tex source files with other folks)
* one on Overleaf (to easily display and edit doc in browser)

This repo itself is a working example! 
Go to the corresponding Overleaf page:
[https://www.overleaf.com/12112063hyqwrddhndqq/](https://www.overleaf.com/12112063hyqwrddhndqq/)

You'll see the files there are the same as the files in this repo.


## Workflow (do this every time you edit your document)

** Prerequisite: Assumes that you have done the Setup steps below **

After edits on Overleaf, which you want to synchronize to the github remote repo:
```
git pull overleaf master
git push github master
```

After edits on Github, which you want to synchronize to the overleaf remote repo:
```
git pull github master
git push overleaf master
```


## Setup (do this once)

### (1) Create a new project on Overleaf

* * Goto overleaf.com 
* * Click New Project
* * Click the Share button (on top of screen)
* * Copy the Clone with Git link

Example link: `https://git.overleaf.com/12112063hyqwrddhndqq`

If you have an existing project, just copy its link.

### (2) Clone the overleaf remote repo on your laptop

First, clone the repo into a folder of your choice on your local machine:
```
cd /path/to/your/repos/
git clone https://git.overleaf.com/12112063hyqwrddhndqq
```

Rename your local repo to something useful:
```
mv 12112063hyqwrddhndqq demo_tex_project_with_overleaf
cd demo_tex_project_with_overleaf/
```

Rename the remote repo so it is called "overleaf"
```
git remote add overleaf https://git.overleaf.com/12112063hyqwrddhndqq
```

If you like, we recommend you remove the "origin" remote to avoid confusion:
```
git remote rm origin
```

### (3) Create a new repository on Github

* * Goto github.com/dtak/ (or wherever your home is on github)
* * Click the New button (green)
* * Setup the description etc. as you wish and click OK
* * Copy the "Clone" link

Example link: `https://github.com/dtak/demo_tex_project_with_overleaf.git`

If you have an existing Github repo you want to integrate, just copy its link.

### (4) Setup the github repo as an alternative remote

First, add a new remote named "github":
```
git remote add github https://github.com/dtak/demo_tex_project_with_overleaf.git
```

Next, pull content from github
```
git pull github master --allow-unrelated-histories
```
Note: the special flag here allows the two projects which started with unrelated content (a main.tex file from Overleaf, a README/License from Github) to become a single repo.


**That's all folks!**

