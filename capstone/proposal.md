•	A general idea of your question (a sentence or two)
Building  a content moderation(offensive language/ hurt speech) or sentiment analysis model.  The model will classify user input text into three classes ‘egregious’ , ‘neutral’ ,’normal’ and also identify the sentiment as positive or negative.


•	An initial guess at what data you will need to answer that question
Data requirement will be sentences from  conversations from social media platforms or posted articles/news etc which will have to be tagged to one of the above classes.


•	An initial guess as to how you will source that data
Found these resources
1)	Kaggle dataset’s (primary for text classification into the 3 classes) -  https://www.kaggle.com/competitions/jigsaw-toxic-comment-classification-challenge/data  , https://www.kaggle.com/datasets/mrmorj/hate-speech-and-offensive-language-dataset
2)	Kaggle dataset ( primarily to do sentiment analysis)  https://www.kaggle.com/datasets/therohk/india-headlines-news-dataset
3)	Generate some labelled data using ‘zero-shot-text classification’ - https://discuss.huggingface.co/t/new-pipeline-for-zero-shot-text-classification/681 , and perform a manual review of the tagging
