# Predicting Tweet Sentiment With Emojis

Do emojis in tweets impact sentiment prediction models? This is the question that I wanted to answer in my project. I am studying how emojis affect tweet sentiment to improve sentiment analysis accuracy and learn more about their role in text sentiment. To test my question, I used a Naive Bayes model. Through my testing, I found that adding emojis to tweet text input increases the accuracy of categorization. Surprisingly, the most accurate model that I tested on involved training the model on only emojis, not text. 

Twitter (now X) is a platform where people can share their thoughts and opinions through words, pictures, or videos. Many tweets contain emojis, and they can change or add to the meaning of tweets. Many tweet sentiment analysis models only focus on the words in the tweets when training and testing - and we did it this way in class too (JamesMTucker, n.d.). However, emojis add a lot to the meaning of some tweets. For example, "I LOVE this artist 😍" vs "I LOVE this artist 🙄" have two very different meanings. This is why I chose to focus on this topic for my project. By incorporating emojis into text sentiment analysis, it could create a more accurate model.
 
The dataset that I used was taken from Kaggle (Tweets With Emoji, 2023). It contained 43 separate csv files, categorized by emoji. Each csv file had about 20k tweets per emoji. If a tweet contained multiple emojis, the creators just picked one of the emojis in the tweet to categorize it under. To make it easier for me, I decided to merge the csv files into a large DataFrame. In order to preserve which emoji they were categorized under, I made 2 columns in my DataFrame: Text (tweet) and Emoji, which had the name of the csv file the tweet was in. For example, face_savoring_food or thinking_face. 

Next, I took a small subset of the 860,000 total tweets and made a csv file with an equal amount of tweets per emoji. It had 860 total tweets. I did this because the original dataset didn't contain any sentiment labels, so I had to add them manually. Adding sentiment to hundreds of thousands of tweets was out of the question, so I chose to label the subset of the entire dataset. 

After labeling them, I did some exploration of the data by graphing the distribution of positive and negative tweets and their length. 

<img width="404" alt="Screenshot 2023-12-18 at 2 32 11 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/1e9e2b58-d5f5-4ec1-a7f3-0020a5b53e9d">

Methodology/Dataset: This section explains the research design, including the data sources, data collection methods, and analysis techniques used. It also discusses any assumptions made and the rationale behind the chosen methods. [NOTE: 2-4 paragraphs]

Results: This section presents the findings of the research, including descriptive statistics, tables, and graphs. It should provide a clear and concise summary of the main results, highlighting any patterns or trends observed. [NOTE: 2-4 paragraphs]

Discussion: The discussion section interprets the results of the study in light of the research question and literature review. It should explain how the findings relate to previous research and provide a critical analysis of their implications. [NOTE: 6-10 paragraphs]

Conclusion: This section summarizes the main findings of the study, restates the research question, and discusses the implications of the research for future research and practice. [NOTE: 1-2 paragraphs]

### References
emoji. (2023, December 5). PyPI. https://pypi.org/project/emoji/

JamesMTucker. (n.d.). DATA_340_NLP/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb at master · JamesMTucker/DATA_340_NLP. GitHub. https://github.com/JamesMTucker/DATA_340_NLP/blob/master/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb

Tweets with emoji. (2023, April 12). Kaggle. https://www.kaggle.com/datasets/ericwang1011/tweets-with-emoji?select=saluting_face.csv
