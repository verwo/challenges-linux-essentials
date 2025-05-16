## Uncomplicated Firewall

Try to solve the challenges without using google. Better to use the man-pages to find the information you need.

Mark challenges using a ✅ once they are finished.

---

## ✅ Enable Firewall

1. Install ufw:

```bash
sudo apt install ufw
```

2. Allow SSH:

```bash
sudo ufw allow ssh
```

3. Set default rules:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

4. Enable the firewall:

```bash
sudo ufw enable
```

5. Check status:

```bash
sudo ufw status verbose
```

---

## ✅ Setup Apache

1. Install Apache:

```bash
sudo apt install apache2
```

2. Allow HTTP traffic:

```bash
sudo ufw allow http
```

3. Enable Apache service:

```bash
sudo systemctl enable apache2
sudo systemctl start apache2
```

4. Test in web browser:
   Open `http://<raspberrypi-ip>` in a browser on another device in the same network.

---
