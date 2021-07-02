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

Cliquer sur la double flèche (ou le bouton "Run all" sur la version la plus récente de vscode) pour tout exécuter

Charger la classe entrainement_avec_data_augmentation.ipynb

Cliquer sur la double flèche (ou le bouton "Run all" sur la version la plus récente de vscode) pour tout exécuter


## Résultats

Sans la méthode data augmentation :
- Sur l'enthropie croisée, au début, le train et le test sont de même valeur avant que le train diminue sa perte alors que le test parvient à conserver une valeur stable
- De plus, la courbe de test repart à la hausse. Donc il y a surentrainement
- Sur l'efficacité de la classification, le train et le test sont de même valeur avant que le train augmente sa perte alors que le test parvient à conserver une valeur stable
- Sur les deux graphiques : la différence du train par rapport au test est que le train a un écart deux fois plus élevé que le test

Avec la méthode data augmentation :
- Vers le fin des epoch, le résultat est semblable que les résultats sans méthode data augmentation
- Cependant, les valeurs entre le train et le test restent bien plus longtemps semblable avant de diverger, surtout sur l'efficacité de la classification
- De plus, sur l'enthropie croisée, la courbe de test parvient à rester stable. Donc il n'y a pas de surentrainement

En conclusion, la méthode de data augmentation est préférable car elle permet de prévenir le surentrainement et de mieux stabilier les pertes et efficacités entre les train et les tests.



