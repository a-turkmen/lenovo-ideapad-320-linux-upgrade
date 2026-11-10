
# Rénovation matérielle et optimisation sous Linux pour un Lenovo Ideapad 320 pour en faire un pc portable de cours

# 💻 Reconditionnement & Optimisation Linux — Lenovo IdeaPad 320 de 2017 (bientôt 10ans!!)

Projet personnel de valorisation matérielle et logicielle d'un ordinateur portable **Lenovo IdeaPad 320**, reconditionné en machine nomade pour la prise de notes et le travail universitaire en BUT Réseaux & Télécoms.

---

## 🎯 Objectifs du projet

- **Éco-responsabilité / Green IT (RSE?):** Prolonger la durée de vie d'un matériel vieillissant au lieu de le remplacer.
- **Réactivité système :** Éliminer les goulots d'étranglement matériels (disque mécanique, mémoire saturée).
- **Autonomie énergétique :** Maximiser l'autonomie sur batterie en environnement de mobilité (amphis, déplacements) via un OS Linux allégé et un réglage fin de la gestion d'énergie.

---
## Attentes de ce projet
  Une batterie haute capacité, changement de la batterie vieillissante par une batterie a nouvelle cellules de tailles réduites mais à plus grande capacité 

## 🛠️ Modifications Matérielles (Hardware)

| Composant | Configuration d'origine | Configuration après mise à niveau | Bénéfice constaté |
| :--- | :--- | :--- | :--- |
| **Stockage** | Disque dur classique | SSD 2.5" SATA (4 à 5x plus rapide) | Démarrage en < 15s, accès disques instantanés |
| **Mémoire Vive (RAM)** | 4 Go DDR4 soudés | 8 Go (4 Go soudés + barrette SO-DIMM 4 Go) | Confort de multitâche, fin des saturations de Swap |
| **Batterie** | Batterie d'origine dégradée | Nouvelle batterie (cellules haute densité) | Capacité accrue pour un encombrement identique |
| **Refroidissement** | Résidus de pâte thermique seulement | Nettoyage ventilateur + repaste thermique | Baisse des températures de 8-12°C en charge |

---

## 🐧 Configuration Système & Optimisation (`TLP`)

### 1. Choix du système d'exploitation
- **Distribution :** Debian 12
- **Environnement de bureau :** XFCE
- **Avantages :** Consommation RAM au repos inférieure à 800 Mo, empreinte CPU minimale.

### 2. Gestion énergétique avancée avec TLP
Installation du démon d'optimisation d'énergie :
```bash
sudo apt update && sudo apt install tlp tlp-rdw
sudo systemctl enable --now tlp
```
---

## 📊 Métriques énergétiques réelles (`upower`)

Mesure relevée sur batterie (luminosité ~60 %, Wi-Fi connecté (2,4GHz), Bluetooth connecté (clavier externe sans-fils) session de travail bureautique classique sous Debian 13 XFCE : Navigateur avec 4 pages d'ouvertes, BitWarden, 2 terminaux) :

```text
native-path:          BAT0
vendor:               SMP
state:                discharging
energy-rate:          8,021 W
time to empty:        5.9 hours
percentage:           96%
```

![Capture upower en conditions réelles](docs/upower-metrics.png)
