# Analyse des ventes d’une librairie avec Python

## Description
Ce projet consiste à analyser les données de ventes d’une librairie afin d’en dégager des tendances, comprendre les comportements d’achat, et identifier les meilleures ventes.

## Objectifs
Nettoyer et préparer les données de vente.
Explorer les données pour identifier les meilleures catégories et produits.
Visualiser les évolutions des ventes dans le temps.
Établir des recommandations pour la gestion du stock et des promotions.
Instructions pour reproduire l’analyse
Cloner le dépôt et installer les dépendances avec la commande :
```python
pip install -r requirements.txt
```
Charger les fichiers CSV situés dans le dossier /data.
Exécuter les notebooks Python dans /notebooks pour suivre l’analyse complète.
Consulter les rapports générés dans /reports.

## Outils utilisés
Python 3.x avec pandas, matplotlib, seaborn.
Jupyter Notebook pour un travail interactif.

## Résultats techniques
Analyse descriptive des ventes selon les catégories et produits.
Graphiques temporels affichant l’évolution des ventes mensuelles.
Identification des produits phares et recommandations stratégiques.
Code clair et commenté favorisant la réutilisation.

## Exemple de code Python
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Chargement des données
ventes = pd.read_csv('data/ventes_librairie.csv')

# Aperçu des données
print(ventes.head())

# Total des ventes par catégorie
ventes_par_categorie = ventes.groupby('categorie')['quantite_vendue'].sum().reset_index()

# Visualisation des ventes par catégorie
plt.figure(figsize=(8,5))
sns.barplot(data=ventes_par_categorie, x='categorie', y='quantite_vendue', palette='coolwarm')
plt.title('Ventes par catégorie')
plt.xlabel('Catégorie')
plt.ylabel('Quantité vendue')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```
### Explications :
Le script charge les données et affiche un aperçu rapide.
Il regroupe les ventes par catégorie pour obtenir une vision claire des performances.
Un diagramme à barres illustre ces résultats pour faciliter la prise de décision.
