# demo_tex_project_with_overleaf

Shows how to make a git repository for LaTeX document that has TWO remote locations:
* one on Github (to easily share .tex source files with other folks)
* one on Overleaf (to easily display and edit doc in browser)

## Workflow (do this every time you edit your document)

After edits on Overleaf, which you want to syncronize to the github remote repo:
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

* (3) Create a new repository on Github

* * Goto github.com/dtak/
* * Click the New button (green)
* * Setup the description etc. as you wish
* * Copy the "Clone with" link

Example link: `https://github.com/dtak/demo_tex_project_with_overleaf.git`

* (4) Setup the github repo as an alternative remote

First, add a new remote named "github":
```
git remote add github https://github.com/dtak/demo_tex_project_with_overleaf.git
```

Next, pull content from github
```
git pull github master --allow-unrelated-histories
```
Note: the special flag here allows the two projects which started with unrelated content (a main.tex file from Overleaf, a README/License from Github) to become a single repo.



```

**That's all folks!**

