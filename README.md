📈 Predicting Stock Price Movement Using News Sentiment

This project explores whether news sentiment can help indicate or predict stock price movements. Using a combined dataset containing news headlines, publication dates, publishers, URLs, and stock identifiers, this analysis performs sentiment scoring, aggregates the scores over time, and visualizes overall sentiment trends.

🗂️ Project Overview

Financial markets are heavily influenced by news — headlines about earnings, warnings, product launches, lawsuits, and market conditions can all affect investor behavior.
This project demonstrates how to:

Clean and preprocess mixed-format timestamp data

Extract daily dates from news items

Apply a simple sentiment scoring model to headlines

Aggregate sentiment by day

Visualize sentiment trends

Perform a basic time-series decomposition (trend, seasonality, residuals)

The workflow is designed to show how natural language information can be transformed into meaningful numerical signals.

📁 Dataset Description

The dataset contains the following columns:

Column	Description
headline	The news headline text
URL	Source link for the article
publisher	News publisher name
date	Date/time the article was published (mixed formats)
stock	Stock ticker mentioned in the headline

All records are stored in a single CSV file.

🧹 Data Preprocessing

The project performs the following preprocessing steps:

Strip whitespace from date strings

Convert mixed-format dates using pd.to_datetime(..., errors='coerce', utc=True)

Extract just the date (YYYY-MM-DD) from the full timestamp

Drop rows with invalid or unparseable dates

🧪 Sentiment Analysis

A simple rule-based sentiment model assigns:

+1 for each positive keyword

–1 for each negative keyword

Positive examples: up, gain, growth, profit, surge
Negative examples: down, fall, loss, drop, decline

The result is stored in a new column: sentiment.

This is not a full NLP model — but it is intentionally simple to show how sentiment scoring works conceptually.

📊 Analysis & Visualization
Daily Sentiment

The code aggregates average sentiment values per day across all stocks.

Visualizations include:

Line plot of daily sentiment over time

Time series decomposition (trend, seasonal pattern, residual noise)

These help illustrate whether sentiment follows any noticeable directional patterns.

🧾 Code Used

The full processing pipeline includes:

pandas for data handling

matplotlib for plotting

statsmodels for time series decomposition