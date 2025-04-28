# Basic Shell Scripting

Los de uitdagingen op door kleine bash-scripts te maken. Plaats de bash-scripts hier voor elke uitdaging. Zorg ervoor dat je enkele opmerkingen toevoegt en uitlegt hoe ze werken.

Markeer de uitdagingen met een ✅ zodra ze zijn voltooid.

## Je Eerste Shell Script

### Doel:
Maak een eenvoudig shell script dat "Hello, World!" afdrukt.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Open je WSL-terminal en navigeer naar je werkdirectory:
     ```bash
     cd ~
     touch hello_world.sh
     chmod +x hello_world.sh
     ```

2. **Schrijf het script**:
   - Open het bestand in een teksteditor zoals `nano` en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash
     echo "Hello, World!"
     ```

3. **Voer het script uit**:
   - Run het script:
     ```bash
     ./hello_world.sh
     ```

4. **Controleer de uitvoer**:
   - Het script moet "Hello, World!" afdrukken.

---

## Variabelen Gebruiken

### Doel:
Maak een script dat een variabele gebruikt om de naam van de gebruiker op te slaan en vervolgens een begroeting uitvoert.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Maak een nieuw scriptbestand genaamd `greet_user.sh`:
     ```bash
     touch greet_user.sh
     chmod +x greet_user.sh
     ```

2. **Schrijf het script**:
   - Open het bestand en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash
     username="Student"
     echo "Hallo, $username!"
     ```

3. **Voer het script uit**:
   - Run het script:
     ```bash
     ./greet_user.sh
     ```

4. **Verander de waarde van de variabele**:
   - Wijzig de waarde van de `username` variabele en herhaal de stap om de begroeting te wijzigen.

---

## Gebruikersinvoer Lezen

### Doel:
Maak een script dat de gebruiker vraagt om hun naam in te voeren en hen begroet.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Maak een nieuw scriptbestand genaamd `ask_name.sh`:
     ```bash
     touch ask_name.sh
     chmod +x ask_name.sh
     ```

2. **Schrijf het script**:
   - Open het bestand en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash
     echo "Wat is je naam?"
     read name
     echo "Hallo, $name!"
     ```

3. **Voer het script uit**:
   - Run het script en voer je naam in wanneer daarom wordt gevraagd:
     ```bash
     ./ask_name.sh
     ```

---

## Condities en If-Statements

### Doel:
Maak een script dat controleert of een opgegeven bestand bestaat en een bericht afdrukt afhankelijk van de uitkomst.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Maak een nieuw scriptbestand genaamd `check_file.sh`:
     ```bash
     touch check_file.sh
     chmod +x check_file.sh
     ```

2. **Schrijf het script**:
   - Open het bestand en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash
     echo "Voer de bestandsnaam in:"
     read filename
     
     if [ -f "$filename" ]; then
         echo "Het bestand $filename bestaat!"
     else
         echo "Het bestand $filename bestaat niet."
     fi
     ```

3. **Voer het script uit**:
   - Run het script en geef de naam van een bestand op wanneer daarom wordt gevraagd:
     ```bash
     ./check_file.sh
     ```

4. **Test met verschillende bestandsnamen**:
   - Test het script met bestandsnamen die wel en niet bestaan om te controleren of de juiste boodschap wordt weergegeven.

---

## Loop door Bestanden in een Map

### Doel:
Maak een script dat door alle bestanden in een map loopt en de naam van elk bestand afdrukt.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Maak een nieuw scriptbestand genaamd `list_files.sh`:
     ```bash
     touch list_files.sh
     chmod +x list_files.sh
     ```

2. **Schrijf het script**:
   - Open het bestand en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash
     echo "Geef een pad naar een directory op:"
     read dirpath

     if [ -d "$dirpath" ]; then
         for file in "$dirpath"/*; do
             echo "Bestand: $file"
         done
     else
         echo "Het opgegeven pad is geen geldige directory."
     fi
     ```

3. **Voer het script uit**:
   - Run het script en geef een pad naar een directory op:
     ```bash
     ./list_files.sh
     ```

4. **Test het script met verschillende directories**:
   - Test het script door een bestaande directory in te voeren en te controleren of alle bestanden correct worden weergegeven.

---

## Het Gebruik van Functies

### Doel:
Maak een script dat een functie definieert om twee getallen op te tellen en de som af te drukken.

### Stappen:
1. **Maak een nieuw scriptbestand aan**:
   - Maak een nieuw scriptbestand genaamd `sum_numbers.sh`:
     ```bash
     touch sum_numbers.sh
     chmod +x sum_numbers.sh
     ```

2. **Schrijf het script**:
   - Open het bestand en voeg de volgende inhoud toe:
     ```bash
     #!/usr/bin/env bash

     sum() {
         result=$(( $1 + $2 ))
         echo "De som van $1 en $2 is $result"
     }

     echo "Geef het eerste getal in:"
     read num1
     echo "Geef het tweede getal in:"
     read num2

     sum $num1 $num2
     ```

3. **Voer het script uit**:
   - Run het script en voer twee getallen in om hun som te berekenen:
     ```bash
     ./sum_numbers.sh
     ```

---


## ❌ Log de Datum

Maak een script dat de datum elke 10 seconden afdrukt. Gebruik het sleep-commando om te wachten tussen de aanroepen van het date-commando.

## ❌ Beschikbaar Geheugen
Toon het beschikbare systeemgeheugen samen met de huidige datum in het volgende formaat:

```
[Thu 14 May 2020 11:12:55 AM CEST] MemAvailable:   28439572 kB
```

*The available memory can be found in the file `/proc/meminfo`. Use the `grep` tool to filter out the line with MemAvailable.*

## ❌ Fetching Github Keys

Het Ophalen van Github Sleutels
Maak een script dat de openbare SSH-sleutels van een gebruiker op GitHub ophaalt en deze in de terminal weergeeft. Dit kan worden gedaan door het curl-commando te gebruiken om toegang te krijgen tot het eindpunt https://github.com/<username>.keys, waarbij <username> een bestaande GitHub-gebruikersnaam is.

Neem de gebruikersnaam via de commandoregelargumenten. Als er geen gebruikersnaam wordt opgegeven, vraag het dan aan de gebruiker met het read-commando.

Voorbeeld via de commandoregel:

```bash
./githubkeys bioboost
```

*or via the read command:*

```bash
./githubkeys
Please enter GitHub username: BioBoost
Fetching Keys
...
```



