# 🛒 ERP Intelligent : Prédiction de Demande et Optimisation des Stocks
**Projet Master 1 - Systèmes d'Information (IA et Business Intelligence)**

Ce projet implémente un module ERP Intelligent conçu pour automatiser les décisions de réapprovisionnement. En s'appuyant sur des données de ventes réelles, l'IA prédit la demande future, estime les risques de rupture et recommande les quantités optimales de commande.

---

## 📊 Dataset : Corporación Favorita (Kaggle)
Le projet utilise désormais un jeu de données réel provenant de la chaîne équatorienne **Corporación Favorita** (données de 2013 à 2017).
- **Volume :** Plus de 125 millions d'enregistrements (échantillonnés pour ce prototype).
- **Richesse :** 54 magasins, des dizaines de villes et des milliers d'articles enrichis de métadonnées (`stores.csv`, `items.csv`, `holidays_events.csv`).
- **Lien :** [Favorita Grocery Sales Forecasting](https://www.kaggle.com/competitions/favorita-grocery-sales-forecasting)

---

## 🚀 Fonctionnalités Clés
- **Modélisation Avancée (XGBoost) :** Un modèle Gradient Boosting capable de capter les relations non-linéaires complexes.
- **Analyse de Saisonnalité :** Détection automatique des cycles hebdomadaires (pics le week-end).
- **Facteur Événementiel :** Intégration des **jours fériés** pour prévenir les ruptures lors des pics de consommation.
- **Interfaces Interactives :**
  - **Dashboard (Streamlit) :** Analyse historique et exploration des tendances.
  - **Predictor (Gradio) :** Outil opérationnel de prédiction en temps réel avec calendrier intégré.

---

## 🛠️ Installation et Utilisation

### 1. Prérequis
- Python 3.8+
- Un environnement virtuel recommandé :
  ```bash
  python -m venv venv
  venv\Scripts\activate
  ```

### 2. Installation des dépendances
```bash
pip install -r requirements.txt
```

### 3. Lancement des modules
- **Analyse Exploratoire (EDA) :** Consulter `notebooks/01_EDA.ipynb`.
- **Entraînement :** `python src/train_model.py` (pour ré-entraîner le modèle sur les dernières données).
- **Dashboard :** `streamlit run src/dashboard.py`
- **Predictor :** `python src/predictor.py`

---

## 🏢 Architecture du Projet
```text
erp_ai_stock_prediction/
├── data/                   # Fichiers sources (train.csv, metadata)
├── models/                 # Modèles IA sauvegardés (.pkl)
├── notebooks/              # Analyse exploratoire (EDA - Semaine 1)
├── src/                    # Code source (Dashboard, Predictor, Train)
├── IA_Justifications.md    # Documentation scientifique et choix techniques
├── requirements.txt        # Liste des dépendances
└── README.md               # Ce fichier
```

### 📄 Fichiers Clés
- **`src/train_model.py`** : Moteur d'entraînement (MAE: 7.60).
- **`src/dashboard.py`** : Visualisation analytique pour les décideurs.
- **`src/predictor.py`** : Outil terrain pour les magasiniers (Génère l'alerte rupture).
- **`IA_Justifications.md`** : Justification académique des métriques (MAE, RMSE, MAPE).

---

## 👨‍🎓 Contexte Académique
Ce travail a été réalisé dans le cadre d'un Master 1 SI. Il démontre la capacité d'une Intelligence Artificielle à s'intégrer dans un processus métier classique (ERP) pour apporter une valeur ajoutée quantifiable (réduction des invendus et des ruptures).
