# Ownership and Permissions

Make sure to document all your commands here.

Unless specified otherwise, all commands should be executed in a terminal session logged in with your own user account.

Mark challenges using a ✅ once they are finished.

## ✅ Sudo

```bash
id
```

Shows current user's UID, GID and group memberships.

```bash
sudo id
```

This shows the UID and GID of root, because the command runs as root.

---

## ✅ New User Davy

1. Create the user:

```bash
sudo adduser davy
```

2. Switch user:

```bash
su davy
```

3. Try using `sudo`:

```bash
sudo touch ~/i_am_legend
```

Fails because `davy` is not in the `sudo` group.

4. Exit and add to group:

```bash
exit
sudo usermod -aG sudo davy
```

5. Try again:

```bash
su davy
sudo touch ~/i_am_legend
```

Now it works.

6. Exit:

```bash
exit
```

7. Become root:

```bash
sudo su
```

8. Switch to `davy`:

```bash
su davy
```

No password needed because you're already root.

---

## ✅ Auth.log

```bash
sudo tail -f /var/log/auth.log
```

Then run:

```bash
sudo ls
```

This logs an authentication entry in `/var/log/auth.log`.

---

## ✅ Editable Text Configuration

```bash
ls -ld /etc
```

* Owner is `root`
* Permissions: `drwxr-xr-x`

Readable because of `r` for 'others' and executable (`x`) to allow traversal.

---

## ✅ Davy's Secrets

1. Create file:

```bash
echo "secret" > /tmp/davys_secrets.txt
```

2. Check permissions:

```bash
ls -l /tmp/davys_secrets.txt
```

3. Change owner:

```bash
sudo chown davy /tmp/davys_secrets.txt
```

4. Lock out others:

```bash
chmod 600 /tmp/davys_secrets.txt
```

---

## ✅ Sudo created files

1. Create file:

```bash
sudo touch /tmp/my_root.txt
```

2. Check ownership:

```bash
ls -l /tmp/my_root.txt
```

Owned by `root`

3. Change permissions:

```bash
sudo chmod 640 /tmp/my_root.txt
```

User can no longer read unless root or in the same group.

---

## ✅ Recursive

1. Create directories and files:

```bash
mkdir -p /tmp/arts/colors
cd /tmp/arts/colors
touch red green blue

mkdir -p /tmp/arts/musical_notes
cd /tmp/arts/musical_notes
touch do re mi
```

2. List recursively:

```bash
ls -lR /tmp/arts
```

3. Change ownership:

```bash
sudo chown -R davy /tmp/arts
```

4. Fix mistake:

```bash
sudo chown -R root:davy /tmp/arts
```

---

## ✅ Developers group

1. Create group:

```bash
sudo groupadd devs
getent group devs
```

2. Add users:

```bash
sudo usermod -aG devs $USER
sudo usermod -aG devs davy
```

3. Create directory:

```bash
sudo mkdir /projects
```

4. Set ownership and permissions:

```bash
sudo chown root:devs /projects
sudo chmod 770 /projects
```

5. Add user dirs:

```bash
sudo mkdir /projects/wouter
sudo mkdir /projects/davy
sudo chown wouter /projects/wouter
sudo chown davy /projects/davy
```

6. Restrict access:

```bash
sudo chmod 750 /projects/wouter
sudo chmod 750 /projects/davy
```

7. Test with `su` or login sessions

---
