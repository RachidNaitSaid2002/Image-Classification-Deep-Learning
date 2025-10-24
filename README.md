# Projet d'Analyse et de Classification d'Images (Fashion MNIST)

Ce projet présente un projet d'apprentissage automatique (Machine Learning) visant à classer des images d'articles de mode à l'aide d'un réseau neuronal simple implémenté avec TensorFlow/Keras.

Le jeu de données utilisé est **Fashion MNIST**, une collection de 70 000 images en niveaux de gris de 10 catégories d'articles de mode.

## Objectifs du Projet

1.  Charger et explorer le jeu de données Fashion MNIST.
2.  Visualiser des exemples d'images et leurs étiquettes.
3.  Normaliser les données pour l'entraînement du modèle.
4.  Construire, compiler et entraîner un réseau neuronal simple (Dense Layers).
5.  Évaluer les performances du modèle sur l'ensemble de test.

## Dépendances

Ce projet nécessite les bibliothèques Python suivantes :

*   `tensorflow` (avec `keras`)
*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`

Vous pouvez installer ces dépendances en utilisant `pip` :

```bash
pip install tensorflow pandas numpy matplotlib seaborn
```

## Structure du Notebook

Le notebook est structuré en plusieurs étapes logiques :

1.  **Importation des Bibliothèques** : Importation de TensorFlow, Keras et des outils d'analyse de données.
2.  **Chargement et Inspection des Données** : Chargement du jeu de données Fashion MNIST et affichage des dimensions.
3.  **Visualisation des Données** : Affichage d'un échantillon des images d'entraînement.
4.  **Pré-traitement des Données** : Normalisation des valeurs de pixels entre 0 et 1.
5.  **Construction du Modèle** : Définition d'un modèle `Sequential` avec une couche `Flatten` et deux couches `Dense`.
6.  **Compilation et Entraînement** : Compilation du modèle avec l'optimiseur `adam` et la fonction de perte `sparse_categorical_crossentropy`. L'entraînement utilise un `EarlyStopping` pour éviter le surapprentissage.
7.  **Évaluation** : Évaluation finale de la perte et de la précision sur le jeu de données de test.

## Classes d'Articles (Étiquettes)

Le modèle est entraîné pour classer les images dans les 10 catégories suivantes :

| Index | Nom de la Classe (Français) |
| :---: | :------------------------- |
| 0     | T-shirt                    |
| 1     | Srwal (Pantalon)           |
| 2     | Trico (Tricot/Pull)        |
| 3     | Dress (Robe)               |
| 4     | Jacket (Veste)             |
| 5     | Sandal (Sandale)           |
| 6     | 9amija (Chemise)           |
| 7     | Sprdila_Normal (Baskets)   |
| 8     | Sac (Sac)                  |
| 9     | Jordan (Chaussures)        |

## Le projet utilise sparse_categorical_crossentropy plutôt que categorical_crossentropy. Voici pourquoi:
### sparse_categorical_crossentropy
Utilisée dans ce projet
Accepte des labels sous forme d'entiers (0, 1, 2, ...)
Plus simple à utiliser avec Fashion MNIST
Économise en mémoire

### categorical_crossentropy
Nécessite un encodage one-hot
Ex: [0, 0, 1, 0, 0, 0, 0, 0, 0, 0]
Requiert une étape de prétraitement supplémentaire
Plus de mémoire utilisée
