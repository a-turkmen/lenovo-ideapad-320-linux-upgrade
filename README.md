
# Rénovation matérielle et optimisation sous Linux pour un Lenovo Ideapad 320 pour en faire un pc portable de cours

# 💻 Reconditionnement & Optimisation Linux — Lenovo IdeaPad 320 de 2017 (bientôt 10ans!!)

Projet personnel de valorisation matérielle et logicielle d'un ordinateur portable **Lenovo IdeaPad 320**, reconditionné en machine nomade pour la prise de notes et le travail universitaire en BUT Réseaux & Télécoms.

---

## 🎯 Objectifs du projet

- **Éco-responsabilité / Green IT (RSE?):** Prolonger la durée de vie d'un matériel vieillissant au lieu de le remplacer.
- **Réactivité système :** Supprimer les lenteurs au démarrage et les blocages quand plusieurs fenêtres sont ouvertes en même temps.
- **Autonomie énergétique :** Maximiser l'autonomie sur batterie en environnement de mobilité (amphis, déplacements) via un OS Linux allégé et un réglage fin de la gestion d'énergie.

---
## Attentes de ce projet
  Ce projet s'est étalé sur plusieurs années, mes attentes envers ce pc ont évolué au fil des années, tout d'abord je voulais plus de RAM (ce qui fluidifie l'usage bureautique notamment en lancant des logiciels plus rapidement et un démarrage de la machine plus rapide), puis j'ai voulu plus de stockage et des transferts rapide (j'ai changé mon disque dur en un SSD) et aujourd'hui il me faut plus d'autonomie pour avoir un pc qui tient une matinée en amphi, donc j'ai changé ma batterie vieillissante et optimisé la consommation via des outils Linux.
  
## 🛠️ Les améliorations matérielles (Ce qui a été changé dans le PC)

| Composant | Avant (Origine) | Après (Modernisation) | Ce que ça change au quotidien |
| :--- | :--- | :--- | :--- |
| **Stockage** | Disque dur mécanique classique (lent) | **Disque SSD** (4 à 5 fois plus rapide, sans pièces mobiles) | L'ordinateur démarre en moins de 15 secondes et les logiciels s'ouvrent instantanément. |
| **Mémoire Vive (RAM)** | 4 Go (mémoire intégrée d'origine) | **8 Go** (ajout d'une barrette mémoire de 4 Go) | Plus de blocages quand j'ouvre de nombreux onglets internet et logiciels en même temps. |
| **Batterie** | Batterie d'origine usée | **Batterie neuve haute capacité** | Grâce aux technologies récentes plus compactes, elle stocke plus d'énergie dans exactement le même espace. |
| **Refroidissement** | Poussière accumulée et pâte thermique sèche | **Nettoyage complet** et application d'une pâte thermique neuve | Le processeur chauffe beaucoup moins (-8 à -12 °C) et le ventilateur reste silencieux en cours. |

---
## Batterie

Grâce aux progrès des batteries récentes, j'ai pu intégrer une batterie qui stocke plus d'énergie tout en gardant exactement la même taille.

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

La consommation tombe autour de 8 W, ce qui permet de tenir une matinée entière de cours sans chargeur. 
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
