# 🔐 GitHub Personal Access Token (PAT) Instellen

GitHub laat sinds 2021 **geen wachtwoord-authenticatie via HTTPS** meer toe. In plaats daarvan moet je een **Personal Access Token (PAT)** gebruiken.

Deze handleiding legt stap voor stap uit hoe je een token aanmaakt en gebruikt.

---

## ✅ Waarom een Personal Access Token?

Een PAT vervangt je GitHub-wachtwoord wanneer je via HTTPS werkt (bv. `git push`, `git pull`, enz.).

---

## 🧱 Stap 1: Open je GitHub-profiel

1. Ga naar [https://github.com/login](https://github.com/login) en log in
2. Klik rechtsboven op je profielfoto
3. Kies **Settings**

---

## 🛠️ Stap 2: Ga naar Developer Settings

1. Scroll in het menu links naar beneden
2. Klik op **Developer settings**
3. Klik op **Personal access tokens**  
4. Kies **Tokens (classic)**
5. Klik op **Generate new token (classic)**

Of rechtstreeks via:  
👉 [https://github.com/settings/tokens](https://github.com/settings/tokens)

---

## ✍️ Stap 3: Stel je token in

- **Note:** Geef het een herkenbare naam, bv. `dotfiles-wsl`
- **Expiration:** Kies een vervaldatum (90 dagen of 'No expiration' voor testgebruik)
- **Scopes (rechten):**  
  - Vink minstens **`repo`** aan (toegang tot je eigen repositories)

Klik op **Generate token**.

---

## ⚠️ Stap 4: Kopieer je token

> 🔴 **BELANGRIJK:** Je ziet je token **maar één keer**.

- Klik op het kopieericoon
- Plak het ergens veilig (bv. wachtwoordmanager)

---

## 💻 Stap 5: Gebruik je token in Git

Wanneer je `git push` of `git pull` uitvoert:

- **Gebruikersnaam:** jouw GitHub-gebruikersnaam
- **Wachtwoord:** plak je token

Voorbeeld:
```bash
git push origin main
```
Git zal dan vragen:
```
Username: jouwgebruikersnaam
Password: plak-hier-je-token
```

---

## 🧠 Extra: Token opslaan (optioneel)

Zodat je Git het onthoudt:

```bash
git config --global credential.helper store
```

De eerste keer geef je je token in, daarna wordt het onthouden in `~/.git-credentials`.

---

## 🔀 Token verwijderen

Wil je de opgeslagen token verwijderen?

```bash
git credential reject
```

Typ daarna:
```
protocol=https
host=github.com
```

Druk op Enter.

---

## 🎉 Klaar!

Je kunt nu veilig werken met GitHub via HTTPS met je eigen Personal Access Token.
