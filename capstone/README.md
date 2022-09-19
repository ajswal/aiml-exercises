# Objective
The objective of this project is to perform content moderation on incoming chat conversations in conversational channels.
Content Moderation classification is broad and can have multiple classification based on application need.
In this project primary focus is on identifying hurt/hateful conversation.

# Usage
The model can be deployed to filter conversations in the following application.
1) Social media channels.
2) Community Forums.
3) Call Center application where companies offer online Chat as a channel to solve customer problems.

# Approach
The project attempts to build following models :-
1. Logistic Regression, Decision Tree & Naive Bayes Model's using Count Vectorizer , TfidfVectorizer and lemmatization (for normalizing the data).
Link to the workbook : https://github.com/ajswal/aiml-exercises/blob/main/capstone/capstone_content_moderation_LR_DT_NB.ipynb
3. Logistic Regression, Decision Tree & Naive Bayes Model's using Count Vectorizer , TfidfVectorizer and stemming(for normalizing the data).
4. Model using Google Bert for Hurt Speech classification. Base pre-trained Bert model is used and trained on training/testing corpus.
Link to workbook : https://github.com/ajswal/aiml-exercises/blob/main/capstone/capstone_content_moderation_bert.ipynb
6. Real world chat data is collected from production environment , the data is manually tagged by Customer Support teammates, and used as evaluation set for the model. The data has been redacted of any sensitive info.

# Analysis and Finding's
1. Out of the three model Logistic Regression, Deciion Tree and Naive Bayes both Logistic Regression and Naive Bayes have higher accuracy compared to Decision Tree model
2. Logistic Regression with TfidfVectorizer, on pre-processed data withoout stemming or lemmatization, has the best score.
 <img width="702" alt="Screen Shot 2022-09-19 at 12 33 31 AM" src="https://user-images.githubusercontent.com/97572000/190969758-1c5f2ba4-1e6b-447b-9529-1bfcf8df4c6c.png">
3. On Real World dataset, Logistic Regression with TfidfVectorizer has score of .7875, which is .10 lower than on training set.
<img width="506" alt="Screen Shot 2022-09-19 at 12 36 38 AM" src="https://user-images.githubusercontent.com/97572000/190970255-b9d6bf4a-995f-4be8-8064-aef727859aff.png">
4. Pre-trained base Bert, trained on same training set and evaluated on same real word set has higher score - .8837
 <img width="467" alt="Screen Shot 2022-09-19 at 12 38 29 AM" src="https://user-images.githubusercontent.com/97572000/190970558-1602b1a7-7db3-4df0-a122-213869b105c1.png">
5. Certain sentences are falsely identified by the model as hurtfull, but in reality the word which triggered the model hurtful class is part of a name or 
a refrence to some actual issue user is facing.

### Example's: 
#### 1) Can a  account be opened in Niger to allow a person to send and receive money?  - (Fllagged word - Niger)
#### 2) No the 50$ charge was from a porn site that I did not authorize or the 9$ that came with it right after words. (Fllagged word - porn)
#### 3) My name is John Lynch and I havea problem resetting my password. (Fllagged word - Lynch) 
#### 4) Hi iam Justin cox. (Fllagged word - cox) 

6. For some of these situations adding a filter on top of the actual model prediction will help improve the prediction. 
7. The Bert model takes time to train, and would be ideal to use a GPU for training and running the model
8. Even though the Bert model performed beter, but the False Positive rate is higher than Logistic Regression Model 

# Next Steps
1. Overall Bert model would be the recommended model, especially as it has performed well on the organization specific Live data.
2. The accuracy of the Bert can be further improve by more training.
3. This will also help in reducing the false positive rate.
4. For the falsely identified sentences, try adding a filter based on available customer data, to supplement the model prediction.

