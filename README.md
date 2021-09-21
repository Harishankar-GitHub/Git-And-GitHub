# Git and GitHub Masterclass

- Git and GitHub are not exactly same.
- Both can be used independently.
- Both have their own unique features.
- Some of them are shared.

+ Both are related.
+ GitHub relies on Git most of the times.

#### Version Control | Revision Control | Source Control

- To see what is changed
- Where the changes are made
- Who changed etc.

#### Why is Version Control Important ?

>- Instead of creating new versions of a single document (something like final_version, final_version_1, final_version_2 etc., we can use some tool like Google Docs.
>- But we can't compare with the previous versions, some mistakes, time consumed to prepare it, keep track of changes etc.

- Here comes **Version Control System** to manage the Code Base!
- It allows us to **compare with the previous versions** of the code.
- We can **merge** the changes **often**.
- It allows to merge the **work of other team mates**.

#### Summary

- Keep track of changes.
- Ability to go back to the previous working version.
- Can add someone else's work into our own.

#### Where can we use Git Version Control ?

- Code files
- Text files
- Documents like PDF etc.

#### How do development teams use Version Control ?

- To maintain the code version.
- To collaborate with other team members.

+ Version Control always keeps track of the changes.
+ We can always go back to any version if something goes wrong.

> This is why Version Control is very important.

---

#### Downloading Git

> Click to [download and install](https://git-scm.com/downloads) or [install via Chocolatey](https://community.chocolatey.org/packages/git) to download.

#### Few commands

> Open Git Bash
- **Check version**: `git --version`
- **Update Git Bash**: `git update-git-for-windows`
- **Open current directory**: `start .`
- **List directories**: `dir`
- **List hidden files/folders/directories**: `dir -a`

#### Setting up Git Workspace on Windows

- Download the files from resource section and extract them.
- Copy terminal-config and bash_profile to the Home directory
- **Rename the files**: `mv terminal-config .terminal-config` and `mv bash_profile .bash_profile`
- Close Git Bash and open again.
+ Now, the terminal will start with Username instead of Username@DeviceName
+ We can go to Home Directory and edit .bash_profile to change colors etc.
+ We can delete the .bash_profile if this set up is not needed.

---

#### Executing First Commit

- From Git Bash cd to any folder.
- **Create a new folder**: `mkdir Git-And-GitHub` (Folder can be directly created from File Explorer as well)
- **To open the folder in an editor** (In this case Visual Studio Code): `code Git-And-GitHub/`
- Create a new file - index.html and add some code.
- Now, we have a file inside the folder Git-And-GitHub.
- We have to **initialize a Git Repository** inside this folder `git init`.
- **To view the files**: `ls` or `ls -a`
- **To add the modified/added files** to Git: `git add fileName`
- **Commit**: `git commit -m "Commit message"`

#### Process of Committing a Change

> When we add/modify a file in the **Project Directory**, and execute `git add fileName`, the files are **Staged**. It means, the files are ready to be committed.
> When we **commit** `git commit -m "Commit message"`, the files are committed to the Local Git Repository.
> Once the files are committed, that version is **always available**.

#### Reviewing File Changes

> We add some more code to the file (index.html).
- **Check the difference**: `git diff fileName`
- In this case, `git diff index.html`
- Now, `git add index.html` and `git commit -m "Message"`.

#### Git Configurations

- **To see the configurations**: `git config --list`
- **To set username**: `git config --global user.name "Name"`
- **To set email**: `git config --global user.email "Email"`
- **To set default editor**: `git config --global core.editor "code --wait"`
	+ `--wait`: when we don't give a commit message (`git ommit`) the default editor is opened. We have to enter commit message and close the file. After that, the commit will be done.

---

Getting Started with [GitHub](https://github.com/)
-
- GitHub **uses Git** (Copies or Clones the repository).
- Just one more computer that **has a clone of repository online**.
- Adds **user management**.
- **Tool Integration**.

> New account can be created from [GitHub](https://github.com/).

#### Creating a Repository from GitHub

- Give a name to the Repository.
- Give some description.
- Do not select README.md or .gitignore.
- Create it.

#### Pushing the Local Repo to GitHub

- cd to the local repository folder.
- Command to **add local repo to GitHub repo**:`git remote add origin https://github.com/Harishankar-GitHub/Git-And-GitHub.git`
	- **`remote add`** is to push local repo to GitHub.
	- **`origin`** is just a name to refer remote repository.
	- **`GitHub-URL`** is the location on GitHub where we push the local repository.
- **Command to push**: `git push origin master`.

#### Editing and Committing from GitHub

- Open the file (index.html) from GitHub and add/modify few lines.
- Commit it.

#### Pulling from the Remote

- Command to pull: `git pull origin master`
- Command to make the branch that is in local to track the branch that is in GitHub: `git branch --set-upstream-to=origin/master master`
	- **origin/master** is the branch in GitHub.
	- **master** is the local branch.

+ Once we set the tracking information, we **need not use `git pull origin master`**.
+ We can **just run `git pull`** and the changes are updated in the local repository.
+ The process of setting the tracking information is required only when we create a new repo in local and push it to GitHub and work on it.
+ If we clone an existing repository from GitHub, we can directly use `git pull` command.

#### Checking the changes with Git Status

- **Command to check status**: `git fetch` and `git status`.
	- `git fetch` will check if there's any changes in the GitHub repo.
	- Then, `git status` will show the changes that is in local repo as well as GitHub repo.
	- After this, we can do a `git pull` to merge the changes to the local repository.

#### Fork and Clone

- We can fork a **public** repository (in this case I forked a repository called [GitGitHubMasterlcass](https://github.com/Harishankar-GitHub/GitGitHubMasterlcass)) from any other GitHub Account.
- A **copy** of that repository will be available in our GitHub account.
- We **can make changes** to that repository and the changes will be **reflected only in our GitHub account**.

#### Cloning a Repository

- Open GitHub
- Open any repository (public), and click on **Fork**.
- Now, that repository will be available in our GitHub account.

##### Steps to clone:

- In the repository page on GitHub, click on **Clone** and **copy the HTTPS URL**.
- Open **Git Bash** and navigate to a folder to clone the repo.
- **Command to clone:** `git clone <HTTPS_URL>` 
- After cloning, cd inside the repository.
- Run `code .` in Git Bash to **open** the code in the **default editor**.

#### Exploring Git Logs

- Command to view Git logs: `git log`
- To come out of Git log: Press `q`

##### Checking the difference between 2 commits

- `git diff commitId-1 commitId-2`
- `git diff HEAD~1 HEAD ~4`
	- ***HEAD*** is the latest commit
	- `HEAD~1` & `HEAD~4` are the 1st and 4th commit before ***HEAD***

#### Getting Commit and File Details with Git

- `git show commitId`
- `git show HEAD` - ***HEAD*** is the latest commit
- `git show HEAD~3` - `HEAD~3` is to view the 3rd commit before latest commit.

#### To view the changes of a particular file

`git annotate fileName`

#### Exploring Commit and File Details from GitHub

- We can find lot of options in GitHub.
- Viewing the commit history, commit id (SHA), files etc.
- We can also comment, blame, view other branches etc.

#### Making changes and committing

- Instead of doing `git add .` and `git commit -m commitMessage`
- We can directly use `git commit -a -m commitMessage`

#### Undoing Changes and Reverting Commits

- If a ***change*** that is ***saved but not yet staged*** need to be reverted, below command can be used.
	- `git checkout -- fileNameToBeReverted`
- If a change is already staged but need to be reverted, below command can be used,
	- `git reset HEAD fileNameToBeReverted` and then `git checkout -- fileNameToBeReverted`
- If a change is committed/pushed but need to be reverted, below command can be used.
	- `git checkout commitId fileNameToBeReverted`

#### Dealing with multiple files
* `git reset HEAD .` - To un stage multiple files.
* `git checkout HEAD .` - To revert the changes that aren't changed.