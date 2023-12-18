# Predicting Tweet Sentiment With Emojis

Do emojis in tweets impact sentiment prediction models? This is the question that I wanted to answer in my project. I am studying how emojis affect tweet sentiment to improve sentiment analysis accuracy and learn more about their role in text sentiment. To test my question, I used a Naive Bayes model. Through my testing, I found that adding emojis to tweet text input increases the accuracy of categorization. Surprisingly, the most accurate model that I tested on involved training the model on only emojis, not text. 

Twitter (now X) is a platform where people can share their thoughts and opinions through words, pictures, or videos. Many tweets contain emojis, and they can change or add to the meaning of tweets. Many tweet sentiment analysis models only focus on the words in the tweets when training and testing - and we did it this way in class too (JamesMTucker, n.d.). However, emojis add a lot to the meaning of some tweets. For example, "I LOVE this artist 😍" vs "I LOVE this artist 🙄" have two very different meanings. This is why I chose to focus on this topic for my project. By incorporating emojis into text sentiment analysis, it could create a more accurate model.
 
The dataset that I used was taken from Kaggle (Tweets With Emoji, 2023). It contained 43 separate csv files, categorized by emoji. Each csv file had about 20k tweets per emoji. If a tweet contained multiple emojis, the creators just picked one of the emojis in the tweet to categorize it under. To make it easier for me, I decided to merge the csv files into a large DataFrame. In order to preserve which emoji they were categorized under, I made 2 columns in my DataFrame: Text (tweet) and Emoji, which had the name of the csv file the tweet was in. For example, face_savoring_food or thinking_face. 

Next, I took a small subset of the 860,000 total tweets and made a csv file with an equal amount of tweets per emoji. It had 860 total tweets. I did this because the original dataset didn't contain any sentiment labels, so I had to add them manually. Adding sentiment to hundreds of thousands of tweets was out of the question, so I chose to label the subset of the entire dataset. Positive was 1, negative was 0.

After labeling them, I did some exploration of the data by graphing the distribution of positive and negative tweets and their length. 

<img width="404" alt="Screenshot 2023-12-18 at 2 32 11 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/1e9e2b58-d5f5-4ec1-a7f3-0020a5b53e9d">

Next, I created a Naive Bayes model using the code that we learned in class (JamesMTucker, n.d.). My X input contained the text stripped of emojis, but I appended the name of the emoji that each tweet was classified under to the end of the tweet. So each input looked something like "I LOVE this artist eyes_with_hearts". I wanted to train my model on all of the labeled data that I had, and test it on a big chunk of the unlabeled data. However, I wasn't able to measure accuracy because the testing data was all unlabeled. To get some sort of result, I decided to make the same graph as above, but with the tweets from the testing data and their newly assigned labels. It wasn't too surprising that the graph for the test data looked similar to the graph for the training data. 

<img width="573" alt="Screenshot 2023-12-18 at 2 44 44 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/175f154f-433f-47ae-8e5d-f0f0341f7a02">

To get an accuracy, I decided to both train and test on my labeled data. I performed 4 trials: training and testing on only text, using the text and one emoji, using the text and all of the emojis within the tweet, and finally, using only emojis.

### Just Text
During preprocessing, I replaced all the emojis with blank spaces. When doing train, test, split, I only used the Text column as the X input. My test size was 0.2, which was consistent across all of the tests. The accuracy I got for this was 0.691860.

Examples of miscalculated tweets are:

<img width="464" alt="Screenshot 2023-12-18 at 3 34 03 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/7e72eb95-d737-4b4c-82f2-644f70992fc9">

<img width="1007" alt="Screenshot 2023-12-18 at 3 35 02 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/71abc2fe-0501-470c-b9d9-f432ee7bea58">

The miscalculated tweets are tweets that depend on the emoji to understand the meaning.

### Text + One Emoji
During preprocessing, I replaced all the emojis with blank spaces. When doing train, test, split, I combined the Text and Emoji column as the X input. My accuracy increased to 0.784884. 

Examples of miscalculated tweets are:

<img width="390" alt="Screenshot 2023-12-18 at 3 37 09 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/08fae3a7-627c-432b-914c-cf23833f6e57">

<img width="513" alt="Screenshot 2023-12-18 at 3 37 27 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/872bd1d9-2181-425e-b42e-618044bd1f2c">

Tweets that were misclassified in this category likely depend on multiple emojis to get the meaning, such as the last one. That tweet was categorized with the pile_of_poop emoji, which is a primarily negative emoji. However, the other emojis give it a positive (joking) sentiment. This model also doesn't do well with slang or sarcasm, as indicated with the first example tweet. "Fire" and the fire emoji are both, by definition, negative, but slang gives both of these terms a positive meaning. 

### Text + All Emojis
During preprocessing, I kept all the emojis and their text. When doing train, test, split, I used the Text column but not the Emoji column. The Text contains all of the emojis, including the one listed in the Emoji column. The accuracy of this increased to 0.802326.

Examples of miscalculated tweets are:

<img width="701" alt="Screenshot 2023-12-18 at 3 42 08 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/91524612-7124-4aba-9fa4-26b5ac478843">

<img width="967" alt="Screenshot 2023-12-18 at 3 43 58 PM" src="https://github.com/amanroa/emoji-sentiment-prediction/assets/26678552/82dc1ad3-9e73-44d8-9590-1fb6f9e9c3a2">



Results: This section presents the findings of the research, including descriptive statistics, tables, and graphs. It should provide a clear and concise summary of the main results, highlighting any patterns or trends observed. [NOTE: 2-4 paragraphs]

Discussion: The discussion section interprets the results of the study in light of the research question and literature review. It should explain how the findings relate to previous research and provide a critical analysis of their implications. [NOTE: 6-10 paragraphs]

Conclusion: This section summarizes the main findings of the study, restates the research question, and discusses the implications of the research for future research and practice. [NOTE: 1-2 paragraphs]

### References
emoji. (2023, December 5). PyPI. https://pypi.org/project/emoji/

JamesMTucker. (n.d.). DATA_340_NLP/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb at master · JamesMTucker/DATA_340_NLP. GitHub. https://github.com/JamesMTucker/DATA_340_NLP/blob/master/Fall_2023/notebooks/08_Naive_Bayes_Model.ipynb

Tweets with emoji. (2023, April 12). Kaggle. https://www.kaggle.com/datasets/ericwang1011/tweets-with-emoji?select=saluting_face.csv
