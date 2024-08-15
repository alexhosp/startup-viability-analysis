# Customer Segmentation Analysis for Startup Idea
## Brief Description
This customer segmentation analysis investigates the target market for an innovative AI gardening robot, utilizing Google Trends, social media, and web search data. It aims to identify desired features and real-world problems and needs to inform prototype design and define distinct audience segments interested in the prototype and its total addressable market. This will ensure a user-centric prototype and enable the startup to capitalize on market opportunities while reducing the risk of wasted resources.
## Table of Contents 
1. [Project Overview](#project-overview)
2. [Data](#data)
3. [Notebooks](#notebooks)
4. [Dependencies](#dependencies)
5. [How to Run](#how-to-run-colab-notebooks)
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
* The insights gained will then be used for feature engineering, creating a structured table that defines distinct hypothesized audience groups and their key characteristics. This will facilitate effective customer segmentation.

4. **Clustering-Based Customer Segmentation Analysis**
* A clustering algorithm will be utilized to segment the audience into distinct groups based on shared attributes and preferences. These customer segments will then serve as the foundation for a succeeding market opportunity analysis (TAM estimation).

## Data
### Data Sources

1. **Three initial keyword lists**
    - Proposed prototype features.
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
### Data Collection Challenges

1. **Pytrends API** 
    - As Google is the most used search engine, Google Search trends most accurately mirror what the world finds relevant at any given time. People turn to Google first when they're curious about something; their curiosity is derived from a perception of relevance. Thus, Google Trends data most accurately reflects worldwide interest over time. There is no official API to retrieve Google Trends data, so the unofficial Pytrends library was used for data retrieval.
    - The `interest_over_time` method currently faces issues due to changes on the Google Trends side. Although more recent data would be ideal, the available data (June 2020 - June 2024) is likely still representative of current trends.
    - Currently, running the notebooks using this API may result in intermittent 429 errors due to ongoing issues on the Google Trends side. For more details, please refer to  [Pytrends Issue #625](https://github.com/GeneralMills/pytrends/issues/625).
    - If the API functionality stabilizes, the analysis will be updated with the most current data.

## Notebooks
### Project Status
This project is currently **in progress**. This section will outline the existing notebooks and provide an overview of the notebooks that are planned for future development.

### Current Notebooks

- [**`01_google_trends_collection_cleaning__eda.ipynb`:**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/notebooks/01_google_trends_collection_cleaning__eda.ipynb) This notebook focuses on collecting Google Trends data, cleaning it, and conducting exploratory data analysis (EDA) to gain initial insights.
    - Collects, cleans, and transforms Google Trends data (Pandas DataFrames) for predefined keywords, ensuring data quality and readiness for analysis.
    - Conducts in-depth EDA, including visualizations and trend exploration, before storing the processed DataFrames in GCS for further use.
- [**`02_google_trends_analysis.ipynb`:**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/notebooks/02_google_trends_analysis.ipynb)This notebook focuses on the in-depth analysis of Google Trends data to identify keywords with significant audience interest.
    - Analyzes and visualizes interest trends, explores search context of the most relevant keywords, and evaluates keyword significance for further analysis, market understanding, and prototype development.
    - Recommends keywords to prioritize in further data collection and outlines intermediary analysis steps for keywords with insufficient or uncertain relevance to inform their inclusion in subsequent data collection.
### Future Notebooks

- **Data Collection from Online Sources:** Multiple notebooks will be dedicated to collecting, cleaning, exploring, and transforming data using various APIs (social media and search results) using refined keyword lists. Each online source will have a dedicated notebook, and the final processed data will be stored in GCS for future analysis.
- **Feature Extraction & Engineering:** This notebook will focus on extracting relevant features from the textual data and metadata collected from various online sources (social media and search results). It will also involve engineering new features and creating a structured table to represent hypothesized distinct audience groups and their characteristics. This structured table will be stored in Google Cloud Storage (GCS) for subsequent analysis.
- **Clustering-Based Customer Segmentation:** his notebook will employ a clustering algorithm on the structured table from the previous step. The aim is to validate the hypothesized audience groups and refine them into distinct customer segments based on shared attributes and preferences as identified by the clustering algorithm. The output of this process will be well-defined customer segments, each with its own unique characteristics.

## Dependencies
- [**`01_google_trends_collection_cleaning__eda.ipynb`**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/notebooks/01_google_trends_collection_cleaning__eda.ipynb)
    - `pandas==2.1.4`
    - `requests==2.32.3`
    - `pytrends==4.9.2`
    - `urllib3==1.25.11`
    - `seaborn==0.13.1`
    - `matplotlib==3.7.1`
- [**`02_google_trends_analysis.ipynb`**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/notebooks/02_google_trends_analysis.ipynb)
    - `pandas==2.1.4`
    - `pytrends==4.9.2`
    - `urllib3==1.25.11`
    - `scipy==1.13.1`
    - `seaborn==0.13.1`
    - `matplotlib==3.7.1`
    - `numpy==1.26.4`
    - `holoviews==1.18.3`

## How to Run Colab Notebooks
1. Make sure you're logged into your Google account.
2. Click on the provided *Open in Colab* links to open the notebooks in Google Colab.
3. If prompted, install the Colab extension.
4. Allow a few seconds for the notebook to connect to a runtime environment.
5. If prompted to restart the runtime to install the necessary libraries, please do so. After restarting, you'll need to re-run all the cells in the notebook from the beginning. You can do this quickly by clicking the first cell and pressing **`Ctrl-F10`**.
6. Execute the cells in each notebook sequentially from top to bottom using the "Run" button or the keyboard shortcut (**`Shift+Enter`**).

## Results & Insights
### Project Status

This section presents the findings and insights gathered so far in the analysis. **As the project evolves, this section will be updated** to reflect further developments and a more comprehensive understanding of the target audience and market opportunity.
### Google Trends Analysis

#### Key  Results

- The analysis identified several **promising keywords** with high interest or significant growth potential, including **features** like **solar-powered, plant detection, remote access and control,** and **needs** like **educational AI, climate resilience, and sustainable food production**. These keywords have a significant audience and can be used for data collection in the next analysis step.
- Some keywords require further evaluation before determining their suitability for inclusion in subsequent analysis stages. These include the **features** **food system health** and **plant identification** and the **entire problems keyword list**, which needs refinement. In the problems group, the only keyword that showed some potential was **monoculture in agriculture**.
- **Potential audience segments** were identified: **solar consumers, academic innovators, climate activists, health-conscious consumers, and forward-thinking farmers**. These segments provide an **initial understanding** of the diverse groups that might be interested in the gardening robot prototype.
- The **broader interest categories** associated with these audiences include **science and technology, food and agriculture, and energy and environment**. These categories offer potential areas for further exploration and targeting and can be used in conjunction with keywords for data collection.

#### Interpretation of Results & Insights

The analysis successfully identified relevant keywords across the features and needs domains that demonstrate significant global audience interest. Exploratory identification of potential audience segments and their broader interests provides additional insight to support effective customer segmentation. While some keywords (especially in the problem domain) require further evaluation, the initial analysis has successfully narrowed the focus, allowing for a more targeted and insightful subsequent analysis process.
#### Visualizations

- [**Weekly Average Interest for Most Relevant Keywords**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/weekly_average_interest_all_groups.png) - This bar chart shows the weekly average interest for the most relevant keywords identified in the Google Trends analysis, categorized by their type (need, feature, or problem) and interest level (moderate, high, or critical). It shows absolute interest in keywords in all three groups. Keywords in the features group received the most interest.
- [**Interest Over Time for Key Features**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/key_features_interest_over_time.png) - This heatmap displays the Google Trends interest over time for the most relevant features, categorized by interest level (moderate, high, critical). It shows growth patterns and continuously high interest in the most relevant keywords.
- [**Interest Over Time for Key Needs**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/key_needs_interest_over_time.png) - This heatmap displays the Google Trends interest over time for the most relevant needs, categorized by interest level (moderate, high, critical). It shows rapid growth in interest in the most relevant keywords.
- [**Interest Over Time for Problem with Highest Relevance**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/key_problems_interest_over_time.png) - This heatmap visualizes the Google Trends interest for the keyword ‘Monoculture in agriculture’ over the past three years. It highlights the low overall interest with occasional spikes in this most relevant keyword in the problems group, further emphasizing the need to refine the initial keyword list.
- [**Interest in All Proposed Problems**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/interest_in_all_problem_keywords.png) - This heatmap visualizes Google Trends interest over time for the proposed problems, emphasizing the extremely low interest in all proposed problems on the initial keyword list. Reducing the word count and complexity of keywords is recommended.
- [**Keyword and Category Relationships**](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/visualizations/categories_keywords_relationships.png)
 - This chord diagram illustrates the connections between the identified keywords and their associated Google Search categories, showcasing the interconnectedness of the topics relevant to the target audience. This analysis was conducted only using keywords that were classified as of critical interest in their groups.


## Future Work
### Immediate Next Steps

1. The *problems* keyword list will be revised using simpler terms and re-analyzed to identify areas of stronger interest. This process will iterate until at least one problem keyword with significant audience interest is found.
2. Time-series forecasting will be used to evaluate the potential for future interest in 'Food system health' and 'Plant identification.' If the forecast indicates a significant increase in interest, these keywords will be included in subsequent data collection. Otherwise, they will be excluded from further analysis.
3. All relevant keywords, categorized into features, problems, and needs, will be formatted as Python lists for use in the succeeding data collection phase.

### Next Project Phases

1. **Data Collection from Online Sources**:
    - Multiple notebooks will collect, clean, explore, and transform data from social media and search results using refined keywords.
    - Each data source will have its own notebook.
    - Processed data will be stored in GCS.
2. **Feature Extraction & Engineering**:
    - A notebook will extract relevant features from the collected textual data and metadata.
    - New features will be engineered, and a structured table will be created to represent hypothesized audience groups and their characteristics.
    - This table will be stored in GCS.
3. **Clustering-Based Customer Segmentation**:
    - A clustering algorithm will analyze the structured table to validate the hypothesized audience groups and discover distinct customer segments based on patterns and similarities in the data.
    - The output of this process will be well-defined customer segments, each with its own unique characteristics.


## Contributing & License
- I am primarily developing this project as a personal portfolio piece and am not actively seeking contributions. However, if you find it valuable and have ideas for improvements or additions, feel free to fork the repository and submit a pull request.
- This project is open-source and licensed under the MIT License - see the [LICENSE](https://github.com/alexhosp/startup-viability-analysis/blob/main/customer-segmentation/LICENSE) file for details. In simple terms, you are free to use, modify, and distribute this code for personal and commercial purposes.

## Contact
- **Name:** Alex Hosp
- **Email:** alexhosp.dev@gmail.com
- **GitHub Profile:** https://github.com/alexhosp
- **LinkedIn:** http://www.linkedin.com/in/alexandra-hosp
- **Portfolio:** https://alexhosp.dev/

