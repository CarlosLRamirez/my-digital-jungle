---
created: 2026-06-29 18:22
modified: 2026-06-29 18:22
tags:
  - AI
  - AWS
  - AIF-C01
title: Amazon SageMaker Feature Store
aliases: Amazon SageMaker Feature Store
publish: true
folder: AI
---

## Main Concept

SageMaker Feature Store is a centralized repository for storing, discovering, and reusing ML features across datasets, teams, and models within a company. Instead of each team independently computing the same features, Feature Store makes them available company-wide.

> [!TIP] Key Idea
> 
> - **Problem it solves** → features computed by one team are invisible to others, leading to duplicated work and inconsistency.
>     
> - **Solution** → one central place where all features are stored, documented, and discoverable by everyone.
>     
> - **Key benefit** → reuse across multiple ML models and teams without recomputing.
>     

## How It Works

```
Ingest features      → from a variety of data sources or directly
                       from SageMaker Data Wrangler
Describe features    → each feature has a name and description
                       so others know what it represents
Discover features    → searchable inside SageMaker Studio
                       any team member can find and reuse existing features
Define transforms    → transformations can be defined directly
                       inside Feature Store
Reuse at scale       → features used for training are the same ones
                       used for inference — consistency guaranteed
```

> [!example] Example
> 
> A music streaming company has multiple ML teams. Team A computes "average listening duration per user" for their churn model. Without Feature Store, Team B recomputes the same feature from scratch for their recommendation model. With Feature Store, Team A publishes the feature once — Team B discovers and reuses it immediately. Same feature, zero duplicated work.

## Keyphrase

```
"Store and reuse ML features across models or teams" → SageMaker Feature Store.
"Centralized feature repository" → SageMaker Feature Store.
"Discover features across the company" → SageMaker Feature Store.
```

## Exam Scope

- Know Feature Store is for storing and reusing features across models and teams.
- Know features are discoverable inside SageMaker Studio.
- Know Data Wrangler can publish features directly into Feature Store.
- Know features are used for both training AND inference — consistency is the key value.
- You do not need to know how to configure or query Feature Store technically.

## Exam Domain

- Domain 1, Task Statement 1.3: "Identify relevant AWS services for each stage of an ML pipeline" — Feature Store sits between feature engineering and model training.

## Related Notes

- [[SageMaker Data Wrangler]]
- [[Feature Engineering]]
- [[Amazon SageMaker — Exam Summary]]
- [[SageMaker Studio]]
- [[Phases of a Machine Learning Project]]

---

# Feature Engineering

## Main Concept

Feature engineering is the process of transforming raw data into features — the actual input variables a model uses to learn. The quality of your features directly determines the quality of your model. Good features carry predictive signal; bad features introduce noise or bias.

> [!TIP] Key Idea
> 
> - **Raw data** → rarely usable directly by an ML model.
>     
> - **Feature engineering** → transforms raw data into a form the model can actually learn from.
>     
> - **Better features = better model** — this is one of the highest-leverage steps in any ML project.
>     

## Examples

```
Raw data               → Engineered feature
─────────────────────────────────────────────
Birth date (string)    → Age (integer)
Song play timestamp    → Listening duration (minutes)
User profile data      → Listener demographics (categories)
Raw text review        → Sentiment score (0–1)
Football player data   → Goals per training hour ratio
```

> [!example] Why birth date → age matters
> 
> A model cannot learn from "1990-04-15" as a string. It can learn from "34" as an integer. Age has a logical relationship to the prediction target. The raw date does not. Feature engineering makes the signal usable.

> [!TIP] Key Idea: Good feature vs bad feature
> 
> - **Good feature** → has a logical relationship to what you are predicting. "Hours of training" predicts "goals scored."
>     
> - **Bad feature** → no predictive relationship, adds noise. "Birth month" does not predict "goals scored."
>     

## Where It Happens in AWS

```
SageMaker Data Wrangler  → create and transform features visually
SageMaker Feature Store  → store and reuse features across models and teams
```

## Exam Scope

- Know feature engineering transforms raw data into model-ready input variables.
- Know good features have predictive power; bad features add noise or bias.
- Know Data Wrangler and Feature Store are the AWS tools for this stage.
- This maps to the feature engineering stage of the ML pipeline in Domain 1 Task 1.3.

## Exam Domain

- Domain 1, Task Statement 1.3: Feature engineering is an explicit component of the ML pipeline.
- Domain 4, Task Statement 4.1: Poor feature choice can introduce bias — exam connects feature quality to responsible AI.

## Related Notes

- [[SageMaker Data Wrangler]]
- [[SageMaker Feature Store]]
- [[Phases of a Machine Learning Project]]
- [[Responsible AI]]
- [[Bias and Variance]]

