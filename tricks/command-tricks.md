
## Some useful command tricks

#### Rename/move a file with really long path name

```
cp /home/foo/realllylongname.yaml{,.bkp}
  # This is same as doing
  # cp /home/foo/realllylongname.yaml /home/foo/realllylongname.yaml.bkp

# You could do it the other way as well
mv /home/foo/realllylongname.yaml{.bkp,}
  # Same as 
  # mv /home/foo/realllylongname.yaml.bkp /home/foo/realllylongname.yaml
  
```
#### Copy while preserving the date
```
cp -p 
```

#### Repeat the previous command

```
!!
# Repeats your last command. Most useful in the form:

sudo !!
```

#### !$ - last word of the previous command.

```
mkdir test; cd !$
  # Same as
  # mkdir test; cd test
```


#### rename command

```
$ ls
this_has_text_to_find_1.txt
this_has_text_to_find_2.txt
this_has_text_to_find_3.txt
this_has_text_to_find_4.txt

$ rename -v text_to_find been_renamed *.txt
$ ls
this_has_been_renamed_1.txt
this_has_been_renamed_2.txt
this_has_been_renamed_3.txt
this_has_been_renamed_4.txt

```

#### List only the directories

```
ls -d */
```

#### escape aliases set

```
$ alias ls='ls -lAtr'
$ # To escape the alias for ls:
$ \ls # This will run the plain ls command.
```

#### Mark important commands for later use

```
$ imp_command_here   #useful

to search, just grep "useful" in your history

```




