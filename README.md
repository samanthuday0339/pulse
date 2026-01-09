# Swiggy Review Trend Analysis using Agentic AI

This project implements an **agentic AI system** that ingests Swiggy Google Play Store reviews on a daily basis, intelligently consolidates semantically similar feedback into canonical topics, and generates a **rolling 30-day trend analysis report** for product teams.

The system is designed to achieve **high recall**, prevent topic fragmentation, and avoid traditional topic modeling approaches such as LDA or TopicBERT.

---

## Problem Statement

Product teams rely on user reviews to identify:
- Recurrent issues
- Feature requests
- Emerging trends

However, user feedback is noisy and often expressed in different ways for the same underlying issue.  
For example:

- *“Delivery guy was rude”*
- *“Delivery partner behaved badly”*
- *“Delivery person was impolite”*

If treated as separate topics, these create **inaccurate trends**.

This project solves this by using **agentic AI and taxonomy-based deduplication** to consolidate similar feedback into clean, canonical topics.

---

## Solution Overview

The pipeline consists of multiple **AI agents**, each responsible for a specific task:

1. **Data Ingestion Agent** – Extracts Swiggy reviews from the Google Play Store
2. **Daily Batching Agent** – Treats each calendar day as a separate batch
3. **Review Understanding Agent** – Converts raw text into high-recall semantic topic signals
4. **Topic Normalization Agent** – Deduplicates and consolidates similar topics
5. **Trend Aggregation Agent** – Builds a rolling 30-day topic trend table

This design ensures:
- High recall
- No duplicate categories
- Actionable trends for product teams

---

## Key Features

- Agentic AI approach (no LDA / TopicBERT)
- High-recall topic extraction
- Canonical topic normalization
- Automatic handling of new or emerging topics
- Rolling 30-day trend analysis
- Product-ready output format

---


---

## Notebook Description

### 01_data_ingestion.ipynb
- Extracts Swiggy reviews from Google Play Store
- Filters reviews from **June 1, 2024 onwards**
- Stores cleaned data as the source-of-truth dataset

### 02_daily_batching.ipynb
- Groups reviews by posting date
- Simulates real-world daily ingestion

### 03_understanding_agent.ipynb
- Implements a **high-recall review understanding agent**
- Classifies reviews into issues, requests, and feedback
- Avoids traditional topic modeling techniques

### 04_topic_normalization.ipynb
- Deduplicates semantically similar topic phrases
- Consolidates feedback into canonical topics
- Prevents topic explosion and trend fragmentation

### 05_trend_generation.ipynb
- Aggregates topic frequencies per day
- Generates a rolling **30-day trend table**
- Saves final report to `/output`

---

## Input and Output

### Input
- Google Play Store app link (Swiggy)
- Target date (derived from review timestamps)

### Output
A trend analysis table where:
- **Rows** → Canonical topics  
- **Columns** → Dates from T-30 to T  
- **Cells** → Frequency of topic occurrences  




