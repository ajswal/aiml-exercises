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
