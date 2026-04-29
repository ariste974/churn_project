# 📊 Customer Churn Prediction

## 🚀 Overview

Ce projet vise à prédire le **churn client** (désabonnement) à partir de données clients issues du secteur télécom.

Objectif : identifier les clients à risque afin d’optimiser les stratégies de rétention.

---

## 🧠 Features

- Analyse exploratoire des données (EDA)
- Prétraitement et nettoyage des données
- Gestion du déséquilibre des classes
- Entraînement de modèles de Machine Learning
- Évaluation via métriques adaptées (Recall, F1-score)

---

## ⚙️ Models

Plusieurs modèles de classification ont été testés :

- Logistic Regression  
- Random Forest  
- K-Nearest Neighbors (KNN)  
- Gradient Boosting  

Optimisation des hyperparamètres pour améliorer les performances.

---

## 📊 Evaluation

Focus sur le **recall** afin de minimiser les faux négatifs  
(clients prédits comme fidèles mais qui churn réellement).

---

## 🧱 Pipeline

```text
Data → Preprocessing → Feature Engineering → Modeling → Evaluation
