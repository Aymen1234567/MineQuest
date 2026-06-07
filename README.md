# MineQuest — Jeu d'Exploration en Java


---

## 📖 Description

**MineQuest** est un jeu d'exploration en mode console développé en Java. Le joueur navigue sur un plateau de salles cachées, ramasse des ressources, utilise des outils de détection et tente d'atteindre une sortie sans tomber sur une mine.

---

## 🎮 Règles du jeu

- Le joueur démarre au centre du plateau avec **10 grenades** et **20 unités d'énergie**.
- Chaque salle voisine est **fermée** : il faut lancer une grenade pour y accéder (sauf pour revenir en arrière).
- **Condition de victoire** : atteindre l'une des **4 sorties** situées dans les coins du plateau.
- **Conditions de défaite** :
  - Tomber sur une **mine** → mort immédiate.
  - Épuiser toutes ses **grenades** sans pouvoir avancer.

---

## ⚙️ Objets rencontrés dans les salles

| Objet | Effet |
|---|---|
| 💣 Mine (`*`) | Le joueur perd immédiatement |
| 🟩 Caisse de grenades (`G`) | Le joueur peut en ramasser jusqu'à son maximum |
| ⚡ Réserve d'énergie (`R`) | Le joueur peut récupérer de l'énergie |
| 🔧 Outil (`D` ou `S`) | Détecteur de mines ou Scanner unidirectionnel |
| 🚪 Sortie (`<<`) | Victoire ! |
| ░ Salle vide | Rien à faire ici |

---

## 🛠️ Outils disponibles

### Détecteur de mines (`D`)
- Indique le **nombre de mines** dans les 8 salles adjacentes.
- **Coût** : 2 unités d'énergie.

### Scanner unidirectionnel (`S`)
- Le joueur choisit une direction (`h`, `b`, `g`, `d`).
- Indique le nombre de salles vides dans cette direction (avec une marge d'erreur de ±20 %).
- **Coût** : 3 unités d'énergie.

---

## 🕹️ Commandes en jeu

```
1 — Avancer (choisir une direction : h=haut, b=bas, g=gauche, d=droite)
2 — Utiliser un outil
    1 — Scanner unidirectionnel
    2 — Détecteur de mines
```

---

## 🏗️ Architecture du projet

```
src/exploration/
├── Exploration.java          # Point d'entrée (main)
├── Jeu.java                  # Logique principale du jeu
├── Plateau.java              # Grille de jeu
├── Salle.java                # Représentation d'une salle
├── Position.java             # Coordonnées sur le plateau
├── Direction.java            # Enum des directions
├── Joueur.java               # État et actions du joueur
├── Objet.java                # Classe abstraite de base
├── SalleVide.java            # Salle sans contenu
├── Bordure.java              # Limite du plateau
├── Mine.java                 # Objet fatal
├── CaisseGrenades.java       # Réserve de grenades
├── ReserveEnergie.java       # Réserve d'énergie
├── Sortie.java               # Case de victoire
├── Outil.java                # Classe abstraite des outils
├── LesOutils.java            # Gestion de l'inventaire d'outils
├── DetecteurMines.java       # Outil de détection
├── ScannerUnidirectionnel.java # Outil de scan directionnel
├── DemoCategories.java       # Utilitaire de démonstration
└── Lire.java                 # Utilitaire de lecture clavier
```

---

## ▶️ Compilation et exécution

### Prérequis
- **Java JDK 8+**
- Ou **NetBeans IDE** (projet NetBeans inclus)

### Avec NetBeans
Ouvrir le dossier `Projet2024_base/` directement dans NetBeans et lancer le projet.

### En ligne de commande
```bash
# Compiler
javac -d build/classes src/exploration/*.java

# Lancer
java -cp build/classes exploration.Exploration
```

### Avec le JAR pré-compilé
```bash
java -jar dist/Projet2024_base.jar
```

---

## 👥 Auteurs

| Nom | Prénom |
|---|---|
| BERRAMDANI | Aymen |
| BOUAIA | Zineddine |

---

## 📄 Licence

Projet académique — tous droits réservés aux auteurs.
