<p align="center"><img src="merise.jpg"/></p>

<a href="./README.md">Retourner à la racine du repo</a>



# Méthodologie MERISE

> [!NOTE]
> La **Méthode MERISE** (Méthode d'Etude et de Réalisation Informatique pour les Systèmes d'Entreprise) a vu le jour à la fin des années 1970 en France dans le but de définir une démarche de conception des Systèmes d'Information par étapes

## Niveaux de Modélisation

La Méthode MERISE propose trois niveaux de modélisation :

### 1. Niveau Conceptuel

- **Modèle Conceptuel des Données (MCD):** Représentation du système d'information indépendamment de son aspect informatique. Ce modèle doit être compréhensible par un large public, incluant informaticiens, employés, secrétaires, et personnel de direction.

### 2. Niveau Logique

- **Modèle Logique des Données (MLD):** Représentation modélisée précédant l'implémentation dans le Système de Gestion de Base de Données Relationnelles (SGBDR). Il utilise deux représentations :
  - *Entité:* Regroupe l'information statique et durable. Par exemple, l'entité "EMPLOYE" rassemble toutes les informations communes aux employés d'une entreprise.
  - *Association:* Matérialise la dynamique du système en représentant les relations entre les entités. Par exemple, l'association entre "EMPLOYE" et "SERVICE" d'une entreprise.

### 3. Niveau Physique

- **Modèle Physique des Données (MPD):** Représentation modélisée précédant l'implémentation dans le SGBDR.

La Méthode MERISE offre ainsi une approche méthodique et structurée pour la conception des systèmes d'information, garantissant une cohérence entre les différents niveaux de modélisation.

[Pour en savoir plus cliquer ici](https://ineumann.developpez.com/tutoriels/merise/initiation-merise/)
