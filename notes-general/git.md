---
tags: _durability/fleeting
aliases: 
  - git
  - scm
  - source code management
  - vcs
  - version control system
cssclass: idea
publish: true
---
# Git
See also [[github|GitHub]].

## What is Git?
Git is a type of source code management (SCM). SCM tracks changes in files over time so that older versions of those can be retrieved at a later time. Specifically these files are source-code files for specific software, even though it is possible to do this with any type of file.

Many people in software development used to version control their project's source code by archiving the directory of the project and adding a timestamp to the name of the newly created archive. This zipped archive was perhaps then even copied to an external harddisk or server.
In academia, when people write a paper or do a project, they still do it like this. They write the paper in Word, and during editing they will make versions of the paper. When the (almost) finished paper is send to a colleague to be checked, a date is added to the name. And when a revised version of the paper is send back, the name of the person that did check the paper is added to the name of the paper. Well, at least in the lab I am currently working.
This system is incredibly easy to invent and use, but also prone to errors. Not to mention that versions will be lost because they are not interesting anymore, due to the many places where you might store the documents or due to other causes. Additionally, it is incredibly hard to collaborate in this manner. Because of this, software developers invented version control systems (VCS) while working on projects together. One of these VCSs, and certainly the most popular, is Git.

Git is a SCM (and thus VCS), that has the advantage to not only be local, but also distributed. The system that I described in the previous paragraph, a VCS without any secondary computers or servers, is a type of local VCS. In a distributed VCS, every copy of the tracked project contains all the past and present information of the project. This has the advantage that if one copy of the project gets lost, for example due to a crash of a server, then another copy with the same project can be used to recreate the centralized copy of the project (on the server) without losing information.

In software development and bioinformatics, it is expected to work with version control. On top of that, it is highly encouraged to work with VCS in academics as well.

