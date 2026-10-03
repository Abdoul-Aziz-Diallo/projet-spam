\# Classification automatique des emails (spam / non-spam)



Projet Machine Learning, Master BDA/IA, Université Numérique Cheikh Hamidou Kane.

Encadrant : Dr. DIA Yoro.



\## Objectif

Classer automatiquement des emails en spam ou non-spam (classification binaire supervisée).



\## Données

\- Corpus Enron (`Enron.csv`) du dataset Kaggle « Phishing Email Dataset » (Naser Abdullah Alam et al.), licence CC BY-SA 4.0.

\- 29 766 emails après nettoyage, dont 46,9 % de spam.

\- Les données ne sont pas dans le dépôt : téléchargez-les sur Kaggle et placez les CSV dans `data/raw/`.

&#x20; `Ling.csv` et `SpamAssasin.csv` servent uniquement au test de robustesse.



\## Structure

| Dossier | Contenu |

|---|---|

| `notebooks/` | Un notebook par étape (01 à 09) |

| `images/` | Figures du rapport |

| `data/processed/` | Résultats chiffrés (`resultats.csv`) |

| `models/` | Modèle final (`svm\_final.joblib`) |



\## Étapes

1\. Chargement du dataset

2\. Analyse exploratoire

3\. Nettoyage et tokenisation

4\. Découpage train/test et TF-IDF

5\. Baseline Naive Bayes

6\. SVM et Random Forest

7\. Modèles avancés : Word2Vec (local) et DistilBERT (Google Colab, GPU T4)

8\. Optimisation des hyperparamètres

9\. Analyse des erreurs, seuil de décision et robustesse



\## Résultats principaux (jeu de test Enron, 5 954 emails)

Meilleur modèle : SVM linéaire, TF-IDF en unigrammes et bigrammes, C = 1.

Accuracy 99,16 %, F1 99,11 %, 35 faux positifs, 15 faux négatifs.



Limite importante : testé sur les corpus Ling et SpamAssassin, le modèle ne généralise pas

(accuracy 60,7 % et 40,1 %). Voir le notebook 09 et le rapport.



\## Installation

```bash

pip install -r requirements.txt

jupyter notebook

```

Les notebooks s'exécutent dans l'ordre. Le notebook `07b` (DistilBERT) demande `torch`,

`transformers` et un GPU (Google Colab).

