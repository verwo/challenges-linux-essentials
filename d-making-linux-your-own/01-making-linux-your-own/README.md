Making Linux Your Own (WSL)

> Probeer de challenges op te lossen **zonder Google**. Gebruik de **man-pages** om de nodige info te vinden.  
> Markeer met een ✅ wanneer afgewerkt. Je werkt in **WSL (Windows Subsystem for Linux)**.

---

## ❌ Dotfiles
*Setup your own dotfiles. Make the repo public (GitHub).*  
Tip: gebruik `git init` in een map `dotfiles`.

---

## ❌ Installation Script
*Create an installation script for the tools and libraries you use most (bv. git, curl, build-essential...). Add the script to your dotfiles.*  
Test het script met `chmod +x` en `./scripts/wsl`.

---

## ❌ Neofetch
*Voeg `neofetch` toe aan je install script.*  
Laat `neofetch` automatisch starten in je terminal via `.bashrc` of `.zshrc`.

---

## ❌ Zsh + Oh My Zsh
*Installeer `zsh` en `oh-my-zsh`. Zet `zsh` als standaard shell met `chsh`. Configureer een thema naar keuze in `.zshrc`.*

---

## ❌ Aliassen
*Voeg **2 aliassen** toe aan `.zshrc` of `.bashrc`.*  
- Eén alias toont nuttige info (bv. "welke shell gebruik ik?")  
- Eén alias maakt een bestaande opdracht korter (bv. `ll` voor `ls -lh`).

---

## ❌ Random Theme
*Configureer `Oh My Zsh` om bij elke nieuwe terminal een **willekeurig thema** te kiezen uit minstens 3 eigen gekozen thema's.*

---

## ❌ Backup je dotfiles
*Push je dotfiles naar GitHub. Test de installatie op een andere WSL-machine (of herinstalleer in je huidige WSL). Gebruik je installatieprocedure.*

---

## ❌ Dotbot Setup
*Gebruik `Dotbot` om **minstens 2 configbestanden** te beheren via symlinks.*  
Voorbeelden: `~/.gitconfig`, `~/.bashrc`, `~/.zshrc`.  
Test of Dotbot correct werkt met `./install`.

---

## ❌ Script voor WSL
*Maak een script `scripts/wsl` dat automatisch tools installeert: bv. git, curl, node, ...*  
Gebruik een interactieve `pause` functie:  
```bash
function pause() {
  read -p "$* [ENTER]"
}
```
---

## ❌ Bonus: DRY Principle
*Maak een script scripts/common voor gedeelde installaties. Roep dit script aan vanuit `scripts/wsl`. DRY = Don't Repeat Yourself.*

✅ Klaar? Reflecteer:
- Wat heb je geautomatiseerd?
- Wat zou je nog willen verbeteren aan je WSL setup?
- Zou je deze aanpak ook op een echte Linux server kunnen toepassen?