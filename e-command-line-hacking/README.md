# Linux Redirection, Pipelines & Command Chaining

## Challenge Reeks
> Probeer de challenges op te lossen **zonder Google**. Gebruik de **man-pages** om de nodige info te vinden.  
> Markeer met een ✅ wanneer afgewerkt. Werkduur: **30–40 minuten**.

---

### ❌ Output Redirection 1 – Basis
- Gebruik `echo` om **drie regels** tekst toe te voegen aan een bestand `output.txt`.  
  - Eerste regel: met `>` (overschrijven)  
  - Tweede & derde regel: met `>>` (append)
- Bekijk het resultaat met `cat`.

---

### ❌ Input Redirection – Analyseer Bestand
- Gebruik `wc < output.txt` om regels, woorden, tekens te tellen.  
- Vergelijk met `wc output.txt`. Zijn de resultaten gelijk?

---

### ❌ Foutmelding Loggen – stderr
- Gebruik `cat` op een bestand waar je **geen toegang** toe hebt (`/etc/shadow`).  
- Redirect de foutmelding naar `error.log` met `2>`.  
- Voeg een tweede fout toe via `>>error.log`. Bekijk inhoud.

---

### ❌ Alles Loggen – stdout + stderr
- Combineer stdout en stderr in één bestand:  
  - Gebruik `ls /nonexistent /etc >log.txt 2>&1`  
  - Probeer opnieuw met `&>log2.txt`  
  - Bekijk verschillen in inhoud. Welke Bash-versie heb je?

---

### ❌ Redirect naar /dev/null – Onderdruk fouten
- Zoek met `find / -name passwd`  
- Voorkom foutmeldingen door alles van stderr naar `/dev/null` te sturen.  
- Hoeveel resultaten zie je nu?

---

### ❌ Pipeline 1 – Tel Items
- Gebruik `ls -al /etc | wc -l` om te tellen hoeveel items in `/etc` staan.

---

### ❌ Pipeline 2 – Filter Resultaten
- Zoek met `ls -al /usr/bin | grep python`.  
- Tel het aantal regels met `wc -l`. Hoeveel python-gerelateerde bestanden vind je?

---

### ❌ Pipeline 3 – Woordenlijstbewerking
- Gebruik `/usr/share/dict/words`.  
- Zoek woorden met "shell" → sorteer omgekeerd → toon laatste regel → zet in hoofdletters → vervang "LL" met "XX" via `sed`.

---

### ❌ Pipeline 4 – Gecombineerde Redirectie
- Zoek naar een directory genaamd "bash" in `/`, onderdruk fouten, en tel resultaten. Gebruik:  
  ```bash
  find / -name bash -type d 2>/dev/null | wc -l


### ❌  Command Chaining 1 – Succes en Falen
- Gebruik chaining om:
    - Een directory `project` te maken én erin te navigeren met &&.
    - Probeer `false || echo "Mislukt, probeer opnieuw"`

### ❌  Command Chaining 2 – Output verwerken
- Zoek naar "sshd" in `/etc/passwd` en schrijf resultaat naar `sshd.txt`.
- Indien bestand niet leeg is, toon "Gevonden", anders "Niet gevonden"
(hint: `test -s` of `[ -s sshd.txt ]`)

### ❌  BONUS – Mix Alles!
- Schrijf één commandoreeks die:
    - Lijst alle processen (`ps aux`)
    - Filter op "root"
    - Sorteer op geheugengebruik
    - Bewaar resultaat in `rootprocs.txt`
    - Tel het aantal lijnen, toon enkel het getal.

### ✅ Klaar? Reflecteer:
- Welke operatoren heb je geleerd?
- Wat zou je nog willen oefenen?