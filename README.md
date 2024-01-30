### PROJET : Détection de la fraude bancaire

# Presentation :
Le jeu de données utilisé dans le projet est récupéré sur Kaggle. Il est généré à l'aide du simulateur PaySim qui simule
des transactions mobiles d'argent sur la base d'un échantillon de transactions réelles extraites d'un mois de
journaux financiers d'un service d'argent mobile mis en œuvre dans un pays africain.

# Lien :
Lien vers le jeu de données : (https://www.kaggle.com/datasets/ealaxi/paysim1)

# Variables :
Composé des variables suivantes:
- ‘type’ type de transaction : payment, transfer, cash out, cash in, debit.
- ‘amount’ montant de la transaction.
- ‘nameOrig’ identifiant de l’émetteur.
- ‘oldbalanceOrg’ solde de l’émetteur avant la transaction.
- ‘newbalanceOrig’ solde de l’émetteur après la transaction.
- ‘nameDest’ identifiant du destinataire.
- ‘oldbalanceDest’ solde du destinataire avant la transaction.
- ‘newbalanceDest’ solde du destinataire après la transaction.
- ‘isFraud’ 1 si la transaction est frauduleuse, sinon 0.
- ‘isFraggedFraud’ 1 si la transaction a été signalée frauduleuse, sinon 0.

# Méthode suivie :
Afin de mieux catégoriser les différentes transacions bancaire en goupes de transactions frauduleus et non-frauduleuses :
- Je vais tout d’abord pré-traiter les données 
- Ensuite les transformer en des vecteurs numériques afin d'appliquer les modèles de classification.
- J'applique la régression logistique, l'arbre de décision, la foret aléatoire, le calassificateur GBT et calassificateur Naive bayes. 
- Une fois ces modèles appliquées, j'utilise des métriques d'evaluation pour les évaluer et choisir le modèles à utiliser dans la catégorisation de futures transactions.


# Reperoire :

Le répertoire de travail est organisé comme suit:

- input_data : les données de transactions bancaires pour l’apprentissage des modèles.

- src : contient les sources du code python :
	- utils : répertoire des fonctions utilisées dans le main
	- annexe : répertoire contenant l'analyse exploratoire des données

- main.ipynb : le fichier principal contenant les modèles de préparation des données et de classification.
- preprocessing.ipynb : le fichier contenant les différents pré-traitements effectués sur le données afin qu'elles soient exploitables par les modèles d'apprentissage.

- présentation : rapport et présentation des résultats du projet
- README : informations sur le projet


