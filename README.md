
# Rénovation matérielle et optimisation sous Linux pour un Lenovo Ideapad 320 pour en faire un pc portable de cours

# 💻 Reconditionnement & Optimisation Linux — Lenovo IdeaPad 320

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
| **Stockage** | HDD 5400 RPM (SATA) | SSD 2.5" SATA | Démarrage en < 15s, accès disques instantanés |
| **Mémoire Vive (RAM)** | 4 Go DDR4 soudés | 8 Go (4 Go soudés + barrette SO-DIMM 4 Go) | Confort de multitâche, fin des saturations de Swap |
| **Batterie** | Batterie d'origine dégradée | Nouvelle batterie (cellules haute densité) | Capacité accrue pour un encombrement identique |
| **Refroidissement** | Pâte thermique asséchée | Nettoyage ventilateur + repaste thermique | Baisse des températures de 8-12°C en charge |

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

Mesure relevée sur batterie (luminosité ~40 %, Wi-Fi connecté, session de travail bureautique sous Debian 12) :

```text
native-path:          BAT0
vendor:               Green Cell
state:                discharging
energy-rate:          6.42 W
time to empty:        5.8 hours
percentage:           94%
```

![Capture upower en conditions réelles](docs/upower-metrics.png)
