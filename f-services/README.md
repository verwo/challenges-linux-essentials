# Remote Access - Oefeningen

## Inleiding
Deze oefeningen zijn bedoeld om je vertrouwd te maken met verschillende manieren van toegang tot een Linux-systeem op afstand, het gebruik van SCP voor bestandsoverdracht, het delen van mappen met Samba, en het opzetten van Docker-containers.

### Doelen
- SSH toegang tot een systeem opzetten.
- Bestanden overdragen met SCP.
- Een gedeelde map instellen met Samba.
- Een Docker-container opzetten met een Hello API.

---

## Oefening 1: SSH Toegang Instellen

### Doel:
Stel een SSH-server in op een Linux-systeem en test de verbinding vanaf een andere machine.

### Stappen:
1. **Installeer de SSH-server**:
   - Voer het volgende commando uit om de SSH-server op je Linux-systeem te installeren:
     ```bash
     sudo apt-get update
     sudo apt-get install openssh-server
     ```

2. **Controleer of de SSH-server actief is**:
   - Controleer de status van de SSH-server:
     ```bash
     sudo systemctl status ssh
     ```

3. **Verbind via SSH**:
   - Verbind vanaf een andere machine naar je Linux-systeem met het volgende commando:
     ```bash
     ssh <username>@<ip-adres>
     ```

4. **Test de verbinding**:
   - Voer een eenvoudige opdracht uit nadat je verbonden bent, bijvoorbeeld:
     ```bash
     uname -a
     ```

---

## Oefening 2: Bestanden Overdragen met SCP

### Doel:
Gebruik SCP om bestanden te kopiëren tussen een lokale machine en een remote machine.

### Stappen:
1. **Kopieer een bestand naar een remote machine**:
   - Gebruik SCP om een bestand van je lokale systeem naar de remote machine te kopiëren:
     ```bash
     scp <bestand> <username>@<ip-adres>:/pad/naar/doelmap/
     ```

2. **Kopieer een bestand van de remote machine naar je lokale systeem**:
   - Gebruik SCP om een bestand van de remote machine naar je lokale systeem te kopiëren:
     ```bash
     scp <username>@<ip-adres>:/pad/naar/remote-bestand <doelmap-op-lokaal-systeem>
     ```

3. **Controleer de bestanden**:
   - Controleer of het bestand correct is overgedragen door `ls` te gebruiken in de doelmap.

---

## Oefening 3: Een Gedeelde Map Instellen met Samba

### Doel:
Stel een gedeelde map in op een Linux-systeem en verbind deze met een Windows-machine.

### Stappen:
1. **Installeer Samba**:
   - Installeer Samba op je Linux-systeem:
     ```bash
     sudo apt-get install samba samba-common-bin
     ```

2. **Maak een gedeelde map aan**:
   - Maak een map die je wilt delen:
     ```bash
     mkdir ~/sambashare
     ```

3. **Configureer Samba**:
   - Open het configuratiebestand van Samba:
     ```bash
     sudo nano /etc/samba/smb.conf
     ```
   - Voeg de volgende configuratie toe aan het einde van het bestand:
     ```bash
     [sambashare]
     path = /home/<username>/sambashare
     browseable = yes
     writable = yes
     guest ok = yes
     ```

4. **Herstart Samba**:
   - Herstart de Samba-service:
     ```bash
     sudo service smbd restart
     ```

5. **Toegang via Windows**:
   - Open de Verkenner op een Windows-machine en ga naar `\\<ip-adres-van-linux-machine>\sambashare` om de gedeelde map te openen.

---

## Oefening 4: Docker Container Maken en de Hello API Draaien

### Doel:
Stel een Docker-container in en draai de Hello-Node-API op poort 8000.

### Stappen:
1. **Installeer Docker**:
   - Installeer Docker op je Linux-systeem:
     ```bash
     sudo apt-get install docker.io
     ```

2. **Clone de Hello-Node-API repository**:
   - Clone de repository:
     ```bash
     git clone https://github.com/BioBoost/linux-essentials-docker-hello-node-api
     cd linux-essentials-docker-hello-node-api
     ```

3. **Bouw en draai de Docker-container**:
   - Bouw de Docker-image en draai de container:
     ```bash
     docker build -t hello-node-api .
     docker run -p 8000:8000 hello-node-api
     ```

4. **Toegang tot de API**:
   - Open een browser en ga naar `http://localhost:8000` om te controleren of de API werkt.

---

## Oefening 5: Node-RED Instellen op Docker

### Doel:
Gebruik Docker om Node-RED op te zetten en toegang te krijgen via een webinterface.

### Stappen:
1. **Draai de Node-RED Docker-container**:
   - Gebruik het volgende commando om Node-RED in een Docker-container te draaien:
     ```bash
     docker run -it -p 1880:1880 nodered/node-red
     ```

2. **Toegang tot Node-RED**:
   - Open een browser en ga naar `http://localhost:1880` om de Node-RED interface te openen.

---

## Uitdagingen

- ✅ **SSH Toegang**: Is SSH correct ingesteld en kun je verbinding maken?
- ✅ **SCP Bestanden Kopiëren**: Kun je bestanden overdragen tussen systemen?
- ✅ **Samba Gedeelde Map**: Heb je een gedeelde map ingesteld en is deze toegankelijk via Windows?
- ✅ **Docker Hello-API**: Werkt de Hello-Node-API op poort 8000?
- ✅ **Node-RED**: Draait Node-RED correct op Docker?

---

### Opmerkingen:
- Zorg ervoor dat je Docker werkt in WSL of een virtuele machine, afhankelijk van je omgeving.
- Gebruik de man-pages voor hulp bij specifieke commando's (`man <commando>`).
