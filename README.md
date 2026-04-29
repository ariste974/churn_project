📊 NPS Prediction 
Description
Projet de prédiction du Net Promoter Score (NPS) de clients  à partir de verbatims post-contact et de données structurées. Le modèle prédit la loyauté client (score 0–10) en combinant analyse textuelle des commentaires et variables comportementales/contextuelles.

📁 Structure du projet
├── notebook.ipynb   # Notebook principal (EDA, preprocessing, modélisation)
└── db.sqlite        # Base de données SQLite

🗃️ Dataset
Base SQLite contenant 38 303 contacts clients avec les variables suivantes :
ColonneDescriptioncsatScore de satisfaction (1–5)npsScore NPS (0–10) — variable ciblecommentaireVerbatim libre du clientoffer_labelOffre Freebox souscritecanalCanal de contactnom_region / nom_departementLocalisationid_conseillerIdentifiant conseiller (0 si selfcare)date_contactDate du contact

🔄 Pipeline
1. Exploration (EDA)

Distribution des scores CSAT et NPS
Analyse géographique par région (carte choroplèthe via GeoJSON)
CSAT moyen par canal et par offre
Corrélation CSAT / NPS

2. Preprocessing

Nettoyage des valeurs manquantes et des marqueurs \N
Conversion des types (date_contact, nps)
Suppression de csat pour éviter le data leakage
Nettoyage des verbatims : stopwords, émojis, ponctuation, accents

3. Feature Engineering

TF-IDF sur les commentaires
One-Hot Encoding des variables catégorielles
Standardisation des variables numériques

4. Modélisation
Machine Learning
ModèleMAER²Random Forest1.770.39XGBoost1.700.49
Deep Learning (architecture hybride texte + catégoriel + numérique)
ModèleMAER²CNN1.510.56BiLSTM1.690.53

🛠️ Stack technique

Data — pandas, numpy, SQLite
Visualisation — matplotlib, seaborn, plotly
NLP — nltk, spaCy, TF-IDF, unidecode
ML — scikit-learn, XGBoost
Deep Learning — TensorFlow / Keras


🚀 Installation
bashpip install pandas numpy matplotlib seaborn plotly scikit-learn xgboost tensorflow nltk spacy unidecode emoji
python -m spacy download fr_core_news_sm
jupyter notebook notebook.ipynb

📈 Résultats
Le CNN est le modèle le plus performant (R² = 0.56, MAE = 1.51). Les erreurs se concentrent sur ±1 à 2 points sur une échelle de 10, ce qui permet de distinguer efficacement les clients satisfaits des insatisfaits.
Pistes d'amélioration : tuning des hyperparamètres, ajout de features temporelles, expérimentation avec CamemBERT pour mieux exploiter les verbatims en français.

