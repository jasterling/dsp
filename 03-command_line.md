# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > $ pwd = show current working directory path
> > $ mkdir = make a directory
> > $ rmdir = delete a directory (must be empty)
> > $ touch <filename> = creates a file
> > $ rm = deletes a file
> > $ mv <existing_name> <new_name> = rename a file
> > $ ls -a = show all files, including hidden
> > $ cp <old_path> <new_path> = copies a file from one directory to another
> > $ man <command> = provides explanation of command and its arguments
> > $ chmod <arg> = allows you to edit the access permissions to a file or dir

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > $ ls = list files in current directory
> > $ ls -a = list all files, including hidden, in curr dir
> > $ ls -l = 'long' list files in current directory
> > $ ls -l = 'long' list files, with file size notated with MB, KB, etc.
> > $ ls -lah = long list all files, including hidden, with size notated
> > $ ls -t = list and sort by time modified
> > $ ls -Glp = enable colorized output for listed files, add '\' to indicate path is a directory


---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > $ ls -x = lists files as individual rows
> > $ ls -R = includes subdirectories in list of files
> > $ ls -d = displays only directories
> > $ ls -m = displays files separated by commas
> > $ ls -u = displays file ranked by access time

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > xargs is used when combining multiple commands.
> > ex. $ find . -name "*.md" | xargs rm -rf

 

