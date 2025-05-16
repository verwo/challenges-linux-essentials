# Locating Things

Document all the commands and their output on your system. If the output is too long take a couple of lines and add `...` at the end.

Mark challenges using a ✅ once they are finished.

## ✅ Locate

Install and update:

```bash
sudo apt install mlocate
sudo updatedb
```

Locate files:

```bash
locate sudoers.dist
/etc/sudoers.dist

locate ssh_config
/etc/ssh/ssh_config

locate auth.log
/var/log/auth.log
```

---

## ✅ Python man-pages

```bash
whereis python
python: /usr/bin/python /usr/lib/python3.10 ... /usr/share/man/man1/python.1.gz
```

---

## ✅ Binary of find

```bash
whereis find
find: /usr/bin/find /usr/share/man/man1/find.1.gz
```

---

## ✅ Which

```bash
which passwd
/usr/bin/passwd

which locate
/usr/bin/locate

which fdisk
/sbin/fdisk
```

**passwd** is user-facing, **fdisk** is an admin tool found in `/sbin`.
**fdisk** is used for partitioning hard disks.

---

## ✅ kernel.log

```bash
sudo find / -name kernel.log 2>/dev/null
/var/log/kern.log
```

---

## ✅ .bashrc

```bash
find /home -name .bashrc 2>/dev/null
/home/user/.bashrc
/home/davy/.bashrc
```

---

## ✅ System Configuration Files

```bash
find /etc -type f -name "*system*.conf" 2>/dev/null
/etc/systemd/system.conf
/etc/systemd/user.conf
```

---

## ✅ User Readable Files

```bash
find /etc -readable -type f 2>/dev/null | head -n 5
/etc/hosts
/etc/hostname
...
```

Use `-readable` to find files readable by the current user.

---

## ✅ Altered Log Files

```bash
find /var/log -type f -mtime -1 -exec ls -lh {} + 2>/dev/null
-rw-r----- 1 syslog adm 50K May 16 10:00 /var/log/syslog
...
```

---

## ✅ Steal All Logs

```bash
sudo mkdir -p /tmp/logs
sudo find / -type f -name "*.log" -exec cp --parents {} /tmp/logs \; 2>/dev/null
```

This copies all `.log` files preserving paths.

---

## ✅ Markdown README files

```bash
find / -type f -iname "readme.md" 2>/dev/null
/home/user/projects/facts_about_chuck_norris/README.md
...
```

The `-iname` option makes the search case-insensitive.

---
