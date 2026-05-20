# 📦 **Amazon Sales Data Analysis — Nettoyage, Filtrage & Agrégation**

Ce projet consiste à analyser un dataset de ventes Amazon afin d’en extraire des **insights clés** sur les ventes, les catégories, les statuts de commande et les modes d’expédition.
Réalisé dans un **cadre personnel d’apprentissage**, il met en pratique des compétences essentielles en **data analysis**, **pandas**, **data cleaning** et **exploration statistique**.


## 🎯 Objectifs du projet

* Nettoyer et préparer un dataset de ventes Amazon
* Comprendre la répartition des ventes par catégories et montants
* Identifier des patterns dans les quantités, les statuts et les livraisons
* Générer des agrégations pertinentes pour la prise de décision
* Exporter des résultats dans des fichiers Excel pour une analyse ultérieure


## 🧰 Stack Technique

* **Python**
* **Pandas** pour le nettoyage, slicing, filtrage et agrégation
* **Excel** pour l’import/export des données
* **Jupyter / IDE Python (Eclipse/PyCharm/VSCode)**
* Visualisation possible via Excel ou outils BI


## 📝 Questions auxquelles le projet répond

* Combien de ventes ont un **montant supérieur à 1000** ?
* Combien de ventes appartiennent à la **catégorie "Tops"** et ont une **quantité de 3** ?
* Quel est le **total des ventes par catégorie** ?
* Quel est le **montant moyen** par catégorie en fonction du statut ou du mode de fulfilment ?
* Quel est le **total des ventes** selon :

  * le statut d’expédition
  * le type de fulfilment
  * la combinaison des deux


## 🔍 Analyse effectuée

### 🧹 1. Nettoyage des données

* Vérification de valeurs manquantes
* Suppression des lignes contenant des `NaN`
* Nettoyage ciblé sur la colonne `Amount`

### 🔎 2. Exploration & slicing

* Filtrage par catégorie (`Category == "Top"`)
* Filtrage sur condition (`Amount > 1000`)
* Multi-conditions :

  ```python
  filtered_data = sales_data[(sales_data['Category'] == 'Top') & (sales_data['Qty'] == 3)]
  ```

### 📊 3. Agrégation

* Total des ventes par **Category**
* Moyenne des montants par **Category + Fulfilment**
* Moyenne des montants par **Category + Status**
* Total des ventes par **Shipment + Fulfilment**

### 📤 4. Export des résultats

* Export des agrégations en Excel :

  * `average_sales_by_category_and_status.xlsx`
  * `total_sales_by_ship_and_fulfil.xlsx`


## 📂 Structure du projet

```
amazon_sales_analysis/
 ├── sales_data.xlsx                         # Dataset source
 ├── amazon_sales_analysis.py                # Script principal (ton code)
 ├── average_sales_by_category_and_status.xlsx
 ├── total_sales_by_ship_and_fulfil.xlsx
 └── README.md
```


## 🧠 Compétences démontrées

- ✔ Nettoyage et préparation de données
- ✔ Manipulation de DataFrames pandas
- ✔ Filtrage & slicing avancé
- ✔ Agrégations multi-indexes (groupby)
- ✔ Exportation des résultats pour reporting
- ✔ Exploration structurée des données
- ✔ Analyse des tendances de ventes (catégories, quantités, statuts, expédition)


## 🚀 Exemple de code clé

### Total des ventes par catégorie :

```python
category_totals = sales_data.groupby('Category', as_index=False)['Amount'].sum()
category_totals.sort_values('Amount', ascending=False)
```

### Moyenne des montants par catégorie et statut :

```python
status_averages = sales_data.groupby(['Category', 'Status'], as_index=False)['Amount'].mean()
```


## 🔧 Améliorations possibles

* Ajouter de la visualisation (Matplotlib, Seaborn, Plotly)
* Construire un dashboard Power BI / Tableau
* Ajouter une détection d’anomalies (montants extrêmes, valeurs incohérentes)
* Automatiser l’analyse via un script CLI
* Intégrer un pipeline ETL (extraction → nettoyage → analyse → export)


## 👤 À propos

Projet réalisé par **Alex Alkhatib**, passionné par la data, l’analyse et la transformation de datasets en insights utiles.


## 📄 Licence
MIT License
Copyright (c) 2025 Alex Alkhatib
