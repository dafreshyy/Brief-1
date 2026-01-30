# Projet Tableau – Analyse des Données Commerciales

## Contexte du projet

Les entreprises génèrent quotidiennement de grandes quantités de données commerciales liées aux **ventes**, **retours**, **clients**, **produits** et à la **satisfaction client**.
L’exploitation de ces données permet de mieux comprendre la performance commerciale, d’identifier des tendances clés et d’appuyer la prise de décision stratégique.

Ce projet vise à transformer des données brutes en **analyses visuelles interactives**, à l’aide de **Tableau**, afin de fournir une vision claire et exploitable de l’activité commerciale.

---

## Objectifs du projet

* Importer et connecter plusieurs sources de données hétérogènes
* Nettoyer, structurer et préparer les données pour l’analyse
* Créer des **hiérarchies** et **regroupements de dimensions**
* Produire des **visualisations interactives variées**
* Mettre en place des **calculs, mesures et paramètres dynamiques**
* Construire un **dashboard final pertinent**, interactif et lisible

---

## Sources de données

Le projet s’appuie sur plusieurs sources de données commerciales, notamment :

* **Achats** : informations de ventes (montant, quantité, dates, produits)
* **Retours** : données liées aux retours produits
* **Évaluations** : notes et satisfaction client
* **Personnes** : informations clients / segments

---

## Logique de modélisation des données

### Jointures physiques

Les jointures suivantes ont été appliquées dans Tableau :

* `LEFT JOIN` : **Achats ↔ Évaluations**
* `LEFT JOIN` : **Achats ↔ Retours**
* `INNER JOIN` : **Achats ↔ Personnes**

Ces choix permettent de conserver l’ensemble des ventes, tout en intégrant les informations de satisfaction, de retour et de segmentation client.

### Relation logique

Une **relation logique** a été définie entre **Achats** et **Évaluations** afin de préserver la granularité des métriques au **niveau commande**, notamment pour le calcul de la satisfaction moyenne par commande.

---

## Hiérarchies et regroupements

### Hiérarchies créées

* **Produit** :
  `Catégorie → Sous-catégorie → Nom du produit`
* **Géographie** :
  `Pays → Région → Ville`

### Regroupements

* Regroupement personnalisé de la dimension **Sous-catégorie** afin de simplifier l’analyse et améliorer la lisibilité.

---

## Visualisations réalisées

### Visualisations de base

* Histogramme : **Ventes par sous-catégorie**
* Histogramme : **Ventes par segment**
* Quantité par **hiérarchie Produit**
* Satisfaction client par commande
* Évolution des ventes par date (jour / mois / année)

### Visualisations avancées

* Carte : **Ventes par pays / région**
* Graphique à bulles : **Ventes par segment**
* Graphique à axe double : **Ventes vs Quantité**
* Graphique miroir (multi-mesure)
* Matrice de graphiques (small multiples)
* Lignes de référence avec objectifs par partition

---

## Calculs et paramètres

### Champs calculés

* **% Profit / Ventes** : ratio du profit par rapport au montant des ventes
* **Éco-taxe (5 %)** :

  * Appliquée uniquement aux produits de catégorie technologique
  * Non appliquée aux produits identifiés comme recyclés via leur nom
* **Flag ventes faibles** :

  * Champ booléen (Vrai/Faux)
  * Ventes totales < 1000
  * Utilisé pour la mise en forme conditionnelle ou comme filtre

### Paramètre dynamique

* **% accroissement profit**

  * Paramètre utilisateur
  * Calcul d’un **profit ajusté** en fonction du pourcentage sélectionné

---

## Tableaux & reporting

* Tableau simple avec total des ventes
* Tableau multidimensionnel (lignes / colonnes multiples)
* Tableau croisé (pivot)
* Tableau multi-mesure
* Mise en forme conditionnelle (ex. ventes sous objectif en rouge)

---

## Dashboard final

Un **dashboard interactif** a été conçu à partir des visualisations les plus pertinentes :

* Filtres globaux et contextuels (Pays, Date, Segment, Quantité)
* Paramètres dynamiques accessibles à l’utilisateur
* Titres, légendes et couleurs cohérents
* Navigation fluide et lisibilité optimisée

---

## Instructions d’utilisation

1. Ouvrir le fichier **.twbx** dans Tableau Desktop / Tableau Public / Tableau Online
2. Utiliser les filtres pour explorer les données par :

   * Zone géographique
   * Segment client
   * Période
3. Ajuster le paramètre **% accroissement profit** pour simuler différents scénarios
4. Analyser les indicateurs clés via le dashboard interactif

---
