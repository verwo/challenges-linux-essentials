# Remote Access - Oefeningen

## Inleiding
Deze oefeningen zijn bedoeld om je vertrouwd te maken met verschillende manieren van toegang tot een Linux-systeem op afstand, het gebruik van SCP voor bestandsoverdracht, het delen van mappen met Samba, en het opzetten van Docker-containers.


## ❌ SSH Toegang Instellen

Stel een SSH-server in op een Linux-systeem en test de verbinding vanaf een andere machine.

## ❌ Bestanden Overdragen met SCP

Gebruik SCP om bestanden te kopiëren tussen een lokale machine en een remote machine.

## ❌ Een Gedeelde Map Instellen met Samba

Stel een gedeelde map in op een Linux-systeem en verbind deze met een Windows-machine.

## ❌  Docker Container Maken en de Hello API Draaien

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


## ❌  Node-RED Instellen op Docker

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

### Opmerkingen:
- Zorg ervoor dat je Docker werkt in WSL of een virtuele machine, afhankelijk van je omgeving.
- Gebruik de man-pages voor hulp bij specifieke commando's (`man <commando>`).
