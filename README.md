INTRODUCTION

This project uses SQL (MySQL) to clean, standardize, and analyze a global layoffs dataset.
The objective was to transform raw, inconsistent data into a table ready for analysis and extract insights related to company layoffs, industry impact, and time trends.

The project simulates a real-world data analyst workflow, focusing on data quality, accuracy, and exploratory analysis using advanced SQL techniques.


DATASET

Global company layoffs data

Includes company, industry, location, layoff counts, layoff percentages, funding, and dates

Raw data contained duplicates, inconsistent text formatting, missing values, and typed dates not imputed properly


DATA CLEANING WORKFLOW

. Created Staging Tables

. Preserved raw data by working in staging tables

. Ensured transformations did not affect original records


REMOVED DUPLICATE RECORDS

Identified duplicates using ROW_NUMBER() with PARTITION BY

Removed all duplicate rows while retaining one clean record per entry

Techniques used:
Window functions, CTEs


STANDARDIZED TEXT DATA

. Trimmed extra spaces from company names

. Normalized inconsistent industry labels (e.g., crypto variations)

. Cleaned country names by removing trailing punctuation


DATE FORMATTING AND DATA TYPES

. Converted date strings into proper DATE format

. Modified column data types for time-based analysis


HANDLED MISSING AND NULL VALUES

. Converted blank strings to NULL

. Filled missing industry values using self-joins on company names

. Removed rows with no meaningful layoff data


FINAL CLEANUP

. Dropped helper columns used during deduplication

. Produced a clean table ready for analysis


EXPLORATORY DATA ANALYSIS (EDA)

Key Analyses Performed

. Total layoffs by company

. Companies with 100% workforce layoffs

. Layoffs by year and month

. Rolling cumulative layoffs over time

. Layoffs by company stage

. Top 5 companies with the most layoffs per year

Techniques used:
GROUP BY, ORDER BY, SUM(), YEAR(),
DENSE_RANK(), window functions.


KEY INSIGHTS

. Layoffs were highly concentrated during specific economic periods

. A small number of companies accounted for a large share of total layoffs

. Several companies experienced complete shutdowns (100% layoffs)

. Rolling totals showed rapid accumulation of layoffs during peak periods
