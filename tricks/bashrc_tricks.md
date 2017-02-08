# Some useful tricks to be included in your .bashrc file

### .bash_profile vs .bashrc

The _.bash_profile_ is run every time you login, while _.bashrc_ is executed everytime you open a bash shell. So, if you are already logged in a linux system GUI and open a terminal - _.bash_profile_ WILL NOT be executed but _.bashrc_ would be executed everytime a new shell is opened.

#### Why two files ?
If you’d like to print some lengthy diagnostic information about your machine each time you login (load average, memory usage, current users, etc) - _.bash_profile_ is a good place to put it.


#### Useful tricks

*Note : Do read through the file before using.*

```
## Aliases

alias vi='vim'
alias grep='grep --color=auto'
alias mkdir='mkdir -p'
alias ll='ls -lAhtr'
alias less='less -MNG'

## Functions

# 'up 2' would do 'cd ..' twice
function up(){ for i in `seq $1`; do cd ..; done;}

# Colored output for man command
function man() {
        env LESS_TERMCAP_mb=$(printf "\e[1;31m") \
        LESS_TERMCAP_md=$(printf "\e[1;31m") \
        LESS_TERMCAP_me=$(printf "\e[0m") \
        LESS_TERMCAP_se=$(printf "\e[0m") \
        LESS_TERMCAP_so=$(printf "\e[1;44;33m") \
        LESS_TERMCAP_ue=$(printf "\e[0m") \
        LESS_TERMCAP_us=$(printf "\e[1;32m") \
        man "$@"
    }

# A single extract command to extract different kinds of files.
function extract () {
      if [ -f $1 ] ; then
          case $1 in
              *.tar.bz2)   tar xvjf $1    ;;
              *.tar.gz)    tar xvzf $1    ;;
              *.bz2)       bunzip2 $1     ;;
              *.rar)       rar x $1       ;;
              *.gz)        gunzip $1      ;;
              *.tar)       tar xvf $1     ;;
              *.tbz2)      tar xvjf $1    ;;
              *.tgz)       tar xvzf $1    ;;
              *.zip)       unzip $1       ;;
              *.Z)         uncompress $1  ;;
              *.7z)        7z x $1        ;;
              *)           echo "don't know how to extract '$1'..." ;;
          esac
      else
          echo "'$1' is not a valid file!"
      fi
    }

# do a "ls" after every "cd" command
function cd ()
    {
        builtin cd $1
        ls
    }


## Misc commands

# Sync the command history across multiple bash shells
shopt -s histappend    # shopt is a bash command to set shell options
PROMPT_COMMAND="history -n; history -a"  # PROMPT_COMMAND is a bash env variable. Gets executed before every prom
pt.
unset HISTFILESIZE
HISTSIZE=200000    # Increase the history size from default 500 to 200000.


```




### Good links to read more 

1. bash_profile vs bashrc ( http://www.joshstaiger.org/archives/2005/07/bash_profile_vs.html )


