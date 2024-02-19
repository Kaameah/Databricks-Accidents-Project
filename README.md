# Databricks-Accidents-Project

### Projet : Prédiction des Gravités d'Accidents Routiers

#### Introduction
   - Objectif du projet : Prédire la gravité des accidents routiers en utilisant des modèles d'apprentissage automatique.
   - Importance du sujet : Réduire le nombre d'accidents graves en identifiant les facteurs de risque.

#### Sources des Données
   - Les données proviennent de [data.gouv.fr](https://www.data.gouv.fr/fr/)

Dans ce projet, nous disposons de quatre fichiers distincts disponible [ici](https://github.com/asardell/IUT_SD3/tree/main/data):

- **carac.csv :** Fournit des caractéristiques détaillées sur les accidents.
- **lieux.csv :** Recense des informations sur les lieux où les accidents ont eu lieu.
- **veh.csv :** Contient des données spécifiques sur les véhicules impliqués dans les accidents.
- **vict.csv :** Offre des informations détaillées sur les victimes des accidents.

Plus précisément, pour chaque victime, la gravité de l'accident est indiquée sur une échelle de 1 à 4, selon les catégories suivantes :

- **1 :** Indemne
- **2 :** Tué
- **3 :** Hospitalisé
- **4 :** Blessé léger

### Repository GitHub

Dans mon repository vous trouverez deux notebooks Databricks au format dbc.

Le premier **'Modelisation'** comprend les étapes ci-dessous

#### 1. Traitement des Données
   - Nettoyage des données : Gestion des valeurs manquantes, suppression des variables inutiles, etc.

#### 2. Modélisation
   - Choix des modèles : KNeighborsClassifier, DecisionTreeClassifier, RandomForestClassifier.
   - Optimisation des hyperparamètres avec GridSearchCV.
   - Entraînement des modèles sur l'échantillon d'entraînement.

#### 3. Évaluation des Modèles
   - Mesures de performance : Accuracy et F1-score
   - Comparaison des performances des modèles.
   - Sélection du meilleur modèle.

#### 4. Enregistrement du Modèle
   - Utilisation de MLflow pour enregistrer le modèle retenu.
   - Génération de signatures pour les entrées/sorties du modèle.

#### 5. Déploiement
   - Mise en place d'un endpoint pour le modèle déployé.

### Modèle Retenu et Performances

Le modèle retenu est le RandomForestClassifier avec les hyperparamètres optimisés. Les performances du modèle sur l'échantillon de test sont les suivantes :
   - Accuracy : 64,4%
   - F1-score : 44,4%

### Lien de l'Endpoint du Modèle
  - https://adb-4469819661100542.2.azuredatabricks.net/serving-endpoints/BestModel/invocations
  
Le second repository **'Test API'** permet de tester le modèle créé (BestModel) avec des exemples d'accidents.
