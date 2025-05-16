# The Filesystem

Try to solve the challenges without using google. Better to use the man-pages to find the information you need.

Mark challenges using a ✅ once they are finished.

## ✅ touch

*What does `touch` actually do? Demonstrate using an example.*

The `touch` command creates an empty file or updates the access and modification timestamps of an existing file.

```bash
touch testfile
ls -l testfile
```

---

## ✅ Authentication Log

*There is a file on the system that logs authentication changes and failures. Can you guess where it can be found? Provide the path to the file.*

```bash
/var/log/auth.log
```

---

## ✅ Apt Source List

*The apt tool uses a configuration file which specifies in which repositories it should look for packages. Its called the apt `sources.list` file. Can you guess where it can be found? Provide the path to the file.*

```bash
/etc/apt/sources.list
```

---

## ✅ Tmp Filesystem

*Create a file called `hello` in `/tmp`. Restart your linux distro using `reboot`. Where is the file? What happened?*

```bash
touch /tmp/hello
reboot
ls /tmp/hello
```

The file is gone after reboot. `/tmp` is a temporary filesystem cleared on boot.

---

## ✅ Timestamps

*Create a file called `first-of-many` in your home directory. Use `nano` to add some content to the file. Now list the details of the file such as the size and when it was last modified.*

```bash
nano ~/first-of-many
ls -lh ~/first-of-many
```

This shows size, permissions, and timestamp.

---

## ✅ No space for spaces

*Try to create a file called `second try` (with the space included). What happened? Why? How to fix it?*

```bash
touch second try  # Fails: tries to create two files
```

To fix:

```bash
touch "second try"
```

or

```bash
touch second\ try
```

---

## ✅ The root

*Try to create a directory `/backups`. Why is it failing? Now use `sudo` to do it. Try creating a file in it.*

```bash
mkdir /backups  # Fails: permission denied
sudo mkdir /backups
sudo touch /backups/README.md
```

You need root privileges to write to `/`.

---

## ✅ Bash RC

*In your home directory you will find a file called `.bashrc`. Create a backup of that file called `.bashrc.bak`.*

```bash
cp ~/.bashrc ~/.bashrc.bak
```

---

## ✅ Sym Linking

*What does the tool `ln` allow you to do? Create a link called `secrets` to `/etc/passwd`.*

```bash
ln -s /etc/passwd ~/secrets
cat ~/secrets
```

This shows the contents of `/etc/passwd` via the symbolic link.

---

## ✅ SD Card

*Plug in an SD Card or USB stick. Where is the block device? Where is it mounted?*

```bash
lsblk
```

Example output:

```
sdb      8:16   1  7.5G  0 disk 
└─sdb1   8:17   1  7.5G  0 part /media/user/USB
```

* Block device: `/dev/sdb`
* Mount point: `/media/user/USB`
* Difference: block device is hardware, mount point is where it is accessible in the filesystem.

---

## ✅ My Own Local Domain Name

1. *Backup `/etc/hosts`:*

```bash
mkdir -p ~/backups
sudo cp /etc/hosts ~/backups
```

2. *Use of `/etc/hosts`:*
   A local mapping of hostnames to IP addresses, used before DNS.

3. *Add and test entry:*

```bash
echo "127.0.0.1 hellokitty.dev" | sudo tee -a /etc/hosts
ping -c 1 hellokitty.dev
```

Output shows ping to 127.0.0.1

---

## ✅ Chuck

1. *Clone repo:*

```bash
git clone https://github.com/BioBoost/chuck_norris_facts.git ~/projects
```

2. *Rename:*

```bash
mv ~/projects/chuck_norris_facts ~/projects/facts_about_chuck_norris
```

3. *Keep only README.md:*

```bash
cd ~/projects/facts_about_chuck_norris
rm -rf !(README.md)
rm -rf .git
```

(Note: You may need `shopt -s extglob` for advanced globbing)

---

## ✅ Oh My API

1. *Create directories:*

```bash
mkdir -p ~/projects/oh_my_api/src
```

2. *Create file:*

```bash
touch ~/projects/oh_my_api/src/index.js
```

3. *Run `npm init`:*

```bash
cd ~/projects/oh_my_api
npm init -y
```

4. *Install express:*

```bash
npm install express
```

5. *Edit `index.js`:*

```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => res.send('Welcome to Oh My API'))
app.listen(port, () => console.log(`App is listening on port ${port}!`))
```

6. *Run app and test from browser or Insomnia*

```bash
node src/index.js
```

---
