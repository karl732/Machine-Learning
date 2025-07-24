# Projet web-scraping

Est-ce que vous aussi vous avez déjà voulu vendre votre console de jeux vidéo mais vous ne saviez pas à quel prix la vendre?
Si oui, alors ce projet est fait pour vous ! 😊

Dans ce projet nous avons voulu déterminer le prix de vente optimal d'une console de jeux vidéo en Indre-et-Loire, selon la marque de la console, ses caractéristiques et son état. 
Pour cela nous avons utilisé le package `Selenium` de Python pour faire du web-scraping et récupéré les données de plusieurs centaines de consoles, puis nous avons transformé les données et enfin nous avons utilisé des modèles de machine learning pour prédire le prix optimal d'une console selon ses caractéristiques.


## 1. Scraping

Pour extraire les données qui nous intéressent du site, nous avons créé 4 librairies : librairie_1, librairie_2, librairie_3 et librairie_4. Chacune d'entre elles permet de réaliser une partie de l'extraction des données, dans l'ordre de leur numérotation. L'objet final contenant les données extraites est disponible dans le document "liste_final.json" présent dans le répertoire. Il a été utilisé ultérieurement dans le projet pour la création et le nettoyage de la base de données.

Remarque : Du fait de l'approche que l'on a utilisée pour la création des librairies de cette partie, nous avons rencontré des difficultés à passer les tests sur ces librairies. Des problèmes d'importation des librairies que nous avons créées et qui sont directement utilisées dans les suivantes, ainsi que la non possibilitée d'empêcher la compilation complète à chaque test (librairie_1 exclu).


## 2. Preprocessing

- nettoyage de la base de données et recodage des variables
Avant tout calcul de modèle, les données doivent subir un traitement permettant leur compatibilité avec le module `scikit-learn`. 

Il faut premièrement unifier les données obtenues. Elles sont divisés en quatre fichiers `json` donc le nom est éponyme aux marques. Pour cela, on les ouvre et les concatène à l'aide de la fonction `concat` de `pandas` sous la forme d'un tableau de données (dataframe).

## Machine Learning
- entraînement des modèles
- vérification du surapprentissage
- sélection du meilleur modèle

Dans ce projet, l'uitlisation du machine learning a pour objectif de prédire le prix de marché des consoles de jeux vidéos.

### Modèle utilisés

Les modèles utilisés sont essentiellement tirés du module `scikit-learn`.

Ils comprennent :

- Gradient Boosting
- Support Vector Machine
- Random Forest
- Multi-Layer Perceptron
- KNN
- ...

Les données sont divisés en deux splits avec un rapport 4/5 ; 1/5  :

1. Entraînement
2. Test

Chaque modèle est entrainé par validation croisée sur le split d'entraînement permettant d'obtenir les paramètres optimaux parmi une liste préselectionnée.

Une fonction permet ensuite de calculer le meilleur estimateur.

*NB : le meilleur modèle est recalculé si le scraping est relancé.*

Les prédictions obtenues sont stockées dans un tableau `resultat.csv`.

# Installation

- En téléchargeant le dossier :
```sh
py -m pip install C:/Users/Downloads/GHAFFOUR_JEAN_SONDEJI_PROJECT
```
