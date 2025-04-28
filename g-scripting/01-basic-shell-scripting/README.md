# Basic Shell Scripting

Los de uitdagingen op door kleine bash-scripts te maken. Plaats de bash-scripts hier voor elke uitdaging. Zorg ervoor dat je enkele opmerkingen toevoegt en uitlegt hoe ze werken.

Markeer de uitdagingen met een ✅ zodra ze zijn voltooid.

## ❌ Je Eerste Shell Script

Maak een eenvoudig shell script dat "Hello, World!" afdrukt.

## ❌ Variabelen Gebruiken

Maak een script dat een variabele gebruikt om de naam van de gebruiker op te slaan en vervolgens een begroeting uitvoert.

## ❌ Gebruikersinvoer Lezen

Maak een script dat de gebruiker vraagt om hun naam in te voeren en hen begroet.

## ❌ Condities en If-Statements

Maak een script dat controleert of een opgegeven bestand bestaat en een bericht afdrukt afhankelijk van de uitkomst.


## ❌ Loop door Bestanden in een Map

Maak een script dat door alle bestanden in een map loopt en de naam van elk bestand afdrukt.


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



