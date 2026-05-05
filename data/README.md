# 📦 Données Steam

Les données sont stockées sur AWS S3 (trop volumineuses pour Git) :

```
s3://full-stack-bigdata-datasets/Big_Data/Project_Steam/steam_game_output.json
```

## Accès

```python
# Depuis Databricks ou avec boto3
spark.read.json("s3://full-stack-bigdata-datasets/Big_Data/Project_Steam/steam_game_output.json")
```
