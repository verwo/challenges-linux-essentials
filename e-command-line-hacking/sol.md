# Linux Redirection, Pipelines & Command Chaining

## Challenge Reeks

> Probeer de challenges op te lossen **zonder Google**. Gebruik de **man-pages** om de nodige info te vinden.
> Markeer met een ✅ wanneer afgewerkt.

---

### ✅ Output Redirection 1 – Basis

```bash
echo "Dit is regel 1" > output.txt
echo "Dit is regel 2" >> output.txt
echo "Dit is regel 3" >> output.txt
cat output.txt
```

---

### ✅ Input Redirection – Analyseer Bestand

```bash
wc < output.txt
wc output.txt
```

Beide geven hetzelfde resultaat, tenzij wc meerdere bestanden zou analyseren.

---

### ✅ Foutmelding Loggen – stderr

```bash
cat /etc/shadow 2> error.log
cat /root/secretfile 2>> error.log
cat error.log
```

---

### ✅ Alles Loggen – stdout + stderr

```bash
ls /nonexistent /etc >log.txt 2>&1
ls /nonexistent /etc &>log2.txt
cat log.txt
cat log2.txt
bash --version
```

`&>` is beschikbaar vanaf Bash 4.

---

### ✅ Redirect naar /dev/null – Onderdruk fouten

```bash
find / -name passwd 2>/dev/null
```

Aantal regels vermindert door foutmeldingen te onderdrukken.

---

### ✅ Pipeline 1 – Tel Items

```bash
ls -al /etc | wc -l
```

---

### ✅ Pipeline 2 – Filter Resultaten

```bash
ls -al /usr/bin | grep python | wc -l
```

Geeft aantal python-gerelateerde bestanden.

---

### ✅ Pipeline 3 – Woordenlijstbewerking

```bash
grep shell /usr/share/dict/words | sort -r | tail -n 1 | tr a-z A-Z | sed 's/LL/XX/g'
```

---

### ✅ Pipeline 4 – Gecombineerde Redirectie

```bash
find / -name bash -type d 2>/dev/null | wc -l
```

---

### ✅ Command Chaining 1 – Succes en Falen

```bash
mkdir project && cd project
false || echo "Mislukt, probeer opnieuw"
```

---

### ✅ Command Chaining 2 – Output verwerken

```bash
grep sshd /etc/passwd > sshd.txt
[ -s sshd.txt ] && echo "Gevonden" || echo "Niet gevonden"
```

---

### ✅ BONUS – Mix Alles!

```bash
ps aux | grep root | sort -nk4 > rootprocs.txt
cat rootprocs.txt | wc -l
```

---

### ✅ Klaar? Reflecteer:

* Welke operatoren heb je geleerd?
  `>`, `>>`, `2>`, `2>&1`, `&>`, `|`, `&&`, `||`, `<`
* Wat zou je nog willen oefenen?
  Complexe pipelines met `awk`, `xargs`, `tee`, `jq`...
