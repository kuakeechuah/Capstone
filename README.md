# Capstone Project: Topic Modelling for CMON

## Problem Statement
CMON is a listed company on the HK stock Exchange that sells it's boardgames through a suite of online platforms. It brings boardgames to live by Kickstarter funding and boardgames would go into production once the funding quota is met.

In order to come up with games that are appealing to consumers, it is imperative for CMON to identify customer sentiments, their likes and dislikes and painpoints.

For phase 1 of this project, the data science team has been tasked to classify positive and negative reviews on Boardgamegeeks.com for all of CMON's games using Natural Language Procesisng (NLP).

The model that achieves the highest accuracy on the holdout/test set would be selected for production. The team would also be identifying the key contributors for the classifications.

For phase 2 of the project, the team would be looking at building a recommeder system for CMON based on ratings of the board games.

Phase 1 is crucial for the chief creative director so that CMON is able to understand what consumers like or dislike in their board games so that resources can be channeled to ensuring that the games they launch on kickstarter can be fully and hopefully over subscribed.

Phase 2 would enhance their company's sales by recommending games that players enjoy to encourage purchase.

Deadline for phase 1 would be by the beginning of August 2020 and phase 2 rollout would be dependent on the successful completion of phase 1.

To solve this problem, Natural Language Processing (NLP) will be deployed and binary classification models will be built and the final predictive model will be selected based on the accuracy scores.

Ultimately,using the predictive model, CMON would be able to uncover the answers to the following problems:

Is the feedback provided positive or negative?

What are the key messages from comments of players?

The model chosen should achieve an accuracy better than the baseline line score of 0.51 to be deemed successful.

## Executive Summary
Are trying to figure out whether a comment provided is positive or negative? and Are you trying to decipher the key message from comments?

We can help you!!!

We seek to examine the comments from BoardGamesGeek for all CMON games.

The optimal classification model with best performance would be use to help figure out if a comment is positive or negative and provide some insights on the key topics or area CMON needs to focus on. This helps CMON to understand the key issues from negative comments as well as the key areas to focus on to make a more informed decision before

## Conclusions and Recommendations
The production model chosen is TFIDF & SVC and given that our production model achieves 0.67 on accuracy, higher than our baseline model of 0.51 and 0.63 on recall, we can conclude that the model generalises well on unseen data.

We have also identified key areas that CMON needs to work on that consumers like. First, CMON needs to ensure that miniatures for the board games are of a high standard as some consumers buy the game sets for collection rather than playing. Having an expansion set with more miniatures would enable CMON to improve on sales as well as consumers like expansion sets.

Second, the game rules must be simple, but yet allows players to strategise and have different game plays.

Third, it is important for CMON to have a campaign to introduce the new games. This would be be best done over social media and a way could be getting social media influencers to play the games and launch the videos on youtube.

## Limitations and Next Steps
While the accuracy of the production model is higher than the baseline, it is still not too high. One way to improve this is to collect more data from other sources beside just boardgamegeeks to train the model.

Another way is to consider using BERT( Bidirectional Encoder Representations from Transformer), state of the art model for NLP to see if better results could be obtained.

Next steps would be to share the 3 key areas of focus with CMON and to move on to part 2 of the project, which is to develop a recommender engine for CMON.

## Data Guidelines
Data has been scapped from https://boardgamegeek.com/ for all CMON games. Script is used to scrape all the ratings and comments for all CMON boardgames and saved into CSV format. There are 4 columns including the index. Other columns include the username ( registered user name for the forum), ratings given by user for the boardgame (from 1 to 10) and comments from the user.

Ratings from 7 and below would be deemed to be negative, ratings from 8 to 10 would be deemed to be positive.

There is one csv for each board games and the data would be compiled for review. Preliminary assessment indicates that there would be approximately 16K rows.

They would be split into 50% (train-test) set and 50% holdout set.

The comments column would be lemmatize/ tokenised into useful words.

Data cleaning:

Remove duplicated reviews Remove reviews that do not have any meaningful words Remove reviews that are non-English or gibberish Pre-processing:

Remove HTML tags Use regular expression to remove special characters and numbers Lowercase words Use NLTK to remove stopwords Remove common occurring words that appear in both positive and negative sentiments Use NLTK to stem words to their root form

## Data Dictionary
The data dictionary below provides an overview of the features in our dataset.

| Feature              | Type     | Description                                                                    |
|:---------------------|:---------|:-------------------------------------------------------------------------------|
| unnamed              | obj      | Serial number of comment                                                       |
| userName             | obj      | Username of the reviewer                                                       |
| Rating               | obj      | Ratings from 0 to 10 by user                                                   |
| Comment              | obj      | Textual data of the review                                                     |
| Comment_clean        | int      | Cleaned textual data                                                           |
| number_of_words      | obj      | No of words of "useful" words in comment                                       |
| Target               | int      |1- Positive comments : Ratings 8 to 10, 0- Negative comment: Ratings 0 to <8    |


