# Customer Segmentation Analysis for AI Gardening Robot Startup Idea
## Brief Description
This customer segmentation analysis investigates the target market for an innovative AI gardening robot, utilizing Google Trends, social media, and web search data. It aims to identify desired features and real-world problems and needs to inform prototype design and define distinct audience segments interested in the prototype and its total addressable market. This will ensure a user-centric prototype and enable the startup to capitalize on market opportunities while reducing the risk of wasted resources.
## Table of Contents 
1. [Project Overview](#project-overview)
2. [Data](#data)
3. [Notebooks](#notebooks)
4. [Dependencies](#dependencies)
5. [How to Run](#how-to-run)
6. [Results & Insights](#results--insights)
7. [Future Work](#future-work)
8. [Contributing & License](#contributing--license)
9. [Contact](#contact)

## Project Overview
### Motivation & Context 
This project aims to validate the market potential for a proposed portable, AI-driven gardening robot designed to promote sustainable gardening practices through environmental understanding. The primary objective is to identify and understand target customer segments, their needs, and behaviors to determine the viability of this innovative product. If considered viable, these insights will further inform prototype design and marketing strategy. 

Conducting a customer segmentation analysis aims to mitigate the risk of developing a product that lacks a significant audience. The insights gained will guide the creation of a user-centric prototype that effectively addresses current customer needs.
### Project Steps
1. **Initial Keyword Research & Refinement**
* Three keyword lists will serve as the starting point for the first analysis step, one encompassing potential features of the prototype, another focusing on   the problems it could solve, and the third highlighting the needs it could address. 
* Google Trends data will be utilized to analyze search interest trends for all initial keyword ideas, identifying those with significant audience interest.    This ensures a user-centric design process, resulting in a refined set of the most relevant keywords across the features, problems, and needs groups.

2. **Data Collection From Online Sources**
* The selected keywords will be used as inputs into APIs like social media APIs and the Google JSON Custom Search API to gather data from relevant online sources, such as social media platforms, forums, articles, and (competitor-) websites. This process will output a large collection of raw textual data and associated metadata.

3. **Feature Extraction & Feature Engineering** 
* Feature extraction techniques will be applied to analyze the context of keyword mentions within the collected semi-structured data. This analysis aims to reveal audience characteristics, motivations, and preferences. 
* The insights gained will then be used for feature engineering, creating a structured table that defines distinct audience groups and their key characteristics. This will facilitate effective customer segmentation.

4. **Clustering-Based Customer Segmentation Analysis**
* A clustering algorithm will be utilized to segment the audience into distinct groups based on shared attributes and preferences. These customer segments will then serve as the foundation for a succeeding market opportunity analysis (TAM estimation).

## Data
## Data Sources

1. **Three initial keyword lists**
    - Proposed features.
    - Proposed problems to solve.
    - The proposed needs to address.
2. **Google Trends Data** 
    - Interest over the last three years for all initial keywords.
    - Search suggestions for highly relevant keywords.
    - Nested dictionary of Google Search categories.
3. **Social Media API Data** 
    - Semi-structured JSON data (metadata, textual content).
4. **Google Custom Search API Data**
    - Semi-structured JSON data (metadata, HTML content).
## Data Collection Challenges

1. **Pytrends API** 
    - As Google is the most used search engine, Google Search trends most accurately mirror what the world finds relevant at any given time. People turn to Google first when they're curious about something; their curiosity is derived from a perception of relevance. Thus, Google Trends data most accurately reflects worldwide interest over time. There is no official API to retrieve Google Trends data, so the unofficial Pytrends library was used for data retrieval.
    - The `interest_over_time` method currently faces issues due to changes on the Google Trends side. Although more recent data would be ideal, the available data (June 2020 - June 2024) is likely still representative of current trends.
    - If the API method issue gets resolved, I will update the analysis with the current data.

## Notebooks
## Project Status
This project is currently **in progress**. This section will outline the existing notebooks and provide an overview of the notebooks that are planned for future development.

## Current Notebooks

- **`01_google_trends_collection_cleaning__eda.ipynb`:** This notebook focuses on collecting Google Trends data, cleaning it, and conducting exploratory data analysis (EDA) to gain initial insights.
    - Collects, cleans, and transforms Google Trends data (Pandas DataFrames) for predefined keywords, ensuring data quality and readiness for analysis.
    - Conducts in-depth EDA, including visualizations and trend exploration, before storing the processed DataFrames in GCS for further use.
- **`02_google_trends_analysis.ipynb`:** This notebook focuses on the in-depth analysis of Google Trends data to identify keywords with significant audience interest.
    - Analyzes and visualizes interest trends, explores search context of the most relevant keywords, and evaluates keyword significance for further analysis, market understanding, and prototype development.
    - Recommends keywords to prioritize in further data collection and outlines intermediary analysis steps for keywords with insufficient or uncertain relevance to inform their inclusion in subsequent data collection.
## Future Notebooks

- **Data Collection from Online Sources:** Multiple notebooks will be dedicated to collecting, cleaning, exploring, and transforming data using various APIs (social media and search results) using refined keywords. Each online source will have a dedicated notebook, and the final processed data will be stored in GCS for future analysis.
- **Feature Extraction & Engineering:** This notebook will focus on extracting relevant features from the textual data and metadata collected from various online sources (social media and search results). It will also involve engineering new features and creating a structured table to represent hypothesized distinct audience groups and their characteristics. This structured table will be stored in Google Cloud Storage (GCS) for subsequent analysis.
- **Clustering-Based Customer Segmentation:** his notebook will employ a clustering algorithm on the structured table from the previous step. The aim is to validate the hypothesized audience groups and refine them into distinct customer segments based on shared attributes and preferences as identified by the clustering algorithm. The output of this process will be well-defined customer segments, each with its own unique characteristics.

## Dependencies

## How to Run

## Results & Insights

## Future Work

## Contributing & License

## Contact

