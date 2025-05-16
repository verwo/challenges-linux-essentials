# The Command Line

Find all the info you need in the man-pages. Make sure to comment the commands you used to find this information. Try to solve the challenges without making use of the Internet.

Mark challenges using a ✅ once they are finished.

---

## ✅ The man command

The `man` command shows the manual page for a command. It explains what the command does, how to use it, and lists available options.

```bash
man man
```

---

## ✅ The whoami command

The `whoami` command displays the current logged-in username.

```bash
man whoami
```

---

## ✅ The uptime command

The `uptime` command shows how long the system has been running, the number of users, and the system load averages.

```bash
man uptime
```

---

## ✅ Help on ls

`ls -h` does not give help. It shows file sizes in a human-readable format (KB, MB, etc.).
Help for `ls` is available via:

```bash
man ls
```

---

## ✅ Hidden files

Hidden files in Linux start with a dot (`.`). To list them:

```bash
ls -a
```

This shows all files, including hidden ones.

---

## ✅ Special Directories

* `~`: Home directory of the current user
* `.`: Current directory
* `..`: Parent directory
* `/`: Root directory of the filesystem

```bash
echo ~
pwd
echo ..
cd /
```

---

## ✅ What shells are available

Check available shells by reading:

```bash
cat /etc/shells
```

---

## ✅ What date is it

Show the current date and time with:

```bash
date
```

To see options:

```bash
man date
```

---
