# Sentiment Analysis on Newspaper Headlines Using RandomForest Classifier
The primary goal of this project was to determine whether the sentiment conveyed by the headlines could effectively predict the movement of stock prices. Below is a detailed description of the methodology and results of this analysis.

## Dataset Description
The dataset used for this analysis comprised daily newspaper headlines from various sources over several years, along with corresponding stock market movement labels (0 for no significant change or decrease, and 1 for a significant increase). Each row in the dataset represents the headlines for a particular day, with 25 headline columns per day.

## Data Preprocessing
1. Loading the Data:
The dataset was loaded into a Pandas DataFrame, and the initial inspection revealed columns for the date, label, and 25 headlines.

2. Splitting the Data:
The data was divided into a training set (headlines before January 1, 2015) and a testing set (headlines after December 31, 2014).

3. Text Cleaning:
All non-alphabetic characters were removed from the headlines, and the text was converted to lowercase to ensure uniformity.

4. Combining Headlines:
For each day, the 25 headlines were concatenated into a single string, creating a comprehensive representation of the day's news.

## Feature Extraction
A Bag of Words (BoW) model was used to transform the text data into numerical features. The CountVectorizer was configured to extract bigrams (two consecutive words) from the text, capturing more context than single words.

## Model Training
A RandomForestClassifier was employed for the classification task. This choice was made due to its robustness and ability to handle a large number of features effectively. The model was trained using 200 trees and entropy as the criterion for splitting.

## Model Evaluation
The trained model was evaluated on the test dataset using several metrics:

1. Confusion Matrix:
The confusion matrix showed the true positives, true negatives, false positives, and false negatives, providing a comprehensive view of the model's performance.

2. Accuracy Score:
The overall accuracy of the model was 86.24%, indicating a high level of predictive power.

3. Classification Report:
The precision, recall, and F1-score for each class were calculated. The model achieved a precision of 0.97 and recall of 0.75 for class 0, and a precision of 0.80 and recall of 0.97 for class 1. The weighted average F1-score was 0.86.

## Results
The analysis demonstrated that the sentiment derived from newspaper headlines could predict stock market movements with substantial accuracy. The RandomForestClassifier, coupled with the BoW feature extraction, proved to be effective in capturing the nuances in the headlines that correlate with market trends.

## Conclusion
This project successfully showcased the potential of using natural language processing and machine learning techniques for sentiment analysis in financial contexts. The results highlight that newspaper headlines can serve as a valuable predictor for stock market movements, offering insights for traders and financial analysts.

## Future Work
Future enhancements could include exploring more sophisticated text representation methods like TF-IDF or word embeddings, experimenting with different classification algorithms, and incorporating additional features such as headline sentiment scores or economic indicators to further improve the model's accuracy and robustness.
