# Y'a que la taille (du df) qui compte




### La société "Little Sister" est une entreprise spécialisée dans le secteur de la vidéosurveillance. Elle revient vers vous afin d'améliorer l'algorithme que vous lui avez précédemment fourni.


## Pré-requis

```
sys
pyplot
cifar10
categorical
Sequential
Conv2D
MaxPooling2D
Dense
Flatten
SGD
ImageDataGenerator
```

## Notes

Le jeu de données, cifar10, est automatiquement téléchargé à la première utilisation, ce qui nécessite un temps de traitement supplémentaire
En raison de manque de temps, seul une partie de ce jeu de données sera utilisé :
	- Les 800 premières images pour le train
	- Les 200 suivantes pour le test


## Installation

Installer Anaconda

Installer vscode


## Exécution

Dans vscode, charger d'abord l'environnement puis lancer vscode

```
conda activate [nom de l'environnement]
code
```

Charger la classe entrainement_sans_data_augmentation.ipynb

Cliquer sur la double flèche (ou le bouton "Run all" sur la version la plus récente de vscode) pour tout exécuter.

Charger la classe entrainement_avec_data_augmentation.ipynb

Cliquer sur la double flèche (ou le bouton "Run all" sur la version la plus récente de vscode) pour tout exécuter.


## Résultats

Sans la méthode data augmentation :

- Sur l'enthropie croisée, au début, le train et le test sont de même valeur avant que le train diminue sa perte alors que le test parvient à conserver une valeur stable.
- Sur l'enthropie croisée, la courbe de test commence part une diminution avant de repartir à la hausse. Cela signifie qu'il y a surentrainement.
- Sur la Classification Accuracy, le train et le test sont de même valeur avant que le train augmente sa perte alors que le test parvient à conserver une valeur stable.

Avec la méthode data augmentation :

- La Classification Accuracy a le résultat semblable à celle se passant de la méthode data augmentation.
- Cependant, les valeurs entre le train et le test restent bien plus longtemps semblable avant de diverger, surtout sur la Classification Accuracy.
- Sur l'enthropie croisée, la courbe de test parvient à rester stable. Cela signifie qu'il n'y a pas de surentrainement.

En conclusion, la méthode de data augmentation est préférable car non seulment elle permet de prévenir le surentrainement et de mieux stabiliser les pertes et efficacités entre les train et les tests, mais en plus elle permet un traitement plus rapide.



