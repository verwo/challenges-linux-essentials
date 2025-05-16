# Backups

**Doel:** Je leert hoe je met `rsync`, `scp` en `tar` backups maakt van bestanden en mappen, zowel lokaal als naar een externe server.

Gebruik `man rsync`, `man tar`, `man scp`, enz. Gebruik geen Google.

Markeer voltooide opdrachten met een ✅.

---

## 🔧 Deel 1: Lokale Backups

### ✅ Backup naar tar

```bash
tar -czf ~/project-backup.tar.gz -C ~/ project
```

---

### ✅ Automatische dagelijkse tar-backup

Zorg eerst dat de map bestaat:

```bash
mkdir -p ~/backups
```

Voeg deze regel toe aan je crontab met `crontab -e`:

```cron
0 4 * * * tar -czf ~/backups/documents-$(date +\%F).tar.gz -C ~/ Documents
```

---

### ✅ Gestructureerde backupmap

```bash
rsync -av --delete ~/Documents/ ~/backups/documents/
```

Let op: trailing slashes zijn belangrijk bij `rsync`!

---

## 🌐 Deel 2: Remote Syncing

> Gebruik een remote testserver met `ssh` toegang (bijv. `user@remotehost`).

### ✅ Eenvoudige rsync naar remote

```bash
rsync -av ~/project/ user@remotehost:/home/user/backups/project/
```

---

### ✅ rsync met exclude

```bash
rsync -av --exclude='*.log' --exclude='*.tmp' ~/project/ user@remotehost:/home/user/backups/project/
```

---

### ✅ Verifieer integriteit

Zonder checksum:

```bash
rsync -av ~/testdir/ user@remotehost:/home/user/testbackup/
```

Met checksum:

```bash
rsync -av --checksum ~/testdir/ user@remotehost:/home/user/testbackup/
```

Verschil: met `--checksum` worden bestanden alleen gekopieerd als hun inhoud effectief anders is, zelfs als de timestamp gelijk is.

---

## 💡 Bonus: pull in plaats van push

Op de remote server:

```bash
mkdir -p ~/scripts
nano ~/scripts/pull_backup.sh
```

Inhoud:

```bash
#!/bin/bash
rsync -av user@jouwmachine:/home/user/project/ /home/user/backups/project/
```

Maak uitvoerbaar:

```bash
chmod +x ~/scripts/pull_backup.sh
```

Crontab toevoegen:

```cron
0 * * * * /home/user/scripts/pull_backup.sh
```

---
