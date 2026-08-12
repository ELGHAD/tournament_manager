# Tournament Manager — Gestion de Tournoi Sportif (C++)

> Application console en C++ orientée objet pour gérer un tournoi sportif de bout en bout : équipes, arbitres, terrains, matchs et classement.

![C++](https://img.shields.io/badge/C%2B%2B-20-00599C?style=flat&logo=cplusplus&logoColor=white)
![CMake](https://img.shields.io/badge/Build-CMake-064F8C?style=flat&logo=cmake&logoColor=white)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-blue)
![License](https://img.shields.io/badge/License-Not%20specified-lightgrey)

## Aperçu du projet

Ce projet implémente un système de gestion de tournoi sportif en ligne de commande, développé en C++20 selon les principes de la programmation orientée objet (encapsulation, séparation interface/implémentation). Il permet de configurer un tournoi, d'y inscrire des équipes et des arbitres, de réserver des terrains, puis de générer et suivre les matchs (phase de groupes et phase éliminatoire) jusqu'au classement final.

Il s'adresse aux recruteurs et développeurs souhaitant évaluer une modélisation orientée objet propre en C++ (classes métier découplées, gestion de la mémoire avec pointeurs, algorithmes de tri et de recherche) plutôt qu'une application graphique ou web.

## Fonctionnalités clés

- **Configuration du tournoi** — nom, date, nombre maximum d'équipes, validation des prérequis avant démarrage (équipes, arbitres, terrains).
- **Gestion des équipes** — ajout, consultation, recherche multi-critères (id, nom, ville, score, classement), contrainte métier (minimum 20 joueurs par équipe).
- **Gestion des arbitres** — inscription, recherche par code, historique des décisions arbitrales.
- **Gestion des terrains** — enregistrement (nom, ville, propriétaire, capacité) et recherche multi-critères.
- **Gestion des matchs** — création aléatoire ou planifiée, phases multiples (groupes, éliminatoires, quarts, demi-finale, finale), enregistrement des scores.
- **Classement automatique** — attribution des points (victoire/nul) et tri dynamique des équipes après chaque résultat.
- **Planification** — répartition automatique en groupes de 4 équipes avec bascule directe en phase éliminatoire si moins de 8 équipes inscrites.

## Architecture & Stack technique

| Élément | Détail |
|---|---|
| **Langage** | C++20 |
| **Build system** | CMake (3.29+) |
| **Paradigme** | Programmation orientée objet (classes, encapsulation, séparation `.h` / `.cpp`) |
| **Structures de données** | `std::vector`, pointeurs bruts pour les entités dynamiques (`Match*`) |
| **Gestion mémoire** | Allocation dynamique des matchs avec libération explicite dans le destructeur de `Tournoi` |

**Classes principales :**

| Classe | Responsabilité |
|---|---|
| `Tournoi` | Orchestration globale : équipes, arbitres, terrains, matchs, classement |
| `Equipe` | Représentation d'une équipe (score, classement, effectif) |
| `Arbitre` | Représentation d'un arbitre et de ses décisions |
| `Terrain` | Représentation d'un terrain (ville, propriétaire, capacité) |
| `Match` | Un match donné : équipes, arbitre, terrain, score, phase |

## Installation & Démarrage rapide

### Prérequis
- Un compilateur compatible C++20 (GCC, Clang ou MSVC)
- CMake 3.29 ou supérieur

### Compilation

```bash
git clone https://github.com/ELGHAD/Chess-tournament.git
cd Chess-tournament

mkdir build && cd build
cmake ..
cmake --build .
```

### Exécution

```bash
./gestionTournoi        # Linux / macOS
gestionTournoi.exe      # Windows
```

Le programme lance un menu interactif en console permettant de configurer le tournoi, gérer les équipes/arbitres/terrains, puis créer et suivre les matchs.

## Structure du projet
