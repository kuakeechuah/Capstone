# Capstone

## Problem Statement
CMON is a listed company on the HK stock Exchange that sells it's boardgames through a suite of online platforms. It brings boardgames to live by Kickstarter funding and boardgames would go into production once the funding quota is met.

In order to come up with games that are appealing to consumers, it is imperative for CMON to identify customer sentiments, their likes and dislikes and painpoints.

For phase 1 of this project, the data science team has been tasked to classify positive and negative reviews on Boardgamegeeks.com for all of CMON's games using Natural Language Procesisng (NLP).

The model that achieves the highest accuracy and recall on the validation set would be selected for production. The team would also be identifying the key contributors for the classifications.

For phase 2 of the project, the team would be looking at building a recommeder system for CMON based on ratings of the board games.

Phase 1 is crucial for the chief creative director so that CMON is able to understand what consumers like or dislike in their board games so that resources can be channeled to ensuring that the games they launch on kickstarter can be fully and hopefully over subscribed.

Phase 2 would enhance their company's sales by recommending games that players enjoy to encourage purchase.

Deadline for phase 1 would be by the beginning of August 2020 and phase 2 rollout would be dependent on the successful completion of phase 1.

## Data Guidelines
Data has been scapped from https://boardgamegeek.com/ for all CMON games. Script is used to scrape all the ratings and comments for all CMON boardgames and saved into CSV format. There are 4 columns including the index. Other columns include the username ( registered user name for the forum), ratings given by user for the boardgame (from 1 to 10) and comments from the user.

Ratings from 5 and below would be deemed to be negative, ratings from 6 to 10 would be deemed to be positive.

There is one csv for each board games and the data would be compiled for review. Preliminary assessment indicates that there would be approximately 16K rows.

They would be split into 50% (train-test) set and 50% holdout set.

The comments column would be lemmatize/ tokenised into useful words.

Data cleaning:

Remove duplicated reviews Remove reviews that do not have any meaningful words Remove reviews that are non-English or gibberish Pre-processing:

Remove HTML tags Use regular expression to remove special characters and numbers Lowercase words Use NLTK to remove stopwords Remove common occurring words that appear in both positive and negative sentiments Use NLTK to stem words to their root form
