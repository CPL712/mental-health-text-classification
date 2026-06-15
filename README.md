# 🧠 Mental Health Text Classification

An end-to-end Natural Language Processing (NLP) project comparing a Bidirectional LSTM baseline with a fine-tuned DistilBERT transformer for multi-class mental health text classification.

Developed as part of the **Applied Artificial Intelligence Postgraduate Program** at **George Brown College**, this project demonstrates the complete machine learning workflow, including data preprocessing, exploratory data analysis, deep learning model development, evaluation, model comparison, and deployment with Streamlit.
> *(Project workflow image will be added here.)*

## 📌 Project Overview

Mental health professionals and researchers often work with large volumes of unstructured text collected from online forums, surveys, and social platforms. Manual analysis is time-consuming and difficult to scale.

This project investigates how deep learning can automatically classify mental health-related text into seven categories by comparing two modern Natural Language Processing approaches:

- Bidirectional Long Short-Term Memory (BiLSTM)
- DistilBERT Transformer

The project follows an end-to-end machine learning pipeline from exploratory data analysis and preprocessing through model training, evaluation, comparison, and deployment using Streamlit.

## 📂 Dataset

**Source**

Kaggle – Sentiment Analysis for Mental Health

https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health

### Dataset Summary

- Over 53,000 labelled text statements
- Seven mental health categories
- English language
- Multi-class classification problem

### Categories

- Anxiety
- Bipolar
- Depression
- Normal
- Personality Disorder
- Stress
- Suicidal

> **Note:** The dataset is not included in this repository. Please download it directly from Kaggle and place `raw_data.csv` under `data/raw/`.

## 🎯 Objectives

- Perform exploratory data analysis on mental health text data.
- Build a Bidirectional LSTM baseline model.
- Fine-tune a DistilBERT transformer model.
- Compare deep learning architectures for multi-class text classification.
- Evaluate models using standard classification metrics.
- Deploy the final solution through a Streamlit web application.

## 🔄 Project Workflow

```

Kaggle Dataset

↓

Exploratory Data Analysis

↓

Text Cleaning

↓

Tokenization

↓

Model Development

├── Bidirectional LSTM

└── DistilBERT

↓

Model Evaluation

↓

Performance Comparison

↓

Streamlit Deployment

```
