# sentiment-analysis
 I build a logistic regression model to classify movie reviews as either positive or negative. We will use the popular IMDB data set. Our goal is to use a simple logistic regression estimator from scikit-learn for document classification.
 Sentiment analysis is the interpretation and classification of emotions (positive, negative and neutral) within text data using text analysis techniques. Sentiment analysis allows businesses to identify customer sentiment toward products, brands or services in online conversations and feedback.
 
 movie_data.csv file has been converted into rar file due to its large size
 saved_model.sav has been converted into rar file due to its large size.
 
 label:Atleast 7 stars out of 10 positive(label=1)
       Atmost 4 stars out of 10 negative(label=0)
 
                      Removing Punctuation, Numbers, and Special Characters
Punctuation, numbers and special characters do not help much. It is better to remove them from the text just as we removed the twitter handles. Here we will replace everything except characters and hashtags with spaces.

                      Removing Short Words
We have to be a little careful here in selecting the length of the words which we want to remove. So, I have decided to remove all the words having length 3 or less. These words are also known as Stop Words.
For example, terms like “hmm”, “and”, “oh” are of very little use. It is better to get rid of them.

                     Tokenization
Now we will tokenize all the cleaned tweets in our dataset. Tokens are individual terms or words, and tokenization is the process of splitting a string of text into tokens.
Here we tokenize our sentences because we will apply Stemming from the “NLTK” package in the next step.

                     Stemming
Stemming is a rule-based process of stripping the suffixes (“ing”, “ly”, “es”, “s” etc) from a word.
For example — “play”, “player”, “played”, “plays” and “playing” are the different variations of the word — “play”

Bag of Words is a method to extract features from text documents. These features can be used for training machine learning algorithms. It creates a vocabulary of all the unique words occurring in all the documents in the training set.
Consider a corpus (a collection of texts) called C of D documents {d1,d2…..dD} and N unique tokens extracted out of the corpus C. The N tokens (words) will form a list, and the size of the bag-of-words matrix M will be given by D X N. Each row in the matrix M contains the frequency of tokens in document D(i).
For example, if you have 2 documents-
D1: He is a lazy boy. She is also lazy.
D2: Smith is a lazy person.
First, it creates a vocabulary using unique words from all the documents.
[‘He’ , ’She’ , ’lazy’ , ‘boy’ , ‘Smith’ , ’person’]
As we can see in the above list we don’t consider “is” , “a” , “also” in this set because they don’t convey the necessary information required for the model.

TF-IDF stands for Term Frequency-Inverse Document Frequency, and the TF-IDF weight is a weight often used in information retrieval and text mining. This weight is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency of the word in the corpus.
Typically, the TF-IDF weight is composed by two terms:
Term Frequency (TF) :
The first computes the normalized Term Frequency (TF), aka. the number of times a word appears in a document, divided by the total number of words in that document.

Example :-
Consider a document containing 100 words wherein the word cat appears 3 times.
The Term Frequency (TF) for cat is then (3 / 100) = 0.03
Inverse Document Frequency (IDF) :
The second term is the Inverse Document Frequency (IDF), computed as the logarithm of the number of the documents in the corpus divided by the number of documents where the specific term appears.

Example :-
Assume we have 10 million documents and the word cat appears in one thousand of these.
Then, the Inverse Document Frequency (IDF) is calculated as
log(10,000,000 / 1,000) = 4.
TF-IDF Example :
Formula for finding the TF-IDF weight :-


From the above examples the Term Frequency is 0.03 and Inverse Document Frequency is 4.
Thus, the TF-IDF weight is the product of these quantities : 0.03 * 4 = 0.12.

                       Splitting our dataset into Training and Validation Set
From the above two techniques that is Bag-of-Words and TF-IDF we have extracted features from the tweets present in our dataset.
Now, we have one dataset with features from the Bag-of-Words model and another dataset with features from TF-IDF model.


