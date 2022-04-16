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
See also [GitHub](https://github.com/git).

## What is Git?
Git is a tpe of source code management (SCM). SCM tracks changes in files over time so that older versions of those can be retrieved at a later time. Specifically these files are source-code files for specific software, even though it is possible to do this with any type of file.

Many people in software development used to version control their project's source code by archiving the directory of the project and adding a timestamp to the name of the newly created archive. This zipped archive was perhaps then even copied to an external harddisk or server.
In academia, when people write a paper or do a project, they still do it like this. They write the paper in Word, and during editting they will make versions of the paper. When the (almost) finished paper is send to a colleague to be checked, a date is aded to the name. And when a revised version of the paper is send back, the name of the persion that did check the paper is added to the name of the paper. Well, at least in the lab I am currently working.
This system is increadibly easy to invent and use, but also prone to errors. Not to mention that versions will be lost because they are not interesting anymore, due to the many places where you might store the documents or due to other causes. Additionally, it is increadibly hard to collaborate in this manner. Because of this, software developers invented version control systems (VCS) while working on projects together. One of these VCSs, and certainly the most popular, is Git.

Git is a SCM (and thus VCS), that has the advantage to not only be local, but also distributed. The system that I described in the previous paragraph, without any secondary computers or servers, is a type of local VCS. In a distributed VCS, every copy of the tracked project contains all the past and present information of the project. This has the avantage that if one copy of the project gets lost, for example due to a crash of a server, then another computer with the same project can be used to recreate the centralized copy of the project (on the server).

## Installation

## Basic configuration
ssh
gpg-signing

## Usage
(remote) branches
log


## Useful commands


```git
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
