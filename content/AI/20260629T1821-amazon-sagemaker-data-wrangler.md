---
created: 2026-06-29 18:21
modified: 2026-06-29 18:22
tags:
  - AI
  - AWS
  - AIF-C01
title: Amazon SageMaker Data Wrangler
aliases: Amazon SageMaker Data Wrangler
publish: true
folder: AI
---

Dos notas atómicas para esta sección. La de Feature Engineering también la incluyo porque Maarek la introduce aquí y es conceptualmente separable.

---

# SageMaker Data Wrangler

## Main Concept

SageMaker Data Wrangler is a visual data preparation tool within SageMaker Studio. It allows you to prepare, transform, and engineer ML-ready features from tabular and image data — all from a single interface, without writing code.

> [!TIP] Key Idea
> 
> - **What it does** → data selection, cleansing, exploration, visualization, transformation, and feature engineering — in one place.
>     
> - **Who it's for** → anyone who needs to get data ready for ML before training starts.
>     
> - **Where it lives** → inside SageMaker Studio, not a standalone service.
>     

## What You Can Do In Data Wrangler

```
Data selection        → import data from Amazon S3 and other sources
Data cleansing        → fix missing values, wrong formats, bad rows
Data exploration      → visualize datasets with graphs to understand
                        what you're working with before choosing a model
Data transformation   → apply functions, drop or add columns,
                        reshape data for ML consumption
Feature engineering   → create new features from raw data
                        (e.g., extract age from birth date)
Data quality check    → detect missing data, format issues, column mismatches
Quick model analysis  → early check on whether the data will produce
                        a model that performs well
SQL support           → query and filter data using SQL
Export data flow      → export the entire transformation pipeline
                        so it can be reproduced automatically
```

> [!example] Example
> 
> You import a student dataset from S3. You notice the birth date column is a raw date string — not useful for a model. In Data Wrangler, you transform it into an Age column (a clean numeric value). You visualize the distribution of exam scores across age groups. You export the transformation flow so it runs automatically every time new data arrives.

## Keyphrase

```
"Visually prepare and transform data before training" → SageMaker Data Wrangler.
"Data exploration and visualization for ML" → SageMaker Data Wrangler.
"Check data quality before feeding it to a model" → SageMaker Data Wrangler.
"Anytime you need to transform data" → Data Wrangler (Maarek's exact words).
```

## Exam Scope

- Know Data Wrangler is for data preparation, transformation, and feature engineering.
- Know it includes data quality checking and visualization.
- Know it lives inside SageMaker Studio.
- Know it can export transformation flows for use in automated ML pipelines.
- Know it can publish features directly to SageMaker Feature Store.
- You do not need to know how to use the interface or write transformations.

## Exam Domain

- Domain 1, Task Statement 1.3: "Identify relevant AWS services for each stage of an ML pipeline" — Data Wrangler covers data pre-processing and feature engineering stages.

## Related Notes

- [[SageMaker Feature Store]]
- [[Feature Engineering]]
- [[Amazon SageMaker — Exam Summary]]
- [[Phases of a Machine Learning Project]]
- [[SageMaker Studio]]

---

