# Analyse des pics de vente et organisation des stocks
Analyse des ventes de fruits et légumes frais de l'entreprise FastAlim sur 4 ans.
FastAlim fournit les professionnels de la restauration en produits alimentaires et boissons. L’entreprise souhaite développer son activité de fruits et légumes frais, notamment pour répondre à la demande de menus végétariens de certains clients.
Ma mission consiste à comprendre les variations d’activité et à proposer une répartition des produits dans l’entrepôt adaptée à leurs comportements de vente.

Problématique : comment l’analyse de l’évolution et de la saisonnalité des ventes peut-elle aider FastAlim à anticiper les variations d’activité et à organiser ses stocks ?

## Objectifs principaux
1. Explorer et préparer les données de ventes.
2. Identifier les cinq produits les plus vendus en volume sur 4 ans.
3. Analyser leurs évolutions annuelles et mensuelles.
4. Comparer leurs distributions et repérer les pics et creux saisonniers.
5. Étudier les corrélations entre leurs volumes mensuels.
6. Proposer des recommandations de répartition en entrepôt.
   
## Jeu de données
Fichier utilisé Jeu+de+donnees_P9_SCA.xlsx.
- historique des données: du 1er janvier 2017 au 31 décembre 2022
- période analysée: du 1er janvier 2019 au 31 décembre 2022
- Observations initiales: 32865
- produits distincts: 15
- granularité: vente d'un produit à une date donnée
- colonnes initiales: date, product, sales.
  La variable sales étant utilisée comme volume de ventes
- variables créés: year, month, month_year pour le top5.
Aucune valeur manquante ni de ligne entièrement dupliquée détectée lors de l'exploration.

## Outils et technologies
- Python et Jupyter Notebook.
- pandas : chargement, préparation et agrégation des données.
- Matplotlib et Seaborn : graphiques et matrice de corrélation.
- Plotly Express : courbes interactives et boîtes à moustaches.
- NumPy et SciPy : bibliothèques également importées dans le notebook.
  
## Méthodes
- Statistiques descriptives : médiane, quartiles, écart-type et dispersion des volumes.
- Agrégations temporelles : sommes annuelles et mensuelles par produit.
- Analyse visuelle de la saisonnalité : comparaison des évolutions sur les quatre années.
- Boîtes à moustaches : comparaison des distributions par produit, année et mois.
- Corrélation de Pearson : mesure des associations entre les volumes mensuels des produits du top 5.
  
## Démarches d'analyses des données
- Explorer les données : structure, dates, types, valeurs manquantes, doublons et volumes négatifs.
- Préparer le périmètre : créer les variables temporelles et filtrer les données sur 2019–2022.
- Sélectionner le top 5 : classer les produits selon leurs volumes cumulés sur quatre ans.
- Analyser les évolutions : construire les courbes annuelles et mensuelles.
- Comparer les distributions : examiner les médianes, les dispersions et les valeurs atypiques.
- Étudier les relations : calculer les corrélations et comparer les courbes par paire de produits.
- Formuler les recommandations : traduire les profils observés en propositions de placement dans l’entrepôt.
## Résultats finaux
### TOP5 des produits
| Rang | Produit | Volume cumulé 2019-2022 |
| --- | --- | ---: |
| 1 | Tomate | 238 205,13 |
| 2 | Pomme | 225 451,24 |
| 3 | Banane | 188 235,31 |
| 4 | Abricot | 178 763,88 |
| 5 | Kiwi | 171 136,63 |

### Principales corrélations
| Produits | Corrélation de Pearson |	Relation observée 
| --- | --- | ---: |
| 1 | Tomate / Abricot |	0,94 | Forte relation positive |
| 2 | Kiwi / Abricot |	−0,92	| Forte relation négative |
| 3 | Kiwi / Tomate |	−0,87	| Forte relation négative |
| 4 | Pomme / Banane |	0,53 | Relation positive modérée |
| 5 | Pomme / Tomate |	0,34 | Relation positive plus faible |

## Recommandations logistiques
1. Rapprocher les zones de la tomate et de l’abricot, dont les périodes de forte demande sont similaires, afin de faciliter la préparation et le réapprovisionnement. Le notebook envisage également un rapprochement pomme/tomate, avec une similarité moins forte.
2. Placer le kiwi dans une zone différente de celles de la tomate et de l’abricot, en raison de sa saisonnalité opposée.
## Limites de l’étude
- L’étude décrit les ventes observées sur 2019–2022, elle ne produit pas de prévisions chiffrées des ventes futures.
- Les corrélations ne démontrent pas une relation causale ni une présence simultanée des produits dans les mêmes commandes.
- Les recommandations de placement doivent tenir compte des contraintes de conservation, de capacité, de manutention et de soutenabilité.
- Les gains logistiques attendus ne sont pas quantifiés dans cette étude.
