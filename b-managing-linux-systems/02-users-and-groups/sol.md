# Users and Groups

Try to solve the challenges without using google. Better to use the man-pages to find the information you need.

Mark challenges using a ✅ once they are finished.

## ✅ System user accounts

*Try to login to the `daemon` system user account. Use `sudo su daemon`. What does it display as a message ? What application is outputting this message ? Run that application and prove it.*

```bash
sudo su daemon
This account is currently not available.
```

This message is output by `/usr/sbin/nologin`, which is set as the shell for system accounts like `daemon`.
You can confirm this by running:

```bash
/usr/sbin/nologin
```

---

## ✅ Creating group with id

*Create a group called `hackers` with the specific group id `1337`. Now create two users (students from the class) and add them both the group.*

```bash
sudo groupadd -g 1337 hackers
sudo useradd -m -G hackers student1
sudo useradd -m -G hackers student2
```

Confirm with:

```bash
grep hackers /etc/group
```

---

## ✅ Difference false and nologin

*Some user entries are showing `/bin/false` as the shell command. Do some research and explain what the difference is with `/usr/sbin/nologin`.*

* `/bin/false` exits with status 1 and produces no message.
* `/usr/sbin/nologin` exits with status 1 **and** displays a message (“This account is currently not available.”).

Use:

```bash
/bin/false
/usr/sbin/nologin
```

To see the difference.

---

## ✅ The auth.log file

*What does the file `/var/log/auth.log` track? Provide an example of a command that shows entries being added to the log after you executed the command. Include the entry here that was added to the file.*

The file `/var/log/auth.log` tracks authentication and authorization events (login attempts, sudo usage, etc.).

Example:

```bash
sudo ls
sudo tail -n 10 /var/log/auth.log
```

**Sample entry:**

```
May 16 16:22:01 host sudo:   user : TTY=pts/0 ; PWD=/home/user ; USER=root ; COMMAND=/bin/ls
```

---

## ✅ Locking out Steve

*Create a new user steve and set a password for the user. Login to the `steve` account using `su` to make sure it works.*

```bash
sudo useradd -m steve
sudo passwd steve
su - steve
```

*Now lock the user account completely:*

```bash
sudo usermod -L steve
sudo usermod -s /usr/sbin/nologin steve
```

This disables login entirely for `steve`, even by `su` or `root`.

---

## ✅ Zsh Shell

*Install the zsh shell on your system. Now change your own shell to `zsh`. Make sure to do this in such a way that a new session will also use `zsh`.*

```bash
sudo apt install zsh
chsh -s $(which zsh)
```

Log out and back in or start a new terminal session to activate `zsh`.

---

## ✅ Semester Account

*Create a new account for an exchange student called `maggie`. Make sure the account can only be used until 31st of august of the next year.*

```bash
sudo useradd -m -e 2026-08-31 maggie
sudo passwd maggie
```

You can verify with:

```bash
sudo chage -l maggie
```

---
