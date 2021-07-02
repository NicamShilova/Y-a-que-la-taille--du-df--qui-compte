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

![image](https://user-images.githubusercontent.com/67276724/124312129-1c71b980-db6f-11eb-9cc8-a31405198973.png)

- Sur l'enthropie croisée, au début, le train et le test sont de même valeur avant que le train diminue sa perte alors que le test parvient à conserver une valeur stable
- De plus, la courbe de test repart à la hausse. Donc il y a surentrainement
- Sur la Classification Accuracy, le train et le test sont de même valeur avant que le train augmente sa perte alors que le test parvient à conserver une valeur stable
- Sur les deux graphiques : la différence du train par rapport au test est que le train a un écart deux fois plus élevé que le test

Avec la méthode data augmentation :

![image](https://user-images.githubusercontent.com/67276724/124312189-34493d80-db6f-11eb-8ff2-751ec28992c4.png)

- Vers le fin des epoch, le résultat est semblable que les résultats sans méthode data augmentation
- Cependant, les valeurs entre le train et le test restent bien plus longtemps semblable avant de diverger, surtout sur la Classification Accuracy
- De plus, sur l'enthropie croisée, la courbe de test parvient à rester stable. Donc il n'y a pas de surentrainement

En conclusion, la méthode de data augmentation est préférable car non seulment elle permet de prévenir le surentrainement et de mieux stabilier les pertes et efficacités entre les train et les tests, mais en plus elle permet un traitement plus rapide.



