# ***Further research on command : ls***

## About ls

(courtesy of ChatGPT and atatus.com,[Link](https://www.atatus.com/blog/ls-command-in-linux-with-example/))

> The `ls` command is a commonly used command in Unix-based operating systems like Linux and macOS. It stands for "list directory contents" and is used to display a list of files and directories in the current working directory or a specified directory.

> When you run the `ls` command, it will display the names of all files and directories in the current directory in alphabetical order. By default, it will display only the names of files and directories, but you can use various options and arguments to customize the output.

We've used ls eversince we started introducing basic terminal commands, but in reality, it has many additional features that we did not cover in class.

In this lab report, I will explore more options that we can add to `ls` to make it more powerful. 

---

## ls -l

The `ls -l` option displays the contents of the current directory in a long listing format, one per line. The line begin with the file or directory permission, owner and group name, file size, created/modified date and time, file/folder name as some of the attributes.

```
[cs15lwi23ahh@ieng6-201]:~:397$ ls
grader-skill-demo2  nano.save      perl5             skill-demo1-server
lab7                path-examples  skill-demo1-data  wavelet
[cs15lwi23ahh@ieng6-201]:~:398$ ls -l
total 28
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Mar 16 01:36 grader-skill-demo2
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb 28 12:28 lab7
-rw------- 1 cs15lwi23ahh ieng6_cs15lwi23    6 Feb 23 03:06 nano.save
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 23:05 path-examples
drwxr-sr-x 2 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 18 13:18 perl5
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:40 skill-demo1-data
drwxr-s--- 6 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:01 skill-demo1-server
drwxr-s--- 3 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 19 13:11 wavelet
[cs15lwi23ahh@ieng6-201]:~:399$ 
```

from the above example, we can see how -l gives us more information, compared to plain `ls`.

## ls -a

Also mentioned during lecture, the -a prompt allows us to display files that start with `.`. for Example:

```
[cs15lwi23ahh@ieng6-201]:~:400$ ls -a
.              .kshrc          .profile            path-examples
..             .local          .ssh                perl5
.bash_history  .locallogin     .zprofile           skill-demo1-data
.bash_profile  .login          .zshenv             skill-demo1-server
.bashrc        .modulesbegenv  .zshrc              wavelet
.cache         .motd           grader-skill-demo2
.config        .pki            lab7
.cshrc         .procmailrc     nano.save
```

## ls -r

unlike what we discussed in grep -r, which stands for "recursively find", the -r for ls stands for reversely showing items in the current directory. 

```
[cs15lwi23ahh@ieng6-201]:~:397$ ls -r
wavelet             skill-demo1-data  path-examples  lab7
skill-demo1-server  perl5             nano.save      grader-skill-demo2

[cs15lwi23ahh@ieng6-201]:~:397$ ls
grader-skill-demo2  nano.save      perl5             skill-demo1-server
lab7                path-examples  skill-demo1-data  wavelet

```

this could be useful if we want to locate a file that is located at the bottom of the list.


## ls -t

this command is used to show files in chronological order. We can use -lt (combines -l and -t) to confirm. We cann also combine it with -r to show all files in reverse chronological order (`-ltr`).

```
[cs15lwi23ahh@ieng6-201]:~:398$ ls -t
grader-skill-demo2  nano.save      skill-demo1-data    wavelet
lab7                path-examples  skill-demo1-server  perl5

[cs15lwi23ahh@ieng6-201]:~:399$ ls -lt
total 28
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Mar 16 01:36 grader-skill-demo2
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb 28 12:28 lab7
-rw------- 1 cs15lwi23ahh ieng6_cs15lwi23    6 Feb 23 03:06 nano.save
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 23:05 path-examples
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:40 skill-demo1-data
drwxr-s--- 6 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:01 skill-demo1-server
drwxr-s--- 3 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 19 13:11 wavelet
drwxr-sr-x 2 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 18 13:18 perl5

[cs15lwi23ahh@ieng6-201]:~:400$ ls -ltr
total 28
drwxr-sr-x 2 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 18 13:18 perl5
drwxr-s--- 3 cs15lwi23ahh ieng6_cs15lwi23 4096 Jan 19 13:11 wavelet
drwxr-s--- 6 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:01 skill-demo1-server
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 18:40 skill-demo1-data
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb  7 23:05 path-examples
-rw------- 1 cs15lwi23ahh ieng6_cs15lwi23    6 Feb 23 03:06 nano.save
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4096 Feb 28 12:28 lab7
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4096 Mar 16 01:36 grader-skill-demo2
```
## ls -h

This is an interesting command that allows us to see the size of the data in a more user-friendly format. 

```
[cs15lwi23ahh@ieng6-201]:~:401$ ls -lh
total 28K
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4.0K Mar 16 01:36 grader-skill-demo2
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4.0K Feb 28 12:28 lab7
-rw------- 1 cs15lwi23ahh ieng6_cs15lwi23    6 Feb 23 03:06 nano.save
drwxr-s--- 5 cs15lwi23ahh ieng6_cs15lwi23 4.0K Feb  7 23:05 path-examples
drwxr-sr-x 2 cs15lwi23ahh ieng6_cs15lwi23 4.0K Jan 18 13:18 perl5
drwxr-s--- 4 cs15lwi23ahh ieng6_cs15lwi23 4.0K Feb  7 18:40 skill-demo1-data
drwxr-s--- 6 cs15lwi23ahh ieng6_cs15lwi23 4.0K Feb  7 18:01 skill-demo1-server
drwxr-s--- 3 cs15lwi23ahh ieng6_cs15lwi23 4.0K Jan 19 13:11 wavelet
```

We can see that the file size's unit became k, which stands for kilobits. We can also see the total size of all files. For example, we can see "total 28k". 

## ls -Q/-m

This is a command more for formatting purposes, but one could definitely see it being useful when we want to extract files in a separator, for example, when we want to put these file names in to a csv file. 

```
[cs15lwi23ahh@ieng6-201]:~:410$ ls -Q
"grader-skill-demo2"  "nano.save"      "perl5"             "skill-demo1-server"
"lab7"                "path-examples"  "skill-demo1-data"  "wavelet"

[cs15lwi23ahh@ieng6-201]:~:408$ ls -m
grader-skill-demo2, lab7, nano.save, path-examples, perl5, skill-demo1-data,
skill-demo1-server, wavelet
```





