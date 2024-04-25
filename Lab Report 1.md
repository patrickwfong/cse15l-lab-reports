**Lab Report 1**\
Patrick Fong\
A14080869\
\
**Example of running `cd` with no arguments:**
```
user@users-Air-2 desktop % cd
users@users-Air-2 ~ %
```
* Absolute path to the working directory prior to running the command: /Users/user/desktop
* Running `cd` with no arguments brought me to my home directory.
* This was not an error.

**Example of running `cd` with a path to a directory as an argument:**
```
user@users-Air-2 ~ % cd desktop
user@users-Air-2 desktop % 
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `cd` with the argument `desktop` brought me to the `desktop` directory.
* This was not an error.

**Example of running `cd` with a path to a file as an argument:**
```
user@users-Air-2 desktop % cd dummyfile.txt
cd: not a directory: dummyfile.txt
```
* Absolute path to the working directory prior to running the command: /Users/user/desktop
* Running `cd` with the argument `dummyfile.txt` produced an error, since `dummyfile.txt` is not a directory.
* This output is an error, since `dummyfile.txt` is not a directory.

**Example of running `ls` from my home directory with no arguments:**
```
user@users-Air-2 ~ % ls
Applications    Downloads       Library         Pictures        java
Desktop         FileSearch.sh   Movies          Public          wavelet
Documents       IdeaProjects    Music           hello.txt
user@users-Air-2 ~ % 
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `ls` with no arguments displays all directories and files in my current directory, which was my home directory.
* This was not an error.

**Example of running `ls` with a path to a directory as an argument:**
```
user@users-Air-2 ~ % ls /Users/user/desktop
CIS36A          dummyfile.txt   one
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `ls` with the directory `desktop` as an argument displays all directories and files in the designated directory, `desktop`.
* This was not an error.

**Example of running `ls` with a path to a file as an argument:**
```
user@users-Air-2 ~ % ls /Users/user/desktop/dummyfile.txt
/Users/user/desktop/dummyfile.txt
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `ls` with the absolute path to the file `dummyfile.txt` as an argument displays the relative path to `dummyfile.txt`.
* This was not an error.

**Example of running `cat` from my home directory with no arguments:**
```
user@users-Air-2 ~ % cat
some
some
random
random
stuff
stuff
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `cat` with no arguments waits for lines, reads them from stdin and outputs them to stdout.
* This was not an error.

**Example of running `cat` from my home directory with a path to a directory as an argument:**
```
user@users-Air-2 ~ % cat /Users/user/desktop
cat: /Users/user/desktop: Is a directory
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `cat` with the absolute path to a directory as an argument produces an output saying that the argument is a directory.
* This was not an error.

**Example of running `cat` from my home directory with a path to a `.txt` file as an argument:**
```
user@users-Air-2 ~ % cat /Users/user/desktop/dummyfile.txt
dummytext%                                                                                          
user@users-Air-2 ~ %
```
* Absolute path to the working directory prior to running the command: /Users/user
* Running `cat` with the absolute path to a `.txt` file as an argument outputs the contents of that `.txt` file. In this case, the `.txt` file in question was `dummyfile.txt` and its contents were `dummytext%`.
* This was not an error.
