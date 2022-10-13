## Considering Bias in Data

### Goal of the Project

The goal of this project is to explore the concept of bias in data using Wikipedia articles on political figures from different countries combined with a dataset of country populations. The quality of each article is estimated using a machine learning service called [ORES](https://www.mediawiki.org/wiki/ORES). The purpose of the project is to help understand the causes and consequences of biased data in large, complex data
science projects.

### Source Data
The source data for the Wikipedia articles on politicians comes from **MediaWiki Action API** which offers access to wiki features like authetication, page operations and search. The source data for the population data is the **Population Reference Bureau**, a private and nonprofit organization, that specializes in collecting statistics on the environment, and health and structure of populations.

Link to the Mediawiki Action API terms of use: https://foundation.wikimedia.org/wiki/Terms_of_Use/en

### API Documentation
Links to relevant API Documentation:
- https://www.mediawiki.org/wiki/API:Info
- https://www.prb.org/international/indicator/population/table

### Project Structure

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

### File Descriptions

**data**:
- *wp_article_quality-no_match.csv* : A list of the articles that do not have a page quality value.
- *wp_countries-no_match.csv* : A list of all the countries that do not have match in the population dataset.
- *wp_politicians_by_country.csv* : The resulting dataset after combining the Wikipedia data on politicians with the population dataset.

**raw**:
- *politicians_by_country_SEPT.2022.csv* : The list of all the Wikipedia article pages on [poiliticians by country](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality) used as the source data for looking up page quality values.
- *population_by_country_2022.csv* : The population dataset drawn from the [world population data sheet](https://www.prb.org/international/indicator/population/table) that is used to combine with the politiciand data before analysis..

**results**:
- *results.ipynb*: Notebook containing the resukts of the data analysis.

**sample**:
- *wp_ores_example.ipynb* : Example code to make a ORES request.
- *wp_page_info_example.ipynb* : Example code to make a page info request.

**source**:
- homework2.ipynb - Code for colection and analysis of data.

### Research Implications

1. What biases did you expect to find in the data (before you started working with it),
and why?

Before starting the analysis, I expected that probably big English speaking countries (or probably the most popular and maybe rich ones) would have highest number of articles and highest quality of articles as well. The reason being that you just expect more people in such countries to access Wikipedia pages often and since the articles in Wikipedia are peer-reviewed based on a [Wikipedia COntent Assessment](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment), it just seems inituitive to think that such countries would have more number of articles with higher quality content pages.

2. What (potential) sources of bias did you discover in the course of your data
processing and analysis?
3. What might your results suggest about (English) Wikipedia as a data source?
4. What might your results suggest about the internet and global society in general?
5. Can you think of a realistic data science research situation where using these data
(to train a model, perform a hypothesis-driven research, or make business
decisions) might create biased or misleading results, due to the inherent gaps and
limitations of the data?
6. Can you think of a realistic data science research situation where using these data
(to train a model, perform a hypothesis-driven research, or make business
decisions) might still be appropriate and useful, despite its inherent limitations and
biases?
7. How might a researcher supplement or transform this dataset to potentially correct
for the limitations/biases you observed?