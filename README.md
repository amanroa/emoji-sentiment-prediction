# Predicting Tweet Sentiment With Emojis

Do emojis in tweets impact sentiment prediction models? This is the question that I wanted to answer in my project. I am studying how emojis affect tweet sentiment to improve sentiment analysis accuracy and learn more about their role in text sentiment. To test my question, I used a Naive Bayes model. Through my testing, I found that adding emojis to tweet text input increases the accuracy of categorization. Surprisingly, the most accurate model that I tested on involved training the model on only emojis, not text. 

Twitter (now X) is a platform where people can share their thoughts and opinions through words, pictures, or videos. Many tweets contain emojis, and they can change or add to the meaning of tweets. Many tweet sentiment analysis models only focus on the words in the tweets when training and testing - and we did it this way in class too (JamesMTucker, n.d.). However, emojis add a lot to the meaning of some tweets. For example, "I LOVE this artist 😍" vs "I LOVE this artist 🙄" have two very different meanings. This is why I chose to focus on this topic for my project. By incorporating emojis into text sentiment analysis, it could create a more accurate model.
 
The dataset that I used was taken from Kaggle (Tweets With Emoji, 2023). 

Methodology/Dataset: This section explains the research design, including the data sources, data collection methods, and analysis techniques used. It also discusses any assumptions made and the rationale behind the chosen methods. [NOTE: 2-4 paragraphs]

Results: This section presents the findings of the research, including descriptive statistics, tables, and graphs. It should provide a clear and concise summary of the main results, highlighting any patterns or trends observed. [NOTE: 2-4 paragraphs]

Discussion: The discussion section interprets the results of the study in light of the research question and literature review. It should explain how the findings relate to previous research and provide a critical analysis of their implications. [NOTE: 6-10 paragraphs]

Conclusion: This section summarizes the main findings of the study, restates the research question, and discusses the implications of the research for future research and practice. [NOTE: 1-2 paragraphs]

### References
emoji. (2023, December 5). PyPI. https://pypi.org/project/emoji/

JamesMTucker. (n.d.). DATA_340_NLP/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb at master · JamesMTucker/DATA_340_NLP. GitHub. https://github.com/JamesMTucker/DATA_340_NLP/blob/master/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb

Tweets with emoji. (2023, April 12). Kaggle. https://www.kaggle.com/datasets/ericwang1011/tweets-with-emoji?select=saluting_face.csv
