# Some useful tricks to be included in your .bashrc file

### .bash_profile vs .bashrc

The _.bash_profile_ is run every time you login, while _.bashrc_ is executed everytime you open a bash shell. So, if you are already logged in a linux system GUI and open a terminal - _.bash_profile_ WILL NOT be executed but _.bashrc_ would be executed everytime a new shell is opened.

#### Why two files ?
If you’d like to print some lengthy diagnostic information about your machine each time you login (load average, memory usage, current users, etc) - _.bash_profile_ is a good place to put it.


#### Useful tricks

*Note : Do read through the file before using, to know what you are doing.*

```
## Aliases

alias grep='grep --color=auto'
alias mkdir='mkdir -p'

## Functions

# 'cdn 2' would do 'cd ..' twice
function cdn(){ for i in `seq $1`; do cd ..; done;}

## Misc commands

# Sync the command history across multiple bash shells
shopt -s histappend    # shopt is a bash command to set shell options
PROMPT_COMMAND="history -n; history -a"  # PROMPT_COMMAND is a bash env variable. Gets executed before every prom
pt.
unset HISTFILESIZE
HISTSIZE=2000    # Increase the history size from default 500 to 2000.

```




### Good links to read more 

1. bash_profile vs bashrc ( http://www.joshstaiger.org/archives/2005/07/bash_profile_vs.html )


