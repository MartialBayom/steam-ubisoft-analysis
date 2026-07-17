📓é👉—é«»ééàééééééé# Steam - Analyse Big Data pour Ubisoft

> *Analyser des millions de données de la plateforme Steam avec PySpark sur Databricks pour aider Ubisoft à mieux comprendre le marché du jeu vidéo*

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python)](https://www.python.org/)
[![PySpark](https://img.shields.io/badge/PySpark-Big%20Data-E25A1C?logo=apachespark)](https://spark.apache.org/)
[![Databricks](https://img.shields.io/badge/Databricks-Platform-FF3621?logo=databricks)](https://databricks.com/)
[![AWS S3](https://img.shields.io/badge/AWS-S3-FF9900?logo=amazonaws)](https://aws.amazon.com/s3/)

---

## Objectif

Analyser le catalogue Steam à grande échelle pour répondre aux questions stratégiques d'Ubisoft : quels genres performent le mieux, quel est le sweet spot de prix, quels éditeurs dominent le marché en satisfaction utilisateur ?

---

## Résultats clés

| Indicateur | Valeur |
|---|---|
| Jeux analysés | ~50 000 |
| Avis utilisateurs traités | ~10 millions |
| Genres les mieux notés | Action, RPG, Indie |
| Prix médian des jeux bien notés | ~15€ |
| Part des jeux gratuits | ~25% |

> Les jeux **multi-plateformes** obtiennent **+12%** d'avis positifs. Le sweet spot de prix : **entre 10€ et 20€**.

---

## Structure du projet

```
steam-ubisoft-analysis/
├── data/
│   └── README.md                                  # Chemin S3 vers le dataset (non versionné)
├── notebooks/
│   └── Steam_Analysis_Ubisoft_Project.ipynb        # EDA PySpark + insights stratégiques Ubisoft
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Features analysées

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

## Insights clés pour Ubisoft

- Les **RPG et jeux d'action** ont le meilleur ratio avis positifs parmi les AAA
- Les jeux **multi-plateformes** obtiennent **+12%** d'avis positifs
- **Ubisoft** se positionne dans le top 10 par volume, mais sous la médiane en satisfaction
- Les studios **indépendants** surpassent les grands éditeurs en score utilisateur

---

## Exécution

> Ce notebook utilise les variables `spark` et `display()` fournies automatiquement par
> l'environnement **Databricks**. Il ne s'exécute **pas** tel quel avec un simple `jupyter notebook`
> en local - il faut soit l'exécuter sur un cluster Databricks, soit adapter le code pour créer
> une `SparkSession` locale et remplacer `display()` par `.show()` / `.toPandas()`.

**Sur Databricks (recommandé) :**
```bash
git clone https://github.com/MartialBayom/steam-ubisoft-analysis.git
```
Importer `notebooks/Steam_Analysis_Ubisoft_Project.ipynb` dans un Workspace Databricks,
l'attacher à un cluster, puis exécuter.

**En local (nécessite une adaptation du notebook) :**
```bash
cd steam-ubisoft-analysis
pip install -r requirements.txt
# Java 8+ requis pour PySpark
# Ajouter en début de notebook :
#   from pyspark.sql import SparkSession
#   spark = SparkSession.builder.appName("steam-ubisoft").getOrCreate()
# Puis remplacer chaque display(df) par df.show() ou df.toPandas()
jupyter notebook notebooks/Steam_Analysis_Ubisoft_Project.ipynb
```

---

##  Infrastructure

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

##  Auteur

| | Nom | Rôle |
|---|---|---|
|  | **Martial BAYOM** | Data Science |

Projet réalisé dans le cadre de la **certification Jedha AI School** (RNCP Niveau 6)

---

## Sources

| Dataset | Source |
|---|---|
| Steam Games Dataset | AWS S3 — Jedha AI School |


---

## Notebook publié

Le notebook complet (analyse PySpark + visualisations Databricks) est consultable en ligne, sans compte requis :

 [Voir le notebook Steam_Analysis_Ubisoft (3) — version publiée](https://htmlpreview.github.io/?https://github.com/MartialBayom/steam-ubisoft-analysis/blob/main/Steam_Analysis_Ubisoft%20(3).html)

> Note : le bouton natif « Publish » de Databricks (réservé à la Community Edition) n'était pas disponible sur l'espace de travail utilisé pour ce projet. Le notebook a donc été exporté en HTML avec ses résultats puis publié via [htmlpreview.github.io](https://htmlpreview.github.io) pour rester consultable publiquement par le jury.
> 
