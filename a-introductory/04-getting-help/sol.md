# Getting Help

Find all the info you need in the man-pages. Make sure to comment the commands you used to find this information. Try to solve the challenges without making use of the Internet.

Mark challenges using a ✅ once they are finished.

## ✅ The free command

*Describe in your own words what the `free` command does. Give an example and a partial output.*

The `free` command shows the total amount of free and used physical and swap memory in the system.

> Used: `man free`

**Example:**

```bash
free -h
```

**Partial output:**

```
              total        used        free      shared  buff/cache   available
Mem:           15Gi       2.1Gi       9.8Gi       142Mi       3.1Gi        12Gi
Swap:         2.0Gi          0B       2.0Gi
```

---

## ✅ The id command

*Describe in your own words what the `id` command does. Give an example and a partial output.*

The `id` command displays the user ID (UID), group ID (GID), and groups the current user belongs to.

> Used: `man id`

**Example:**

```bash
id
```

**Partial output:**

```
uid=1000(wouter) gid=1000(wouter) groups=1000(wouter),27(sudo),1001(dev)
```

---

## ✅ The tree command

*Describe in your own words what the `tree` command does. How do you list all subdirectories too? How can you only include directories?*

The `tree` command displays directories and files in a tree-like structure.

* To list all subdirectories and files:

  ```bash
  tree
  ```
* To include only directories:

  ```bash
  tree -d
  ```

> Used: `man tree`

---

## ✅ The which command

*Describe in your own words what the `which` command does. What is the result for `pwd` ?*

The `which` command shows the full path of the executable that would be run when the command is entered.

> Used: `man which`

**Example:**

```bash
which pwd
```

**Result:**

```
/bin/pwd
```

---

## ✅ The file command

*Describe in your own words what the `file` command does. What is the result for `~/.bashrc` ?*

The `file` command determines the type of a file by examining its contents.

> Used: `man file`

**Example:**

```bash
file ~/.bashrc
```

**Result:**

```
/home/wouter/.bashrc: ASCII text
```

---

## ✅ The type command

*Describe in your own words what the `type` command does. What is the result for `ls` and what is the result for `g++` ?*

The `type` command tells how a command name is interpreted (e.g., alias, shell builtin, function, or executable).

> Used: `man bash` (search `type`)

**Examples:**

```bash
type ls
type g++
```

**Result:**

```
ls is aliased to `ls --color=auto`
g++ is /usr/bin/g++
```

---

## ✅ Counting lines and words

*What command can be used to count lines and words in text? Give an example and explain the output.*

Use the `wc` (word count) command.

**Example:**

```bash
wc -l -w example.txt
```

**Explanation:**

* `-l` counts lines
* `-w` counts words

**Sample output:**

```
      15     250 example.txt
```

---

## ✅ The wget command

*How can you download a file from the Internet using the command line?*

Use the `wget` command.

**Example:**

```bash
wget https://example.com/sample.txt
```

> Used: `man wget`

---

## ✅ The dmesg command

*Describe in your own words what the `dmesg` command does. Give an example and a partial output.*

`dmesg` displays system messages from the kernel ring buffer, such as hardware detection and driver messages.

> Used: `man dmesg`

**Example:**

```bash
dmesg | head
```

**Partial output:**

```
[    0.000000] Linux version 5.15.0-75-generic ...
[    0.000000] Command line: BOOT_IMAGE=/vmlinuz root=UUID=...
```

---

## ✅ Checksums

*Download the Raspberry Pi OS image using wget and verify its SHA-256 checksum.*

```bash
wget https://downloads.raspberrypi.org/raspios_armhf_latest
sha256sum raspios_armhf_latest
```

Compare the result with the checksum on the Raspberry Pi website.

**Tool used:** `sha256sum`

**Use of this hash:**
To verify file integrity and detect any corruption or tampering during download.

---

## ✅ The printenv command

*Describe in your own words what the `printenv` command does.*

`printenv` displays environment variables and their values.

> Used: `man printenv`

**Example:**

```bash
printenv HOME
```

**Output:**

```
/home/wouter
```

---

## ✅ IP Address

*Find the IP address of your WiFi interface. What command did you use?*

**Command:**

```bash
ip addr show
```

Look under the section for `wlan0` or similar.

**Partial output:**

```
inet 192.168.0.42/24 brd 192.168.0.255 scope global dynamic wlan0
```

---

## ✅ IP of Sivir Server

*What is the IP address of the server `project.devbit.be`?*

**Command:**

```bash
ping -c 1 project.devbit.be
```

**Output:**

```
PING project.devbit.be (185.3.216.131) ...
```

---

## ✅ The nslookup command

*Describe in your own words what the `nslookup` command does.*

`nslookup` queries DNS to obtain domain name or IP address mapping.

> Used: `man nslookup`

**Example:**

```bash
nslookup google.com
```

**Output:**

```
Name:   google.com
Address: 142.250.179.14
```

---
