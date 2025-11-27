# 📄 Report — Construire le rapport Latex

Ce répertoire contient le rapport LaTeX du projet (attaques Wi-Fi — Télécom Sud Paris).
L’objectif ici est de documenter **comment compiler et obtenir un rendu PDF avec live reload**.

---

## 🐳 Compilation avec Docker + Makefile

### ⚙️ Build manuel

```bash
make
```

### 🔄 Mode watch (recompile automatiquement à chaque sauvegarde)

```bash
make watch
```

Le PDF est généré dans `report/main.pdf`.

> 💡 Le mode *watch* ne recharge pas le PDF tout seul : utilisez un lecteur compatible auto-reload (ci-dessous).

---

## 🔥 Live Reload du PDF

### 🔧 Logiciels recommandés selon votre OS

| OS          | Logiciel                  | Auto-refresh  |
| ----------- | ------------------------- | ------------- |
| **Linux**   | Evince / Okular / Zathura | ✔ automatique |
| **macOS**   | Skim                      | ✔ automatique |
| **Windows** | SumatraPDF                | ✔ automatique |
| **VSCode**  | LaTeX Workshop extension  | ✔ automatique |

### Exemple d’ouverture avec auto-refresh

Linux :

```bash
evince main.pdf &
```

macOS :

```bash
open -a Skim main.pdf
```

Windows :

```bash
start SumatraPDF.exe main.pdf
```

VSCode :

* Installer l’extension **LaTeX Workshop**
* Ouvrir `main.pdf` $\rightarrow$ le refresh automatique fonctionne dès `make watch`

---

## 📁 Structure attendue

```
report/
 ├── main.tex
 ├── Makefile
 ├── docker-compose.yml
 ├── bib/
 └── main.pdf   (généré)
```

---

## 🧪 Commandes utiles

```bash
make clean        # supprimer fichiers auxiliaires
make clean-all    # reset complet
```

---

## 🚀 GitHub Actions

Un pipeline compile automatiquement le PDF à chaque **push** et le publie dans les artifacts.

Voir `.github/workflows/latex.yml` pour les détails.