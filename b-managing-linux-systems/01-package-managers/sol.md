# Package Managers

Find all the info you need in the man-pages. Make sure to comment the commands you used to find this information. Try to solve the challenges without making use of the Internet.

Mark challenges using a ✅ once they are finished.

## ✅ Cowsay

*Download the `.deb` package for `cowsay` and install it using `dpkg`. You can find the package at [https://packages.debian.org/sid/all/cowsay/download](https://packages.debian.org/sid/all/cowsay/download).*

**Solution:**

```bash
wget http://ftp.de.debian.org/debian/pool/main/c/cowsay/cowsay_3.03+dfsg2-8_all.deb
dpkg -i cowsay_3.03+dfsg2-8_all.deb
```

*Run it once it's installed. What does it do ?*

```bash
cowsay "Hello Linux!"
```

**Output:** A talking ASCII cow displays your message in a speech bubble.

---

## ✅ Nmap

*Install the `nmap` package using `apt`.*

```bash
sudo apt update
sudo apt install nmap
```

*Port scan the server `docker.veict.lan`. What services are running?*

```bash
nmap docker.veict.lan
```

**Example Output:**

```
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
1883/tcp open  mqtt
```

---

## ✅ NodeJS

*Install Node.js v18.x from Nodesource:*

```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
```

*Check version:*

```bash
node --version
```

**Expected Output:**

```
v18.18.0
```

*Run NodeJS and test code:*

```bash
node
> console.log("Hello World from JavaScript");
Hello World from JavaScript
```

---

## ✅ Dhcpdump

*Install and capture DHCP traffic:*

```bash
sudo apt install dhcpdump
sudo dhcpdump -i eth0
```

*Ask another student to connect to the network.*

*Identify the MAC address from the dump and verify it:*

```bash
ip link show
```

---

## ✅ MQTT

*Install mosquitto-clients:*

```bash
sudo apt install mosquitto-clients
```

*Send your name to topic `linux/students` on broker `emqx.veict.lan`:*

```bash
mosquitto_pub -h emqx.veict.lan -t linux/students -m "Wouter" -u student -P Student123
```

---

## ✅ tree command

What does the `tree` command do? How do you list all subdirs too? How can you only include directories?

**Answer:**

* The `tree` command displays the directory structure as a tree.
* To list everything including subdirectories:

  ```bash
  tree
  ```
* To only include directories:

  ```bash
  tree -d
  ```

> Used: `man tree`

---
