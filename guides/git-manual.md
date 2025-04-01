# 🧑‍💻 Git voor Beginners: Simpele Git-handleiding

Deze handleiding is bedoeld voor absolute beginners die willen starten met Git en GitHub. We gebruiken de terminal (command line) en GitHub om je code online op te slaan.

---

## 📦 Wat is Git?
Git is een versiebeheersysteem. Het helpt je om wijzigingen in bestanden bij te houden, samen te werken met anderen, en terug te keren naar vorige versies als iets misloopt.

Git werkt lokaal op je computer, maar je kunt je code ook online bewaren via GitHub.

---

## ⚙️ 1. Git installeren

Op Ubuntu (WSL of Linux):
```bash
sudo apt update
sudo apt install git
```

Op Windows/macOS: [https://git-scm.com/downloads](https://git-scm.com/downloads)

---

## 👤 2. Git instellen (éénmalig)

```bash
git config --global user.name "Jouw Naam"
git config --global user.email "jij@email.com"
```

---

## 📁 3. Een nieuwe Git-repository maken

```bash
mkdir mijn-project
cd mijn-project
git init
```

Nu wordt een verborgen `.git` map aangemaakt. Git volgt nu de veranderingen in deze map.

---

## ➕ 4. Bestanden toevoegen en committen

1. Maak een bestand aan:
```bash
echo "Hello world" > README.md
```

2. Voeg toe aan git:
```bash
git add README.md
```

3. Commit het:
```bash
git commit -m "Eerste commit"
```

---

## ☁️ 5. Verbind met GitHub

1. Maak een nieuwe (lege) repository op [https://github.com](https://github.com)

2. Koppel aan je lokale repo:
```bash
git remote add origin https://github.com/jouwgebruikersnaam/naam-van-je-repo.git
```

3. Hernoem de branch naar `main` (indien nodig):
```bash
git branch -m main
```

4. Push je code:
```bash
git push -u origin main
```

> ℹ️ GitHub gebruikt geen wachtwoorden meer voor HTTPS-verkeer. Gebruik in plaats daarvan een **Personal Access Token (PAT)**. 

Lees hier hoe je een token aanmaakt en gebruikt:
- [GitHub PAT Handleiding (lokaal document)](#)
- [Externe gids op GitHub](https://github.com/verwo/challenges-linux-essentials/blob/master/guides/configure-git.md)

---

## 🔄 6. Wijzigingen maken en opnieuw pushen

1. Maak wijzigingen in bestanden
2. Check de status:
```bash
git status
```
3. Voeg toe en commit opnieuw:
```bash
git add .
git commit -m "Beschrijving van je wijziging"
```
4. Push:
```bash
git push
```

---

## 🔁 7. Code ophalen van GitHub (pull)

Als iemand anders iets heeft gewijzigd, haal je die wijzigingen binnen:
```bash
git pull
```

---

## 🧽 8. Handige commando's

- `git log` → Toon de geschiedenis van commits
- `git diff` → Toon de verschillen tussen bestanden
- `git status` → Toon de huidige status
- `git clone URL` → Download een GitHub-repo

---

## 🎉 Klaar om te starten!
Je bent nu klaar om Git en GitHub te gebruiken voor je eigen projecten. Gewoon proberen is de beste manier om het te leren.