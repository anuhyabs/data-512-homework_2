# Considering Bias in Data

## Goal of the Project

The goal of this project is to explore the concept of bias in data using Wikipedia articles on political figures from different countries combined with a dataset of country populations. The quality of each article is estimated using a machine learning service called [ORES](https://www.mediawiki.org/wiki/ORES). The purpose of the project is to help understand the causes and consequences of biased data in large, complex data science projects.

## Source Data
The source data for the Wikipedia articles on politicians comes from **MediaWiki Action API** which offers access to wiki features like authetication, page operations and search. The source data for the population data is the **Population Reference Bureau**, a private and nonprofit organization, that specializes in collecting statistics on the environment, and health and structure of populations.

Link to the Mediawiki Action API terms of use: https://foundation.wikimedia.org/wiki/Terms_of_Use/en

## API Documentation
Links to relevant API Documentation:
- https://www.mediawiki.org/wiki/API:Info
- https://www.prb.org/international/indicator/population/table

# Project Structure

```bash
data-512-homework_2
├── data
│   ├── wp_article_quality-no_match.csv
│   ├── wp_countries-no_match.csv
│   └── wp_politicians_by_country.csv
├── raw
│   ├── politicians_by_country_SEPT.2022.csv
│   └── population_by_country_2022.csv
├── results
│   └── results.ipynb
├── sample
│   ├── wp_ores_example.ipynb
│   └── wp_page_info_example.ipynb
├── source
│   └── homework2.ipynb
├── LICENSE
└── README.md
 ```

## File Descriptions

**data**:
- *wp_article_quality-no_match.csv* : A list of the articles that do not have a ORES page quality value.
- *wp_countries-no_match.csv* : A list of all the countries that do not have match in the population dataset.
- *wp_politicians_by_country.csv* : The resulting dataset after combining the Wikipedia data on politicians with the population dataset.

**raw**:
- *politicians_by_country_SEPT.2022.csv* : The list of all the Wikipedia article pages on [poiliticians by country](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality) used as the source data for looking up page quality values.
- *population_by_country_2022.csv* : The population dataset drawn from the [world population data sheet](https://www.prb.org/international/indicator/population/table) that is used to combine with the politiciand data before analysis..

**results**:
- *results.ipynb*: Notebook containing the tables resulting from the data analysis done in *homework2.ipynb*.

**sample**:
- *wp_ores_example.ipynb* : Example code to make a ORES request.
- *wp_page_info_example.ipynb* : Example code to make a page info request.

**source**:
- *homework2.ipynb* - Code for collection and analysis of data.

## Data Descriptions

*Politicians dataset*
|Column |Description|
|---|---|
|name | Wikipedia article title on politician|
|url | URL to the Wikipedia page|
|country | Country associated with the politician|

*Population Dataset*
|Column |Description|
|---|---|
|Geography| Country and Regions|
|population (in millions)| Population of the region in millions|

# Research Implications

Before beginning the analysis I suspected bigger and richer English speaking countries to have more number of total article and articles with higher qualitites. In process of the analysis, I was suprised to discover that many major English speaking countries like the Unites States, United Kingdom, Australia and Canada did not have any politician articles maped to them and hence no page quality score related to them. Thus, these countries were completely excluded in the data analysis which is a major source of data bias. Another interesting thing was how dynamically the data changed on Wikipedia. When I re-ran the API for page info and ORES score, there would often be inconsistencies in the number of missing articles.

1. What biases did you expect to find in the data (before you started working with it), and why?

    Before starting the analysis, I expected that probably big English speaking countries (or probably the most popular and maybe rich ones) would have highest number of articles and highest quality of articles as well. The reason being that you just expect more people in such countries to access Wikipedia pages often and since the articles in Wikipedia are peer-reviewed based on a [Wikipedia Content Assessment](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment), it just seems inituitive to think that such countries would have more number of articles with higher quality content pages.

2. What (potential) sources of bias did you discover in the course of your data processing and analysis?

    The web-crawling done on the Wikipedia page to generate a list of article pages about politicians from a wide range of countries did not capture politicians from major English speaking countries (as seen above). The data collection was flawed. Taking this file as the source of the data analysis, leads to bias as a major category of countries is not accounted for in the data. 

3. How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?

    A researcher may augment the dataset by crawling Wikipedia pages and ensuring that the politicians dataset contains poiliticians from each country in order to prevent bias and be able to work on meaningful data analysis.
