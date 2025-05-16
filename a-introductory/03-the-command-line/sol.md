# The Command Line

Find all the info you need in the man-pages. Make sure to comment the commands you used to find this information. Try to solve the challenges without using the Internet.

Mark challenges using a ✅ once they are finished.

---

## ❌ The `man` command

**Describe in your own words what the `man` command does.**

The `man` command displays the manual page for a specific command. It provides detailed information such as a description, syntax, available options, and examples.

> Used: `man man`

---

## ❌ The `whoami` command

**Describe in your own words what the `whoami` command does.**

The `whoami` command shows the username of the current user who is logged into the terminal session.

> Used: `man whoami`

---

## ❌ The `uptime` command

**Describe in your own words what the `uptime` command does.**

The `uptime` command shows how long the system has been running, the number of users currently logged in, and the system load averages for the past 1, 5, and 15 minutes.

> Used: `man uptime`

---

## ❌ Help on `ls`

**`ls` can be used to list the files and directories in Linux. If you execute the command `ls -h` you do not get any help about the command. How come? What does `ls -h` actually do?**

The `ls -h` command does not display help because `-h` is not a help flag. It stands for "human-readable" and is used to display file sizes in a readable format (e.g., KB, MB). For help on `ls`, you should use `man ls`.

> Used: `man ls`

---

## ❌ Hidden files

**Linux harbors some hidden files which are not automatically listed when executing `ls`. Find out how to list hidden files. How can we recognize hidden files?**

Hidden files start with a dot (`.`) in their filename. To list them, use:

```bash
ls -a
```

The `-a` option shows all files, including hidden ones.

> Used: `man ls`

---

## ❌ Special Directories

**What do the following symbols refer to when used, for example, with `ls`?**

* `~`: Refers to the current user's home directory.
* `.`: Refers to the current directory.
* `..`: Refers to the parent directory.
* `/`: Refers to the root directory of the filesystem.

> Used: Shell knowledge and `man bash`

---

## ❌ What shells are available

**Check the Internet on how you can get a list of all available shells on your system.**

To list all available shells, use:

```bash
cat /etc/shells
```

This file contains a list of valid login shells on the system.

> Tip: This is not in a man-page, so an exception is made to check the file directly.

---

## ❌ What date is it

**How would you request the current date and time via the terminal?**

Use the `date` command:

```bash
date
```

This displays the current system date and time.

> Used: `man date`

---
