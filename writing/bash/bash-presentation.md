---
tags:
  - _durability/fleeting
  - _type/presentation
aliases: 
cssclasses:
  - presentation
publish: false
---
# A presentation on BASH

- What is shell scripting
- Why shell scripting
- REPL
	- `fc` (feed code)
	- `!!`, replace something in last command `^code1^code2` or `!!:gs/string1/string2` or `fc -s code1=code2`, use last arguments `!$` or `$_`, use first argument `!^`, use abituary argument/command `!!:1` (first arguments), `!:1-3` (arguments 1-3) `!!:0` (command) , all arguments from last command `$*`, most recent command with pattern `!pattern`, etc etc
- Script / shebang
- variables
    - set/unset/export
- reading input, printing output
    - stdin, stdout, stderr, 3>1&, 2>1&, /dev/fd, redirection
    - piping |, redirecting >, >>, <
- flow control
    - if, then, else
        - testing variables w/ [] and [[]]
        - and or not
    - for and while loops
        - breaks
- integers and arrays
    - arithmetics, (( )), https://opensource.com/article/18/5/you-dont-know-bash-intro-bash-arrays
- advanced
    - shifts, getopts https://stackoverflow.com/questions/16483119/an-example-of-how-to-use-getopts-in-bash
    - set options (set -o/+o)
- functions
    - arguments $#, $*, $1, $2
    - default values
    - optionals
- strings
    - search and replace ${var/pattern/replacement/}
- subcommands
    - $(), <()
- Jobs
    - &, wait, jobs, ctrl-z, etc
- Build in functionality
    - https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_01_03.html
    - run scripts, debugging (bash -x, declare -t VAR=text, trap "echo $VAR" DEBUG)
    - cd,popd,pushd
    - jobs, ctrl-z, bg, fg
- not buildin functionality
    - ps,top,htop
    - find
    - mkdir,touch,rm,cp,mv
- https://www.onlc.com/outline.asp?ccode=xlbash