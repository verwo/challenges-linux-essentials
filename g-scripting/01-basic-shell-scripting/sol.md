# Remote Access - Oefeningen

## Inleiding

Deze oefeningen zijn bedoeld om je vertrouwd te maken met verschillende manieren van toegang tot een Linux-systeem op afstand, het gebruik van SCP voor bestandsoverdracht, het delen van mappen met Samba, en het opzetten van Docker-containers.

---

## ✅ SSH Toegang Instellen

```bash
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```

Controleer verbinding vanaf een andere machine:

```bash
ssh gebruikersnaam@ip-adres
```

---

## ✅ Bestanden Overdragen met SCP

Kopieer een bestand van lokaal naar remote:

```bash
scp bestand.txt gebruiker@ip:/home/gebruiker/
```

Kopieer van remote naar lokaal:

```bash
scp gebruiker@ip:/home/gebruiker/bestand.txt ./
```

---

## ✅ Een Gedeelde Map Instellen met Samba

1. Installeer Samba:

```bash
sudo apt install samba
```

2. Maak een gedeelde map aan:

```bash
mkdir -p /srv/samba/share
sudo chown nobody:nogroup /srv/samba/share
sudo chmod 0775 /srv/samba/share
```

3. Bewerk `/etc/samba/smb.conf` en voeg toe:

```ini
[Share]
   path = /srv/samba/share
   browsable = yes
   read only = no
   guest ok = yes
```

4. Herstart Samba:

```bash
sudo systemctl restart smbd
```

5. Verbind vanuit Windows: gebruik `\<IP-ADRES>\Share`

---

## ✅ Docker Container Maken en de Hello API Draaien

1. Installeer Docker:

```bash
sudo apt-get install docker.io
```

2. Clone de repo:

```bash
git clone https://github.com/BioBoost/linux-essentials-docker-hello-node-api
cd linux-essentials-docker-hello-node-api
```

3. Bouw en draai container:

```bash
docker build -t hello-node-api .
docker run -p 8000:8000 hello-node-api
```

4. Open `http://localhost:8000` in je browser

---

## ✅ Node-RED Instellen op Docker

1. Start de container:

```bash
docker run -it -p 1880:1880 nodered/node-red
```

2. Open `http://localhost:1880` in je browser

> Let op: Docker moet correct werken in WSL of VM

---
