# SMS-Spam-Detection 


# About this project(Summary)
We need a way to represent text data for machine learning algorithm and the bag-of-words model helps us to achieve that task. We use the tokenized words for each observation and find out the frequency of each token.Using this process  , we  convert this collection of documents to a matrix, with each document being a row and each word(token) being the column,and the corresponding (row,column) values being the frequency of occurrence of each word or token in that document.

# Important term/technique used in this project

# '.loc':
method in pandas is a label-based indexer that is used to access a group of rows and columns by labels or a boolean array. 

# lowercase = True :
The lowercase parameter has a default value of True which converts all of our text to its lower case form.

# token_pattern = (?u)\b\w\w+\b :
The token_pattern parameter has a default regular expression value of (?u)\b\w\w+\b which ignores all punctuation marks and treats them as delimiters, while accepting alphanumeric strings of length greater than or equal to 2, as individual tokens or words.

# stop_words :
The stop_words parameter, if set to english will remove all words from our document set that match a list of English stop words which is defined in scikit-learn.
Considering the size of our dataset and the fact that we are dealing with SMS messages and not larger text sources like e-mail, we will not be setting this parameter value.

 # pprint:
 stands for "pretty-print," and it's a module in the standard library that provides a way to print data structures in a more human-readable and formatted manner.

# sklearn.naive_bayes :
method to make predictions on our dataset for SMS Spam Detection
-> Specifically, we will be using the  **multinomial Naive Bayes** implementation. This particular classifier is suitable for **classification with discrete features**. It takes in integer word counts as its input.
-- On the other hand **Gaussian Naive Bayes** is better suited for **continuous data** as it assumes that the input data has a Gaussian(normal) distribution.
 
 # alpha=1.0
 *'alpha'* parameter is a smoothing parameter .It is used to avoid issues when calculating probabilities for unseen features.

 # class_prior:
 The prior probabilities of the classes. If set to None (the default), the class priors are adjusted based on the data. If you provide an array-like object, it should contain the prior probabilities of each class. The order should match the order of unique classes in your training data.

# fit_prior:
The fit_prior parameter determines whether to learn class priors from the data (True) or use uniform class priors (False). If set to True, the algorithm estimates class priors based on the relative frequencies of the classes in the training data. If set to False, uniform class priors are used.
 
# Accuracy:
measures how often the classifier makes the correct prediction. It’s the ratio of the number of correct predictions to the total number of predictions (the number of test data points).

# Precision:
tells us what proportion of messages we classified as spam, actually were spam. It is a ratio of true positives(words classified as spam, and which are actually spam) to all positives(all words classified as spam, irrespective of whether that was the correct classification) like, [True Positives/(True Positives + False Positives)]

# Recall(sensitivity) :
tells us what proportion of messages that actually were spam were classified by us as spam. It is a ratio of true positives(words classified as spam, and which are actually spam) to all the words that were actually spam, in other words it is the ratio of

[True Positives/(True Positives + False Negatives)]

# f1_score:
For classification problems that are skewed in their classification

For example if we had a 100 text messages and only 2 were spam and the rest 98 weren’t, accuracy by itself is not a very good metric.We could classify 90 messages as not spam(including the 2 that were spam but we classify them as not spam, hence they would be false negatives) and 10 as spam(all 10 false positives) and still get a reasonably good accuracy score.

For such cases, precision and recall come in very handy. These two metrics can be combined to get the F1 score, which is weighted average of the precision and recall scores. This score can range from 0 to 1, with 1 being the best possible F1 score.

We will be using all 4 metrics to make sure our model does well. For all 4 metrics whose values can range from 0 to 1, having a score as close to 1 as possible is a good indicator of how well our model is doing.

