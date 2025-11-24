# Projet – Big Data  


Analyse et visualisation de données AIS (Automatic Identification System) de navires dans le golfe du Mexique.

## Objectif
Créer une application complète d’exploration, nettoyage, visualisation et prédiction à partir du jeu de données vessel-total-clean.csv.

## Fonctionnalités implémentées (R – RMarkdown)

1. **Exploration & Nettoyage**  
   – Statistiques descriptives (longueur, largeur, vitesse, etc.)  
   – Nettoyage : suppression des NA, outliers (vitesse > 30 nœuds, dimensions nulles), hors zone  
   – Boîtes à moustaches avant/après

2. **Visualisations graphiques** (ggplot2)  
   – Camembert répartition des types de navires  
   – Histogrammes : longueurs, types de cargo, ports les plus fréquentés  
   → Tous les graphiques exportés en PNG

3. **Cartes interactives** (leaflet + shiny)  
   – Trajectoires individuelles ou globales  
   – Application Shiny : choisir un bateau par nom → affiche sa trajectoire  
   – Routes principales (10 % des bateaux les plus observés en rouge)  
   – Bonus : détection cargos pleins/vides via le tirant d’eau

4. **Corrélations**  
   – Matrice de corrélation + corrplot  
   – Tableaux croisés, tests du χ² et mosaicplots (VesselType ↔ Status, Cargo, etc.)

5. **Prédiction**  
   – Régression logistique multinomiale : prédiction de VesselType  
   – Régression linéaire : prédiction de la vitesse (SOG) + RMSE  
   – Export du dataset nettoyé → export_IA.csv

## Technologies
- R (dplyr, ggplot2, leaflet, shiny, nnet, caret, corrplot, vcd, …)
- RMarkdown (projet_BigData.Rmd) → compile en HTML/PDF

## Comment exécuter
1. Installer R et RStudio.
2. Installer les packages via install.packages(c("readxl", "ggplot2", "leaflet", "dplyr", "corrplot", "vcd", "shiny", "nnet", "caret", "mapview", "RColorBrewer")).
3. Placer vessel-total-clean.csv.xlsx dans le chemin indiqué dans le script  
4. Ouvrir projet_BigData.Rmd dans RStudio  
5. Knit ou exécuter les chunks → graphiques, cartes et modèles générés automatiquement

## Contenu du dépôt
- projet_BigData.Rmd – tout le code commenté  
- vessel-total-clean.csv.xlsx - fichier des données  
- data-dictionary
- vesselType.txt
- VesselTypeCodes2018
- Developpement_BigData_Projet_A3_AIS_Brest (1) - sujet qui contient tout les fonctionnalité
