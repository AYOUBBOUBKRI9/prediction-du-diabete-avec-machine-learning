# Projet Data Mining : Prédiction du diabète avec le Machine Learning

## 1. Présentation du projet

Ce projet a été réalisé dans le cadre du module **Data Mining**. Il porte sur la conception et l'évaluation de modèles de Machine Learning capables de classifier des individus selon la présence ou l'absence du diabète, à partir de variables liées à leur état de santé.

L'objectif principal est d'étudier plusieurs algorithmes de classification supervisée, de comparer leurs performances et d'identifier leurs avantages et leurs limites sur le jeu de données utilisé.

## 2. Objectifs du projet

- Collecter et comprendre les données utilisées.
- Nettoyer et préparer les données avant la modélisation.
- Réaliser une analyse exploratoire des données (EDA).
- Appliquer plusieurs algorithmes de classification.
- Évaluer les performances à l'aide de différentes métriques.
- Comparer les modèles et interpréter les résultats.
- Étudier l'importance des variables dans les prédictions.

## 3. Démarche suivie

Le projet suit les principales étapes d'un processus de Data Mining :

1. **Collecte des données :** récupération du jeu de données utilisé pour la prédiction du diabète.
2. **Nettoyage des données :** examen des valeurs manquantes, des valeurs aberrantes et des éventuelles incohérences.
3. **Transformation des données :** préparation des variables pour leur utilisation par les algorithmes.
4. **Modélisation :** entraînement de quatre modèles de classification supervisée.
5. **Évaluation :** calcul et comparaison des performances des modèles.
6. **Interprétation :** analyse des résultats et de l'importance des variables.

## 4. Algorithmes de Machine Learning

### 4.1. Arbre de décision (Decision Tree)

L'arbre de décision est un algorithme de classification supervisée qui apprend des règles à partir des variables disponibles. Il divise progressivement les observations en groupes afin de produire une prédiction.

### 4.2. Forêt aléatoire (Random Forest)

Random Forest combine plusieurs arbres de décision afin de produire une prédiction commune. Le projet utilise également l'importance des variables pour examiner celles qui contribuent le plus aux prédictions du modèle.

### 4.3. K plus proches voisins (KNN)

KNN classe une observation en fonction des observations les plus proches dans l'espace des variables. Le choix du nombre de voisins, noté K, influence les performances du modèle.

Une expérimentation a été réalisée pour comparer l'accuracy selon différentes valeurs de K. La présentation indique que K = 3 correspond à la meilleure valeur observée lors de ce test.

### 4.4. Machine à vecteurs de support (SVM)

SVM cherche à séparer les classes à l'aide d'une frontière de décision. Le modèle présenté utilise un noyau RBF, qui permet de représenter des séparations non linéaires.

## 5. Technologies utilisées

Les technologies mobilisées dans le projet comprennent :

- **Python** : développement et expérimentation.
- **Pandas et NumPy** : manipulation et préparation des données.
- **Scikit-learn** : entraînement et évaluation des modèles.
- **Matplotlib et Seaborn** : visualisation des données et des résultats.
- **Jupyter Notebook / Google Colab** : environnement de développement.

Cette liste doit être ajustée en fonction des bibliothèques réellement utilisées dans le code.

## 6. Résultats et comparaison des modèles

Les résultats présentés lors de l'exposé sont les suivants :

| Algorithme | Accuracy rapportée |
|---|---:|
| Arbre de décision | 79,22 % |
| KNN | 76,62 % |
| SVM avec noyau RBF | 74,68 % |
| Random Forest | 74,03 % |

### Interprétation

Parmi les résultats rapportés, l'arbre de décision présente la meilleure accuracy, avec 79,22 %, suivi de KNN avec 76,62 %.

Le SVM obtient une accuracy de 74,68 %, tandis que Random Forest atteint 74,03 %.

Ces valeurs permettent de comparer les résultats des expérimentations réalisées. Toutefois, une comparaison rigoureuse suppose que les modèles aient été évalués sur le même jeu de test et selon le même protocole.

L'accuracy représente la proportion totale de prédictions correctes. Elle ne suffit pas, à elle seule, pour évaluer la capacité d'un modèle à détecter les cas de diabète.

## 7. Analyse détaillée du modèle SVM

Le rapport de classification présenté pour le SVM avec noyau RBF fournit les résultats suivants :

| Métrique | Non-diabétique | Diabétique |
|---|---:|---:|
| Précision | 0,78 | 0,67 |
| Rappel | 0,85 | 0,56 |
| F1-score | 0,81 | 0,61 |
| Nombre d'observations | 100 | 54 |

L'accuracy globale rapportée est de 74,68 %, sur un échantillon de test de 154 observations.

Le rappel de 0,56 pour la classe diabétique indique que le modèle a identifié environ 56 % des observations réellement diabétiques dans cet échantillon. Ce résultat montre qu'une partie des cas positifs n'a pas été détectée.

Cette observation souligne l'importance d'examiner le rappel, le F1-score et la matrice de confusion, en complément de l'accuracy, notamment pour un problème lié à la santé.

## 8. Importance des variables

L'analyse de l'importance des variables du modèle Random Forest présentée dans l'exposé met en évidence les variables suivantes :

- Glucose
- IMC (indice de masse corporelle)
- Âge
- Diabetes Pedigree Function
- Insuline
- Grossesses
- Épaisseur du pli cutané
- Pression artérielle

Dans les résultats présentés, le glucose possède le score d'importance le plus élevé, suivi de l'IMC et de l'âge.

Cette importance correspond à la contribution des variables aux prédictions du modèle selon la méthode utilisée. Elle ne démontre pas, à elle seule, une relation de causalité avec le diabète.

## 9. Limites du projet

Plusieurs limites doivent être prises en compte :

- Les performances dépendent du jeu de données et de sa représentativité.
- L'accuracy ne reflète pas toutes les erreurs de classification.
- Les résultats doivent être confirmés avec un protocole d'évaluation cohérent.
- Une validation supplémentaire serait nécessaire pour évaluer la généralisation des modèles.
- Les prédictions ne peuvent pas être utilisées comme un diagnostic médical.

## 10. Structure du dépôt GitHub

```text
diabetes-prediction-data-mining/
├── README.md
├── diabetes_prediction.ipynb
├── requirements.txt
├── data/
└── images/
    ├── decision_tree.png
    ├── random_forest_feature_importance.png
    ├── knn_accuracy.png
    └── model_comparison.png
```

Les noms des fichiers peuvent être adaptés à ceux réellement présents dans le dépôt.

## 11. Installation et exécution

1. Cloner le dépôt GitHub.
2. Installer les dépendances indiquées dans `requirements.txt`.
3. Ouvrir le notebook dans Jupyter Notebook ou Google Colab.
4. Vérifier le chemin d'accès au jeu de données.
5. Exécuter les cellules dans l'ordre pour reproduire les étapes du projet.

## 12. Conclusion

Ce projet a permis d'étudier et de comparer quatre algorithmes de classification supervisée appliqués à la prédiction du diabète : Decision Tree, Random Forest, KNN et SVM.

Les résultats présentés indiquent que l'arbre de décision obtient la meilleure accuracy parmi les modèles testés. L'analyse détaillée du SVM met également en évidence l'intérêt d'utiliser plusieurs métriques pour mieux comprendre les performances d'un classificateur.

Ce travail a permis de mettre en pratique les principales étapes d'un projet de Data Mining, depuis la préparation des données jusqu'à l'évaluation et à l'interprétation des résultats.

## Auteur
- Mohamed Ayoub Boubkri