## Installation
To first start of with Git as a VCS, we must install it in our computer. Depending on the Operating System (OS), this is done differently.
For **[[windows|Windows]]**, a package must be downloaded from [git-scm.com](https://git-scm.com/download/win) and thereafter executed. It must be installed with Git Bash and the Git executable must be added to the PATH environmental variable. Git Bash is needed for some configuration.
For **[[mac|Mac]]** and **[[linux|Linux]]**, simple commands will do the trick: for Mac, execute `brew install git` (using [[homebrew|Homebrew]]), and for Linux (Debian/Ubuntu) execute `apt-get install git`.
Git can now be accessed using the command line interface (CLI). For **Windows** that is usually `cmd`, [[powershell|Powershell]] or Git Bash, while for **Mac** and **Linux** it is the terminal or iTerm2.

## Basic configuration
After the installation of Git, some configuration needs to be done. For all Operating Systems both the user name and the email address should be set. Execute using the CLI the following commands: `git config --global user.name "Jos van Nijnatten"` and `git config --global user.email "9002122+vanNijnatten@users.noreply.github.com"`. Of course replace "Jos van Nijnatten" and "9002122+vanNijnatten@users.noreply.github.com" with your name and email address respectively. If you use GitHub as a remote branch, the type of email shown above can be obtaind from the [email page](https://github.com/settings/emails). Additionally, it is possible to cach your long credentials using `git config --global credential.helper cache`, though [[Mac]] does it automatically.

Additionally, there is a difference in Windows and Unix-style line ending. Because of this, `safeclrf` should be set to `true` using `git config --global core.safeclrf true`. One more settings is important when developing cross-platform. For **Windows** you will want to checkout Windows-style, and commit Unix-style. Execute `git config --global core.autoclrf true`. For **Mac** and **Linux** you will want to checkout Unix-style, and commit Unix-style. Execute `git config --global core.autoclrf input`.

If you work with remote branches over SSH, you also need to create an SSH key and upload the public key to the server containing the remote branch. For this, see the page on [[ssh|SSH]] and use to configure Git. For [[github|GitHub]] this public key can be uploaded on [this page](https://github.com/settings/keys).

## Additional configuration
Apart from the basic, but important, settings that should be set for git to work properly, some more can be set

### Commit signing
Commits to a Git repository (a directory tracked by Git) can be signed using [[pgp|GPG]], which verifies the origin of the commit. For [[github|GitHub]], a GPG key must be an RSA-4096 key. After a key has been created, the id of the signing key can be obtained using `gpg --list-secret-keys --keyid-format LONG "9002122+vanNijnatten@users.noreply.github.com"`. The id is located on the first line, just after "rna4096/". Note that for **Windows**, the following commands should be executed in Git Bash.
Once the signing keys is obtained, three Git options must be set: `git config --global user.signingKey 2F01902897288144`, where "2F01902897288144" is the id of the signing key. Additionally, `git config --global commit.gpgsign true` and `git config --global gpg.program gpg` must be set. (For **Windows**, the path to the gpg program must be absolute: `git config --global gpg.program "/c/Program Files (x86)/GnuPG/bin/gpg.exe"`). This makes sure commits are signed by a GPG key and that unsigned commits are not allowed.

For **Mac**, pinentry could also be installed using HomeBrew (`brew install pinentry-mac`), and the line "pinentry-program /usr/local/bin/pinentry-mac" should be appended to file "~/.gnupg/gpg-agent.conf". All "gpg-agent" instances should be killed.

To verify if the signing of commits, make a commit. If the Git option `commit.gpgsign` is set to `true`, the commit should be signed to be accepted. Additionally, the signatues of commits can be shown using `git show head --show-signature` and `git log --show-signature -1`.

## Understanding Git
To understand Git, it's best to work with Git. This section does not include any explanation on how to work with [[github|GitHub]]. 

### Initializing and Cloning repositories
After configuring Git, a repository must be made or **initialized**. This can be done with `git init` in an empty directory. If the repository is already made somewhere else, a copy or **clone** can be made over [[https|HTTPS]] using `git clone https://website.com/username/repo.git` or over [[ssh|SSH]] using `git clone git@website.com:username/repo.git`. This will create a new directory named after 'repo' in 'repo.git'. The Git repository will open the 'master' or 'main' [[git#branches|branch]].

### Adding, removing and excluding files
Files created in or copied to the repository are not automatically part of the repository and removed files are not automatically removed from the repository. These changes first need to be added to the the repository, which is called 'staging'. To see which files are new, changed or deleted, `git status` can be run. If any changes to the repository are found, these can be added using `git add path/to/file.txt`. A shortcut to add all changes that are listed is `git add .`.
A 'staged' file or change is marked to be part of the repository, but not actually part of the repository. For this to happen, we need to commit the changes. This is done by running `git commit -m "Commit message"`, in which the 'Commit message' should be describing the changes that are made in all changes. For example "Feature X was implemented (Task nr 007)", or "Differential analysis of COPD vs Non COPD".
If the previous commit did not include all intended changes, than these should be staged. Next, the previous commit can be changed using `git commit --amend --no-edit`. The '--no-edit' option preserves the previous commit message, though a new message can also be set using the '-m' option.
These edits are done on the current [[git#Branch|branch]].

### Seeing changes
diff, blame

### Creating, changing and deleting branches

### Branching strategy

### Remote repositories, pushing, pulling, merging

### Restoring files

### The stash

## Usage
```Bash
git init
git clone git@website.com:username/repo.git
git add .
git rm file.txt
git mv filename new-path/new-filename
git commit -m "commit message"
git commit --amend -m "rewrite commit message" <- without any staged file(s)
git commit --amend --no-edit <- with staged file(s)
git revert HEAD -> will revert the last commit
git clean -n
git clean -f
git clean -d
git push
git push origin (branch-name)
git push -u origin (branch-name)
git push origin --delete (origin) (branch-name)
git pull --verbose
git status
git log
git show ((short)-commit-id)
git diff
git diff --staged
git diff (filename)
git blame (file)
git switch (branch) -> switches to branch
git checkout (commit) -> from branch sets branch to commit
git checkout (commit) (file) -> restore version of file
git checkout -b (new-branch) -> creates branch and checks out this new branch
git restore . -> discard all local changes
git restore --staged (file_name)
git restore --source (commit) (file_name) -> restores file from commit
git restore (file_name) -p -> walk through changes
git reset HEAD -> all files will be considered unstaged
git reset HEAD filename -> file will be considered an unstaged file
git reset (--hard -> from a branch to a commit will move the branch)
git branch -a -> list all branches
git branch (new-branch-name) (origin-branch-name)
git branch -D (branch-name) -> will delete the label (without warning)
git merge (branch-B) --no-ff -> from branch-A, merge branch-B into branch-A
git merge --abort
git remote -v -> list remote URLs
git remote show origin
git remote add origin (url) 
git remote set-url origin (url)
git stash save -u "message" -> include-untracked
git stash list
git stash apply stash@{1}
git stash pop stash@{1}
git stash show stash@{1}
git stash branch new-branch-name stash@{1}
git stash clear
git stash drop stash@{1}
git tag -a "tag-name" -m "annotated message" (commit_hash)
git push origin v1.2
git push origin --tags
git push origin --delete <tag_name>
git reflog
# hooks / scripts (?)
# Detached HEADS
# .gitignore | .gitallow(?) | .gitattributes | .gitconfig
```

## Useful commands
```Bash
# Cheatsheet
# https://dev.to/rubiin/one-list-to-rule-them-all-1kh5#computer-science
# https://github.com/tiimgreen/github-cheat-sheet#readme
# https://gitimmersion.com/lab_01.html
# https://ohshitgit.com
# https://levelup.gitconnected.com/top-30-git-commands-you-should-know-to-master-git-cli-f04e041779bc

# Aliases
lg = lg1
lg1 = lg1-specific --all
lg2 = lg2-specific --all
lg3 = lg3-specific --all
lg4 = lg4-specific --all
lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'
lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(auto)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim whi    te)- %an%C(reset)'
lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(auto)%d%C(reset)%n''              %C(white)%s%C(reset)%n''          %C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)'
lg4-specific = log --graph --full-history --all --color --pretty=tformat:"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%s%x20%x1b[33m(%an)%x1b[0m"
```
