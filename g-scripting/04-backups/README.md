# Backups

**Doel:** Je leert hoe je met `rsync`, `scp` en `tar` backups maakt van bestanden en mappen, zowel lokaal als naar een externe server.

Gebruik `man rsync`, `man tar`, `man scp`, enz. Gebruik geen Google.

Markeer voltooide opdrachten met een ✅.



## 🔧 Deel 1: Lokale Backups

### ❌ Backup naar tar  
Maak een back-up van de map `~/project` naar een gecomprimeerd `.tar.gz` bestand met de naam `project-backup.tar.gz` in je home-directory.

De opdracht mag bestaande bestanden overschrijven.



### ❌ Automatische dagelijkse tar-backup  
Maak een cronjob die elke dag om 04:00 een backup maakt van `~/Documents` naar een bestand `documents-YYYY-MM-DD.tar.gz` in `~/backups`. Gebruik `date +"%F"` in de bestandsnaam.

Zorg dat de map `~/backups` bestaat!



### ❌ Gestructureerde backupmap  
Gebruik `rsync` om een backup te maken van `~/Documents` naar `~/backups/documents/`. Zorg dat bestanden die verwijderd zijn uit de bron ook uit de bestemming verdwijnen.

Gebruik volgende opties:
- archive mode
- verbose
- delete



## 🌐 Deel 2: Remote Syncing

> Gebruik een remote testserver met `ssh` toegang (bijv. `user@remotehost`).

### ❌ Eenvoudige rsync naar remote  
Gebruik `rsync` om je map `~/project` te synchroniseren naar de remote server onder `/home/user/backups/project/`.



### ❌ rsync met exclude  
Maak een rsync-backup van `~/project` naar de remote server, maar sluit bestanden uit die eindigen op `.tmp` of `.log`.

Tip: gebruik `--exclude='*.log'` en `--exclude='*.tmp'`.



### ❌ Verifieer integriteit  
Gebruik `rsync` met de optie `--checksum` om te verzekeren dat bestanden niet onnodig worden gekopieerd.

Maak een testmap met enkele grote bestanden, pas een paar aan, en test dan het verschil in gedrag tussen `--archive` en `--archive --checksum`.




## 💡 Bonus: pull in plaats van push  
Maak een script op de remote server dat een `rsync` "pull" uitvoert van jouw machine. Plan dit in met een cronjob op de remote server zodat je machine niet zelf iets hoeft te doen.



