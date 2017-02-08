
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
