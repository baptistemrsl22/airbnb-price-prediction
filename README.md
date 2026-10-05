# Prédiction du prix de logements Airbnb

Projet de Machine Learning réalisé dans le cadre de ma formation Data & IA à l'ESILV.

L'objectif est de prédire le prix de logements Airbnb à partir des caractéristiques des annonces, des hôtes, des avis et des équipements disponibles.

## Présentation du projet

Le projet suit les principales étapes d'un pipeline de Machine Learning :

- Analyse exploratoire des données
- Traitement des valeurs manquantes
- Feature engineering
- Encodage des variables catégorielles
- Comparaison de plusieurs modèles de régression
- Validation croisée à 5 folds
- Entraînement du modèle final et génération des prédictions

Afin d'éviter toute fuite de données lors de l'évaluation, le prétraitement est ajusté indépendamment sur les données d'entraînement de chaque fold de validation croisée.

## Modèles comparés

Plusieurs approches ont été évaluées :

- Baseline basée sur la moyenne
- Régression linéaire
- Ridge
- Lasso
- Arbre de décision
- Random Forest
- Gradient Boosting

## Résultats

| Modèle | RMSE en validation croisée |
|---|---:|
| Baseline (moyenne) | 0.7188 ± 0.0049 |
| Régression linéaire | 0.4706 ± 0.0069 |
| Ridge | 0.4706 ± 0.0069 |
| Lasso | 0.4783 ± 0.0089 |
| Arbre de décision | 0.4711 ± 0.0089 |
| Random Forest | 0.4061 ± 0.0090 |
| **Gradient Boosting** | **0.3932 ± 0.0077** |

Le **Gradient Boosting Regressor** obtient les meilleures performances et est donc retenu comme modèle final.

## Feature engineering

Plusieurs variables ont été créées à partir des données initiales, notamment :

- Ancienneté de l'hôte
- Nombre de jours depuis le dernier avis
- Présence ou absence d'avis
- Équipements disponibles dans le logement
- Nombre total d'équipements
- Nombre de personnes par chambre
- Score des avis pondéré par le nombre d'avis

## Technologies utilisées

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- seaborn
- Jupyter Notebook

## Structure du dépôt

```text
.
├── airbnb_price_prediction.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

Les jeux de données d'entraînement et de test ne sont pas inclus dans le dépôt.

## Remarque

Ce projet a initialement été réalisé dans le cadre de ma formation à l'ESILV. La version présente sur ce dépôt améliore notamment la procédure d'évaluation afin que le prétraitement soit appris indépendamment dans chaque fold de validation croisée.