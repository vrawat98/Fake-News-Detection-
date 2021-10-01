## Problem Statement
In today’s world everything is online and so as news which is the basic source of what is happening around the world. Online news articles provide very useful information but internet is also filled with fake and misinformation news which even led to misleading people in wrong way. So in order to solve this problem our team of four people combined with the help of each other has develop a A.I. based fake news detection system which detect a news being real or fake.
DATA UNDERSTANDING
Data understanding relies on problem statement. Data related to the this Fake News Detection System is collected from “kaggle”. A snapshot of raw data is been shown below.
 
### Data Preparation
Once the data has been collected, it must be transformed into a usable subset unless it is determined that more data is needed. Since we will be using NLP so the missing data was replaced by a single space and a column is added which is concatenation of two column in the same train dataset those are title , author and text.
 
We used word cloud to see if we could interpreter the world which are used the most in a fake and real news using the WORDCLOUD library.
                                                 figure shows keywords used in real news
Text Cleaning and Preprocessing:-
Removing punctuations and symbols in the the articles as the these are not the factors that will affect the the news being real or fake. We used Regex  to remove those and replaced with a blank. The ‘re’ library for this which uses regular expressions to do the task in text processing. 
Tokenizing the sentences using ‘nltk’ library to use the words in article as an array. Once the tokenizing is done the stopwords were removed from the array as stopwords are not useful in this.
After removing the stopwords Lemmatization of words was done using WordNetLemmatizer() library in nltk. It is done to get the root words so that for predict efficiently. E.g. lemmatization covert cities into city, mice into mouse.


### APPLYING NLP TECHNIQUES:- 
Now that we have got all the words in articles to be used for training the model but before that  we will use some NLP techniques to use our data in modeling.
 Using CountVectorizer  on previously processed data to get the frequency of the words in the articles.
Using 	TF-iDF Vectorizer which stands for term frequency—inverse document frequency. It is used to find how relevant a term in a given document.
	

### Modelling
For modeling we used two Machine Learning Algorithms to fit the model with train data and best performing algorithm was used for the deployment of the model.



As shown in figure above the Logistic regression has higher accuracy on test data i.e 98% while MultinomialNB has 88% accuracy. So we will use logistic Regression to deploy the model.
Pipelining for the deployment of model:
Pipelining the process that we have done till now and saving the pipeline so that we can use this in the deployment part.


### Model Deployment
In the deployment step, the model is used on new data outside of the scope of the dataset and by new users. The new interactions at this phase might reveal the new variables and needs for the dataset and model.
For deployment we will be using our local server to deploy the model using Flask which is a web development framework used for small apps.

Running app.py will start the server and the following page will be displayed on localhost:8080
	
