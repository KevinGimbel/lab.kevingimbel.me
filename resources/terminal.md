---
layout: default
title: "Terminal"
exclude: true
---

# Terminal

The Terminal is a program installed on all computers. It can be used to interact with the computers file system or to execute programs. With a terminal you can do everything you would do with your GUI (_Graphic User Interface_). Creating files and folders, starting applications or executing programs - all these things are possible from a terminal.

A Terminal has a Prompt which shows some informations about the logged-in user, the computer and the path (directory) you are in. When writing about terminal the `$` is used as a prompt placeholder. You prompt might looks like one of the following.

```sh
bash-3.2$

kevin@MacBook-Pro $

root #

% ~/Dev
```

You can change your prompt as you wish. The prompt configuration is huge and beyond the scope of this resource file. You can read more [on https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html](https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html).

## Opening a terminal

To open a Terminal you typically press `CTRL + ALT + T` or `CTRL + CMD + T`, you can also search your computer for the `CMD` (Windows) or `bash` (Linux / Mac OS) application. You will see a program open with a Prompt (see above) where you can enter text. Type in `echo "Hello Terminal"` and press `Enter`.

## Some basic commands

### Creating files

New files can be created without any content with `touch`. If you `touch` a file it is simply created on the hard drive without any content inside. To create the file `test.txt` use `touch test.txt`.

To find out more, run `man touch` inside your terminal to read the manual.

### Writing into a file

`echo` is a program that "echoes" back whatever you give it as content - it's like you would shout into a cave and the echo comes back. `echo "Hello World!"` will write `Hello World` to the terminal. To write into a file, you can redirect the output with `>` as seen below.

```sh
$ echo "Hello world" > test.txt
```
To find out more, run `man echo` inside your terminal to read the manual.

### Viewing a file

To view a file inside your terminal you can use `less` or `cat`. `less` will open the file inside the terminal and you can move forward and backward with the UP and DOWN key. `cat` will output the file to the terminal (see below).

```sh
$ echo "Test!" > test.txt
$ less test.txt
Test!
```
To find out more, run `man less` inside your terminal to read the manual.

### cat

`cat` is short for concatenate which means "put together". Cat can be used to combine two or more files into one file and is often abused to view files in a terminal. The "correct" way to view a file is `less` but you can also use `cat` as shown below.

```sh
$ cat test.txt
Test!
```

For small files viewing them with `cat` is okay and you will find this around the internet a lot in tutorials. The actual use case of `cat`, the concatenation of files, is shown below. We create two files, `a.txt` and `b.txt`, the we use `cat` to combine them into `c.txt`.

```sh
$ echo "I am A" > a.txt
$ echo "I am B" > b.txt
$ cat a.txt b.txt > c.txt
$ less c.txt
I am A
I am B
```

As you can see the text from both files got combined in `c.txt`.

To find out more, run `man cat` inside your terminal to read the manual.

### Listing files

To view files, you can use the `ls` command. This will output all files and folders in the current directory. To view hidden files (= files starting with a dot), use `ls -h`. To view file owners and last modify dates, use `ls -al`.

The output looks like this

```sh
$ ls -ahl
total 24
drwxr-xr-x   5 kevingimbel  staff   170B Feb 15 18:38 .
drwxr-xr-x  14 kevingimbel  staff   476B Feb 15 23:14 ..
-rw-r--r--   1 kevingimbel  staff   433B Feb 15 21:22 footer.html
-rw-r--r--   1 kevingimbel  staff   258B Feb 15 18:49 head.html
-rw-r--r--   1 kevingimbel  staff   1.2K Feb 15 21:33 header.html
```

To find out more, run `man ls` inside your terminal to read the manual.

### Creating a new folder

To create a new folder inside a terminal you use the `mkdir` command (`mkdir` = make directory).

```sh
$ mkdir test
$ ls
test
```

To find out more, run `man mkdir` inside your terminal to read the manual.

### Removing files

`rm` (`rm` = remove) is used to remove files and directories from the system. **CAUTION:** Files deleted with `rm` are not placed inside your trash bin - they are gone and hard to recover so pay attention when deleting files.

To delete a file called `test.txt`, you execute `rm test.txt`. To execute a directory you need to add the `-r` (recursive) parameter like so `rm -r test-directory`.

**CAUTION:** `rm` has a parameter named `-f`. `-f` stands for _force_ and will not ask you when removing files and folders. If you run this command with administrator rights, e.g. `sudo rm -rf` on Ubuntu, you can destroy your entire computer because the computer can delete all files on the hard drive including the entire system! I personally recommend to never run `rm -rf` even if you think you know what you are doing.

To find out more, run `man rm` inside your terminal to read the manual.
