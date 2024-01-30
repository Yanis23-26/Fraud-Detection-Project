### PROJET : Détection de la fraude bancaire

# Presentation :

**C'est quoi ?** Ce projet est lui meme un modèle  qui consiste à trouver le modèle ML de classification adapté qui permet de categoriser les transactions bancaires frauduleuse en non frauduleuse d'un dataset donné.

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

# Données :
Le jeu de données utilisé dans le projet est récupéré sur Kaggle. Il est généré à l'aide du simulateur PaySim qui simule
des transactions mobiles d'argent sur la base d'un échantillon de transactions réelles extraites d'un mois de
journaux financiers d'un service d'argent mobile mis en œuvre dans un pays africain.

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

# Questions & Reponses :

**Quelle rapport entre modèle et l'algorithme ?** Un modèle contient son propre algorithme
**Ou se trouve les modèles à comparer ?** déjà prets dans la MLLib (e.g algorithmes : la foret aléatoire,le classificateur GBT, algo de regression logistique, calassificateur Naive bayes,  le gradient boost ... )

**Comment fonctionne ce modèle ?** Il divise le dataset fournit en echantillon de test 20% et de verfication 80%, exécute les modèles sur les 20%, fait des prédiction pour les verifie sur les 80%, le modèle avec le moins d'érreur est le meilleur.

**Comment nos modèle reconnaissent une fraude ?** grace aux caracteristiques inhabituelles déjà predefinies (type isFraud) : 
- montants de virements trop elevés et suspicieux
- retrait/dépot bizarres dans des endroits inhabituels
-  debit ...

**Quelles techniques ?** utilise :
- MLLib : lib de apache Spark qui contient les differents modèles
- Apache Spark : fournit une API = envirement d'éxécution pour accéler les differents modèles MLLib  
- Python : est le langage de programmation utilisé dans ce projet pour coder les differents algorithmes
- MatplotLib & Pandas : lib de python pour créer mes visualisations dans l'étape de visualisation des données.


**Quelles étapes à suivre ?** 
- Exploration Data Analysis
- Pré-traitement des données
- Developpement de l'application
- Evaluation des prediction
- Resultats


# Méthode suivie :

**1- EDA: Exploration Data Analysis :** 
étude statistique descriptive et visualisation préliminaire des données pour déterminer les mesures de base du dataset (moyenne, min, max ...) % de fraude dans notre daechantillon de test puis d'étudier la correlation entre les variables pour detecter s'il ya correlation (==> redondance ==> mauvais modele)
Remarque : dans notre cas, il y'a un déséquilibre ==> résultats seront donc peu précis
**2- Pré-traitement des données :** : verification des données manquantes (e.g colonne), puis transformation des données en vecteurs numeriques (e.g String --> int) pySpark traite les val num avec les fonctions  ===> On utilise Spark pour faire vite
**3- Developpement de l'application :** ici on va deviser le jeu de données (20% pour le test, 80% pour le controle qualité) on entraine les differents modèles sur le test puis on fait des prédictions et on fait nos évaluation sur les 80% réstants
**4- Evaluation des predictions :** on applique les métriques d'évaluation (Recall, ROC, AUC ... ) pour évaluer la fiabilité des modeles et calculer le % d'erreur ainsi trancher sur le meilleur modèle à prendre.

# Resultats : 
Le GRadient Boost Classifier est plus performant que les autres modèles si on considère toutes les ́metriques de l'evaluation.


