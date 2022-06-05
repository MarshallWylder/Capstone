# Recipe Recommendations: A Content Based Approach
Author: Marshall Wylder

## Overview
This project aims to build a content based recommendation system for recipes. Users will be able to input ingredients that they have or would like use and the recommender will give recipes based around those ingredients. To run the notebooks, all required packages are avsilable in the environment.yml file.


## Motivation
Cooking can be a creative challenge. The first part of the challenge is even knowing where to start. I wanted to create a bottom up approach to deal with deciding what to cook. Start with ingredients and find out what can be made with it. This approach can be a more effiecent way to get through left over ingredients from prior meals as well as a way to find meals based around healthier ingredients or dietary restrictions.


## Data Understanding
Over 8000 recipes were collected through web-scraping the New York Times Cooking webpage. The data scraped from the websited included ingredient list along with the URL of the page to extract the name of the recipe. All the data was text data so NLP techniques were used to clean and prepare the data to be used in the recommendation system.

## Data Preparation
After the data was collected the title of each recipe needed to be parsed from the URL and the list of ingredients for each recipe needed to be flattened into one string. I created a function called recipe_parser that would change all the words to lowercase, remove numbers and stopwords, and tag words as certain parts of speech and remove the all words that were not labeled as a noun or plural of a noun. Cleaning the recipes like this trys to simplify the list of ingredients down to the base words that identify that ingredient. For example, if a recipe ask for a teaspoon of minced garlic then the word garlic is ingredient we are looking for. 


## Content-Based Model 
After the recipes were parsed then CountVectorizer was used to turn each recipe into a word embedding that will be used for the recommendor system. I decided to use CountVectorizer instead of TF-IDF because in the trm frequency of and ingredient in an ingredient list would be low because most ingredients terms are only stated once. The recommendation system also needs an input to build a recommendation off of. When the recommender system is run the user is prompted to input an ingredient or a list of ingredients. That input is turned into a word embedding and a recommendation based on cosine similarity is made. The output of the recommender is the title of the recipe(s) along with the URL and the full list of ingredients.

## Conclusion
This content-based recommender has many improvements to go through but the sysyem was able to recommend appropriate recipes. Some next steps for this project was to greatly refine the NLP methods to better isolate the ingredients from the lists. Also setting up a stremlit app to delploy the recommendor system for easier use for myself and others.

```
 ├── images
 ├── EDA and Modeling.ipynb
 ├── Web-Scraping.ipynb
 ├── environment.yml
 ├── ingredients.pickle
 ├── README.md
 ├── Recipe Recommender.pdf
 └── Recipe_names.pickle

```


