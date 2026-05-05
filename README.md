# 🎮 Steam — Analyse Big Data pour Ubisoft

> *Analyser des millions de données de la plateforme Steam avec PySpark sur Databricks pour aider Ubisoft à mieux comprendre le marché du jeu vidéo*

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python)](https://www.python.org/)
[![PySpark](https://img.shields.io/badge/PySpark-Big%20Data-E25A1C?logo=apachespark)](https://spark.apache.org/)
[![Databricks](https://img.shields.io/badge/Databricks-Platform-FF3621?logo=databricks)](https://databricks.com/)
[![AWS S3](https://img.shields.io/badge/AWS-S3-FF9900?logo=amazonaws)](https://aws.amazon.com/s3/)

---

## 🎯 Objectif

Analyser le catalogue Steam à grande échelle pour répondre aux questions stratégiques d'Ubisoft : quels genres performent le mieux, quel est le sweet spot de prix, quels éditeurs dominent le marché en satisfaction utilisateur ?

---

## 📊 Résultats clés

| Indicateur | Valeur |
|---|---|
| Jeux analysés | ~50 000 |
| Avis utilisateurs traités | ~10 millions |
| Genres les mieux notés | Action, RPG, Indie |
| Prix médian des jeux bien notés | ~15€ |
| Part des jeux gratuits | ~25% |

> Les jeux **multi-plateformes** obtiennent **+12%** d'avis positifs. Le sweet spot de prix : **entre 10€ et 20€**.

---

## 🗂️ Structure du projet

```
steam/
├── data/
│   └── steam_games.json              # Dataset brut (extrait S3)
├── notebooks/
│   ├── 01_eda_pyspark.ipynb          # Analyse exploratoire avec PySpark
│   └── 02_insights_ubisoft.ipynb     # Insights stratégiques pour Ubisoft
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🧠 Features analysées

| Feature | Description |
|---|---|
| `name` | Nom du jeu |
| `genres` | Genres (Action, RPG, Indie...) |
| `positive_ratings` | Nombre d'avis positifs |
| `negative_ratings` | Nombre d'avis négatifs |
| `price` | Prix en USD |
| `publisher` | Éditeur |
| `release_date` | Date de sortie |
| `platforms` | Windows / Mac / Linux |

---

## 📈 Insights clés pour Ubisoft

- Les **RPG et jeux d'action** ont le meilleur ratio avis positifs parmi les AAA
- Les jeux **multi-plateformes** obtiennent **+12%** d'avis positifs
- **Ubisoft** se positionne dans le top 10 par volume, mais sous la médiane en satisfaction
- Les studios **indépendants** surpassent les grands éditeurs en score utilisateur

---

## ⚙️ Installation

```bash
git clone https://github.com/MartialBayom/steam-ubisoft-analysis.git
cd steam-ubisoft-analysis
pip install -r requirements.txt
# PySpark nécessite Java 8+
jupyter notebook notebooks/01_eda_pyspark.ipynb
```

---

## 🏗️ Infrastructure

```
AWS S3 (dataset JSON ~5GB)
        ↓
Databricks (cluster PySpark)
        ↓
EDA Big Data (PySpark DataFrames, Spark SQL)
        ↓
Agrégations & Insights
        ↓
Présentation Ubisoft
```

---

## 👤 Auteur

| | Nom | Rôle |
|---|---|---|
| 🧑‍💻 | **Martial BAYOM** | Data Science |

Projet réalisé dans le cadre de la **certification Jedha AI School** (RNCP Niveau 6)

---

## 📂 Sources

| Dataset | Source |
|---|---|
| Steam Games Dataset | AWS S3 — Jedha AI School |
