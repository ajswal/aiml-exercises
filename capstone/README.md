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
2. Logistic Regression, Decision Tree & Naive Bayes Model's using Count Vectorizer , TfidfVectorizer and stemming(for normalizing the data).
3. Model using Google Bert for Hurt Speech classification. Base pre-trained Bert model is used and trained on training/testing corpus.
5. Real world chat data is pulled from production, the data is manually tagged by Customer Support teammates, and used as evaluation set for the model.

# Analysis and Finding
1. Out of the three model Logistic Regression, Deciion Tree and Naive Bayes both Logistic Regression and Naive Bayes have higher accuracy compared to Decision Tree model
2. Logistic Regression with TfidfVectorizer, on pre-processed data withoout stemming or lemmatization, has the best score.
 <img width="702" alt="Screen Shot 2022-09-19 at 12 33 31 AM" src="https://user-images.githubusercontent.com/97572000/190969758-1c5f2ba4-1e6b-447b-9529-1bfcf8df4c6c.png">
3. On Real World dataset, Logistic Regression with TfidfVectorizer is .7875, which is .10 lower than on training set.
<img width="506" alt="Screen Shot 2022-09-19 at 12 36 38 AM" src="https://user-images.githubusercontent.com/97572000/190970255-b9d6bf4a-995f-4be8-8064-aef727859aff.png">
4. Pre-trained base Bert, trained on same training set and evaluated on same real word set has higher score - .8837
 <img width="467" alt="Screen Shot 2022-09-19 at 12 38 29 AM" src="https://user-images.githubusercontent.com/97572000/190970558-1602b1a7-7db3-4df0-a122-213869b105c1.png">
5. Certain sententes are falsely identified by the model as hurtfull, but in reality the word which triggered the model hurtful class is part of a name or 
a refrence to some actual issue user is facing 
   ## Example's: 
   1) Can a  account be opened in Niger to allow a person to send and receive money?  - (Fllagged word - Niger)
   2) No the 50$ charge was from a porn site that I did not authorize or the 9$ that came with it right after words. (Fllagged word - porn)
   3) My name is John Lynch and I havea problem resetting my password. (Fllagged word - Lynch) 
   4) Hi iam Justin cox. (Fllagged word - cox) 
