# pr-dire-les-salaires-avec-les-modeles-de-DL-et-ML

🧠 Contexte du projet

Ce projet analyse un dataset contenant des informations sur les salaires dans différents métiers liés à la data science à travers le monde. Le but est d’étudier les facteurs influençant la rémunération, comme le niveau d’expérience, le type d’emploi, la localisation géographique, et le contexte de travail (télétravail, présentiel, etc.).

Le dataset inclut des données collectées sur plusieurs années, avec des salaires exprimés dans différentes devises, et convertis en dollars américains pour faciliter les comparaisons internationales. Il couvre un large éventail de rôles dans le domaine de la data, notamment Data Scientist, Data Engineer, Data Analyst, et plus encore.


# Prédiction de salaire avec Machine Learning et Deep Learning

Ce projet compare deux approches pour prédire le salaire (en USD) à partir de données liées aux métiers et profils dans le domaine de la data :

- Un modèle **Machine Learning** classique (Random Forest)  
- Un modèle **Deep Learning** simple (réseau de neurones Keras)

---

## Données

Les données utilisées sont issues du fichier `jobs_in_data.csv` contenant des informations sur les postes, l'expérience, la localisation, la taille d'entreprise, etc.

---

## Fonctionnalités principales

- Nettoyage et sélection des colonnes importantes  
- Gestion des valeurs aberrantes (outliers) sur la cible `salary_in_usd`  
- Encodage des variables catégorielles avec `OneHotEncoder`  
- Normalisation des variables numériques et de la cible (pour DL)  
- Séparation train/test  
- Entraînement et évaluation du modèle Random Forest (ML)  
- Entraînement et évaluation d’un réseau de neurones Keras (DL)  
- Visualisation comparative des prédictions ML vs DL

---
Modèle Machine Learning : Random Forest

Le Random Forest est un modèle d’ensemble très utilisé en Machine Learning. Il combine plusieurs arbres de décision, chacun entraîné sur une sous-partie des données, pour faire des prédictions plus robustes et précises.

Principaux points :

Manipule directement les données tabulaires, avec encodage simple des variables catégorielles (OneHotEncoder).

Bon pour capter des relations non linéaires entre variables.

Rapide à entraîner et à prédire sur des datasets de taille moyenne.

Assez interprétable (ex : importance des features).

Performant sur des données structurées comme ici (profils métiers, expérience, localisation, etc.).

Évalue les performances du modèle avec deux métriques :

MSE (Mean Squared Error) : mesure moyenne des erreurs au carré entre prédictions et valeurs réelles (plus c’est petit, mieux c’est)

R² (coefficient de détermination) : mesure la qualité de la prédiction (1 = parfait, 0 = modèle qui prédit la moyenne)

Les resultats
MSE: 79648455.14

R2 score: 0.9808

![Capture d’écran 2025-08-05 003429](https://github.com/user-attachments/assets/73534530-5743-413f-b7a7-1bd8e2a6d999)


Modèle Deep Learning : Réseau de Neurones Dense
Le modèle Deep Learning est un réseau de neurones à couches entièrement connectées (Dense), construit avec Keras/TensorFlow. Il apprend automatiquement des représentations complexes des données pour faire des prédictions.

Principaux points :

Nécessite un prétraitement plus poussé (normalisation des features et de la cible).

Peut modéliser des relations complexes et interactions non linéaires plus fines que certains modèles classiques.

Plus gourmand en données et ressources de calcul (GPU recommandé).

Moins interprétable car considéré comme une "boîte noire".

Potentiellement plus puissant si on augmente la profondeur ou la taille du réseau, ou avec plus de données.


<img width="741" height="541" alt="image" src="https://github.com/user-attachments/assets/31410744-9d70-40b1-8f33-d781e5b91f3d" />


la comparaison entre les deux DL et ML

<img width="764" height="539" alt="image" src="https://github.com/user-attachments/assets/1982d8aa-d60a-4c8a-bc54-27c052778e11" />

Résultat dans ce projet
Le modèle Random Forest offre une bonne précision rapidement et avec peu de paramétrage.

Le modèle Deep Learning, bien que plus long à entraîner, peut capturer des relations plus fines entre les variables et améliorer la performance si on ajuste correctement le réseau et les hyperparamètres.
