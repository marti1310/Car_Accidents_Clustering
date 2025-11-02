#Clustering des accidents corporels de la circulation routière (France, 2023)

## Description du projet
Ce projet s’inscrit dans le cadre du module **Data Mining** du Master 2 Informatique – Parcours Data Science de l'Université Claude Bernard Lyon 1. 
L’objectif est de réaliser une **analyse de clustering** sur des données réelles issues du site [data.gouv.fr](https://www.data.gouv.fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2024/), concernant les **accidents corporels de la circulation routière en France en 2023**.

Le but est d’identifier des **profils types d’accidents** à partir de variables mixtes (numériques et catégorielles) et de comparer plusieurs approches de clustering :
- K-Means adapté avec distance mixte (Euclidienne + Hamming)  
- K-Modes (pour données catégorielles)  
- K-Prototypes (pour données mixtes)

---

## Données
Le dataset est composé de **quatre tables** :
- `caracteristiques.csv`
- `lieux.csv`
- `vehicules.csv`
- `usagers.csv`

Ces tables ont été nettoyées, fusionnées et transformées afin de construire un jeu de données exploitable pour le clustering.  
Les variables utilisées incluent notamment :
- `catv` : catégorie du véhicule  
- `manv` : manœuvre effectuée  
- `choc` : type de choc  
- `collision_vehicule_mb`, `collision_pieton`, `obstacle_fixe` : indicateurs de collision  
- `sexe`, `age`, `trajet`, `gravite_moyenne` : informations sur l’usager et la gravité des blessures  
- `vma` : vitesse maximale autorisée  
- `atm`, `lum`, `surf`, `int`, `agg`, `catr` : conditions de l’environnement  

Une variable dérivée `gravite_moyenne` a été créée pour agréger la gravité des blessures et obtenir une mesure ordonnée.

---

## Méthodologie
1. **Prétraitement des données**  
   - Nettoyage et harmonisation des valeurs manquantes  
   - Conversion des codes à `-1` en `NaN`  
   - Normalisation des variables continues  
   - Regroupement des modalités rares  
   - Création d’attributs binaires pour certaines variables (ex. collisions)

2. **Clustering**  
   - Application de K-Means adapté, K-Modes et K-Prototypes  
   - Sélection du nombre optimal de clusters via la méthode du coude et le score silhouette  
   - Analyse et interprétation des profils d’accidents obtenus

3. **Évaluation**  
   - Comparaison de la qualité des clusters (inertie, silhouette, robustesse)  
   - Analyse descriptive des variables clés dans chaque cluster  
   - Visualisations (PCA, distributions, cartes de densité)

---

## Résultats
Les modèles de clustering ont permis de distinguer **quatre grands profils d’accidents** selon les conditions environnementales, la gravité et le type d’usager.  
K-Modes s’est révélé le plus efficace sur nos données.

---

## Technologies utilisées
- **Python 3.x**
- **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**
- **Scikit-learn**, **kmodes**
- **Jupyter Notebook**

---

## Autrices
- **Martina AGÜERA SANCHEZ**   
- **Tamazgha SOUTOU** 

Master 2 Informatique – Parcours Data Science  
Université Claude Bernard Lyon 1 (2025–2026)
