---
tags: ✍️
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
Git is a tpe of source code management (SCM). SCM tracks changes in files over time so that older versions of those can be retrieved at a later time. Specifically these files are source-code files for specific software, even though it is possible to do this with any type of file.

Many people in software development used to version control their project's source code by archiving the directory of the project and adding a timestamp to the name of the newly created archive. This zipped archive was perhaps then even copied to an external harddisk or server.
In academia, when people write a paper or do a project, they still do it like this. They write the paper in Word, and during editting they will make versions of the paper. When the (almost) finished paper is send to a colleague to be checked, a date is aded to the name. And when a revised version of the paper is send back, the name of the persion that did check the paper is added to the name of the paper. Well, at least in the lab I am currently working.
This system is increadibly easy to invent and use, but also prone to errors. Not to mention that versions will be lost because they are not interesting anymore, due to the many places where you might store the documents or due to other causes. Additionally, it is increadibly hard to collaborate in this manner. Because of this, software developers invented version control systems (VCS) while working on projects together. One of these VCSs, and certainly the most popular, is Git.

Git is a SCM (and thus VCS), that has the advantage to not only be local, but also distributed. The system that I described in the previous paragraph, a VCS without any secondary computers or servers, is a type of local VCS. In a distributed VCS, every copy of the tracked project contains all the past and present information of the project. This has the avantage that if one copy of the project gets lost, for example due to a crash of a server, then another copy with the same project can be used to recreate the centralized copy of the project (on the server) without losing information.

In software development and bioinformatics, it is expected to work with version control. On top of that, it is highly encouraged to work with VCS in academics as well.

## Installation
To first start of with git as a VCS, we must install it in our computer. Depending on the Operating System (OS), this is done differently.
For **[[windows|Windows]]**, a package must be downloaded from [git-scm.com](https://git-scm.com/download/win) and thereafter executed. It must be installed with Git Bash and the Git executable must be added to the PATH environmental variable. Git Bash is needed for some configuration.
For **[[mac|Mac]]** and **[[linux|Linux]]**, simple commands will do the trick: for Mac, execute `brew install git` (using [[homebrew|Homebrew]]), and for Linux (Debian/Ubuntu) execute `apt-get install git`.
Git can now be accessed using the command line interface (CLI). For **Windows** that is usually `cmd`, [[powershell|Powershell]] or Git Bash, while for **Mac** and **Linux** it is the terminal or iTerm2.

## Basic configuration
After the installation of Git, some configuration needs to be done. For all Operating Systems both the user name and the email address should be set. Execute using the CLI the following commands: `git config --global user.name "Jos van Nijnatten"` and `git config --global user.email "9002122+vanNijnatten@users.noreply.github.com"`. Of course replace "Jos van Nijnatten" and "9002122+vanNijnatten@users.noreply.github.com" with your name and email address respectively.

Additionally, there is a difference in Windows and Unix-style line ending. Because of this, `safeclrf` should be set to `true` using `git config --global core.safeclrf true`. One more settings is important when developing cross-platform. For **Windows** you will want to checkout Windows-style, and commit Unix-style. Execute `git config --global core.autoclrf true`. For **Mac** and **Linux** you will want to checkout Unix-style, and commit Unix-style. Execute `git config --global core.autoclrf input`.

If you work with remote branches over SSH, you also need to create an SSH key and upload the public key to the server containing the remote branch. For this, see the page on [[ssh|SSH]]. For [[github|GitHub]] this public key can be uploaded on [this page](https://github.com/settings/keys).

## Additional configuration
Apart from the basic, but important, settings that should be set for git to work properly, some more can be set

### GPG
#### Windows
See [medium.com](https://neurotechnics.com/blog/configure-gpg-to-sign-git-commits-in-windows/).
Install [GnuPG]([https://gpg4win.org/download.html](https://gpg4win.org/download.html)).

#### Mac/Linux
```BASH
# See https://github.com/settings/emails
EMAIL="9002122+vanNijnatten@users.noreply.github.com"
# See output of "gpg --list-secret-keys --keyid-format LONG"
SECRET_KEYID="2F01902897288144"


brew install gnupg
brew install pinentry-mac


echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf
killall gpg-agent


gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG "$EMAIL"
gpg --armor --output gpg_github_pub.asc --export "$EMAIL"
cat gpg_github_pub.asc
# Perhaps you also would like to add the public key to GitHub at 
# https://github.com/settings/keys


# If you do something wrong while creating the GPG key, delete it:
gpg --list-secret-keys --keyid-format LONG "$EMAIL"
# sec   rsa4096/$SECRET_KEYID 2021-09-24 [SC] [expires: 2031-09-22]
#       RANDOMNUMBERSANDLETTERSRANDOMNUMBERSANDL
# uid                 [ultimate] Jos van Nijnatten (This is for GitHub only.) <$EMAIL>
# ssb   rsa4096/SOMEOTHERIDENTIF 2021-09-24 [E] [expires: 2031-09-22]
gpg --delete-secret-key "$SECRET_KEYID"


git config --list
git config --global user.email "$EMAIL"
git config --global user.signingKey "$SECRET_KEYID"
git config --global commit.gpgsign true
git config --global gpg.program gpg


# To test the signature: Open a Sandbox repository
vim "README.MD"
git commit -m "Small change to test GPG"
git push
git show head --show-signature
git log --show-signature -1
```

## Understanding Git

## Usage
git init
git clone
git add .
git commit -m "commit message"
git commit --amend -m "rewrite commit message" <- without any staged file(s)
git commit --amend --no-edit <- with staged file(s)
git clean -n
git clean -f
git clean -d
git push
git pull
git status
git log
git blame (file)
git switch (branch) -> switches to branch
git checkout (commit) -> from branch sets branch to commit
git checkout (commit) (file) -> restore version of file
git checkout -b (new-branch) -> creates branch and checks out this new branch
git restore . -> discard all local changes
git restore --staged (file_name)
git restore --source (commit) (file_name) -> restores file from commit
git restore (file_name) -p -> walk through changes
git reset (--hard -> from a branch to a commit will move the branch)
git branch (new-branch-name) (origin-branch-name)
git branch -D (branch-name) -> will delete the label
git merge (branch-B) -> from branch-A merge branch-B into branch-A
git remote add origin (url) 
git remote set-url origin (url)
git stash (https://medium.com/free-code-camp/useful-tricks-you-might-not-know-about-git-stash-e8a9490f0a1a)
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
hooks (?)
Detached HEADS

## Useful commands


```git
# Cheatsheet
# https://dev.to/rubiin/one-list-to-rule-them-all-1kh5#computer-science
# https://github.com/tiimgreen/github-cheat-sheet#readme
# https://gitimmersion.com/lab_01.html
# https://ohshitgit.com

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
