# Reddit text analysis

### Objective

The reason I chose two subreddits below is due to the nature of fashion at the moment. The erasure of the gender boundaries can be observed over the recent decade: female trends have become more masculine, adopting _"traditionally"_ male fashion pieces and jargon, whereas men's fashion showcased adaptation of _"traditionally"_ female fabrics such as chiffon and lace. I wanted to analyze how different are we in languages that we utilise in these _unisex_ setting.
 
 
     - Male Fashion Advice with 2.2 mln subscribers
     
     - Female Fashion Advice with 850 k subscribers

These two subreddits are good in a sense that for malefashionadvice the majority of participants are prevalently men and vice versa for female thread, and most of the text would be used in the post not in the comment section, providing me with an opportunity to actually analyze the differences in gender languages.




So the main objectives of the project are to:


 - Analyze two subreddits and the difference in the language used in the two threads
     
     
 - Create model with highest accuracy score and minimize Type I and Type II errors
 
 
 ---


### Project Overview

1. For this project I had to pull in the data first, so I scraped the data using Reddit API

    - I was able to collect enough dataset for my project around 3835 posts proportinately divided between two subreddits
    
    
2. Data cleaning is an essentail part of any data science project

    - There were missing values in the dataset, but I mostly didn't need these features for my model
    
    - The only features I was interested in are 'selftext' and 'title'
    
    - And I had to engineer the main feature since the actual posts are in the 'selftext' columns, but the may be missing due to the nature of the post, i.e. posing a question in the 'title' section
    
    
3. As for data munging, I had to create the model first and analyze it performance

    - Only then I could go back and create several lists for stop words to be used in the model
    
    
4. In order to select the best fit model I utlized GridSearch and Pipeline in order to tweak the features of the transformer and used it on Naive Bayes model and Logistic Regression model

    - Logistic Regression model performed substantially better and I was able to achieve zero false positives


5. Data visualisation in order to analyze:

    - what words are most common between two subreddits
    
    - word and sentence length
    
    - which words were assigned the highest coefficients
    
    
6. Conclusions on the project


---

### Useful links

1. This is the link to the [Data Scraper NB](./Scraper.ipynb) in case you want to check out the code for scraping data using Reddit API

2. To check out the data cleaning process click on this link [Data Cleaning NB]('./Data_cleaning.ipynb')

3. Follow this link [Model NB](./Model_2.ipynb) to check out how Naive Bayes model performed against Logistic Regression model using GridSearch and Pipeline

4. This is the link to the [Project NB](./Project_3.ipynb) which covers:
    - EDA
    - Model performance
    - Coefficient analysis
    - Conclusions on the project

---

### Conclusions

As I stated at the beginning of the project the reason for choosing these two subreddits is due to the nature of the subreddits that gave me an opportunity to pull texts that was actually utilised by both genders in their realted subreddits. And it is clear that there is a big overlap in the words that are used in the fashion context.


In order to make sure that my model is unbiased as possible, I got rid of gender related words and tried running my model with and without the stopwords, and it turns out that the accuracy score jumps up by 10% if I leave the English stop words in. This in conjunction with the EDA and careful data analysis leads me to the conclusions below:

1. The way we structure our language differs between genders:


     - Posters in Male subreddit tend to use less words in their sentences and posts
     
     - They also tend to abbreviate words more, and hence the high frequency usage of the **$** sign


2. Posters on female fashion advice tend to use more emotional language or word describing emotions such as **love and feel**


3. Although there is a vast amount of overlapping words that are used in the fashion context, phrases and words substantially differ between the two subreddits. Certain words such as 'shirt', 'chinos' or 'dress' have high impact on the predictions ability of the model.


4. Logistic Regression performed better for me in terms of this project as opposed to Naive Bayes, since not only does it have 99$%$ accuracy score but also it is more interpretable so that it helps to analyze what words are the best predictors.


---

### Possible applications of the project:

1. This model can be used to determine what words are most impactful on gender in terms of marketing fashion products


2. It can be used to define who is commenting certain posts/news


3. It can be used to simulate human-like behaviour, etc.