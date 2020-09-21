# Bash

**Bash** (AKA **B**ourne **A**gain **Sh**ell) is a **type of interpreter** that processes shell commands.

the **terminal** is the **interface to the shell interpreter**.

Normally, a Bash script file has `.sh` extension to make it clear that it is a shell script file



### shebang

**shebang** is the character sequence consisting of the characters [number sign](https://en.wikipedia.org/wiki/Number_sign) and [exclamation mark](https://en.wikipedia.org/wiki/Exclamation_mark) (#!) at the beginning of a script. This line will make the text file executable

we can directly execute it like a binary but we need to put a [**shebang**](https://en.wikipedia.org/wiki/Shebang_(Unix)) or **hashbang** line at the top of the file **to declare the** **interpreter**.

```
#! /usr/bin/env **bash**
\# *comment: use command ./make-files.sh*
ls -alh ./test
```



The path is absolute, but from computer to computer the location can change

Often, the program [/usr/bin/env](https://en.wikipedia.org/wiki/Env) can be used to circumvent this limitation by introducing a level of [indirection](https://en.wikipedia.org/wiki/Indirection). `#!` is followed by /usr/bin/env, followed by the desired command without full path



## Basic commands

- **[cat](https://www.geeksforgeeks.org/cat-command-linux-examples/)** : It is generally used to concatenate the files. It gives the output on the standard output.
- **[more](https://www.geeksforgeeks.org/more-command-in-linux-with-examples/)** : It is a filter for paging through text one screenful at a time.
- **[less](https://www.geeksforgeeks.org/less-command-linux-examples/)** : It is used to viewing the files instead of opening the file.Similar to *more* command but it allows backward as well as forward movement.
- **[head](https://www.geeksforgeeks.org/head-command-linux-examples/)** : Used to print the first N lines of a file. It accepts N as input and the default value of N is 10.
- **[tail](https://www.geeksforgeeks.org/tail-command-linux-examples/)** : Used to print the last N-1 lines of a file. It accepts N as input and the default value of N is 10.



**File and Directory Manipulation Commands**: 

- **[mkdir](https://www.geeksforgeeks.org/mkdir-command-in-linux-with-examples/)** : Used to create a directory if not already exist. It accepts directory name as input parameter.
- **[cp](https://www.geeksforgeeks.org/cp-command-linux-examples/)** : This command will copy the files and directories from source path to destination path. It can copy a file/directory with new name to the destination path. It accepts source file/directory and destination file/directory.  `cp file ../new path/namefile`
- **[mv](https://www.geeksforgeeks.org/mv-command-linux-examples/)** : Used to move the files or directories. This command’s working is almost similar to *cp* command but it deletes copy of file or directory from source path.
- **[rm](https://www.geeksforgeeks.org/rm-command-linux-examples/)** : Used to remove files or directories.
- **[touch](https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/)** : Used to create or update a file.
- **[grep](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)** : This command is used to search for the specified text in a file. (you can use Regex)
- **[sort](https://www.geeksforgeeks.org/sort-command-linuxunix-examples/)** : This commands is used to sort the contents of files
- **[wc](https://www.geeksforgeeks.org/wc-command-linux-examples/)** : Used to count the number of characters, words in a file.
- **[cut](https://www.geeksforgeeks.org/cut-command-linux-examples/)** : Used to cut a specified part of a file.



**Basic Navigation Commands:** 

- **[ls](https://www.geeksforgeeks.org/practical-applications-ls-command-linux/)** : To get the list of all the files or folders.
- **[cd](https://www.geeksforgeeks.org/cd-command-in-linux-with-examples/)** : Used to change the directory.
  -  `cd /` to change the directory to the root
  - `cd ~`change directory to the home
- **[du](https://www.geeksforgeeks.org/du-command-linux-examples/)** : Show disk usage.
- **[pwd](https://www.geeksforgeeks.org/pwd-command-in-linux-with-examples/)** : Show the present working directory.
- **[man](https://www.geeksforgeeks.org/man-command-in-linux-with-examples/)** : Used to show the manual of any command present in Linux.
- **[rmdir](https://www.geeksforgeeks.org/rmdir-command-in-linux-with-examples/)** : It is used to delete a directory if it is empty.
- **[ln](https://www.geeksforgeeks.org/ln-command-in-linux-with-examples/) file1 file2** : Creates physical link.
- **[ln](https://www.geeksforgeeks.org/ln-command-in-linux-with-examples/) -s file1 file2** : Creates symbolic link.



**File Permissions Commands:** The *chmod* and *chown* commands are used to control access to files in UNIX and Linux systems.

- **[chown](https://www.geeksforgeeks.org/chown-command-in-linux-with-examples/)** : Used to change the owner of file.
- **[chgrp](https://www.geeksforgeeks.org/chgrp-command-in-linux-with-examples/)** : Used to change the group owner of file.
- **[chmod](https://www.geeksforgeeks.org/chmod-command-linux/)** : Used to modify the access/permission of a user.



`read` https://www.computerhope.com/unix/bash/read.htm

