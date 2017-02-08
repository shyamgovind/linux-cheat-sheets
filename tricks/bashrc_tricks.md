# Some useful tricks to be included in your .bashrc file

## .bash_profile vs .bashrc ( [info source](http://www.joshstaiger.org/archives/2005/07/bash_profile_vs.html) )

The _.bash_profile_ is run every time you login, while _.bashrc_ is executed everytime you open a bash shell. So, if you are already logged in a linux system GUI and open a terminal - _.bash_profile_ WILL NOT be executed but _.bashrc_ would be executed everytime a new shell is opened.

### Why two files ?
If you’d like to print some lengthy diagnostic information about your machine each time you login (load average, memory usage, current users, etc) - _.bash_profile_ is a good place to put it.
