# Fake-News-Detection-NLP-Project

### Project Idea:

A type of yellow journalism, fake news encapsulates pieces of news that may be hoaxes and is generally spread through social media and other online media. This is often done to further or impose certain ideas and is often achieved with political agendas. Such news items may contain false and/or exaggerated claims and may end up being virtualized by algorithms, and users may end up in a filter bubble.

### Dataset Definition:

The dataset has a shape of 7796×4. The first column identifies the news, the second and third are the title and text, and the fourth column has labels denoting whether the news is REAL or FAKE.

### Project Requirements:
  1.	Data Preprocessing
  2.	Feature Extraction
  3.	Model Training & Testing
  4.	Visualizing Results
  5.	Saving the model

 
1.	Data Preprocessing:

The dataset consists of 6335 entries with four columns: 'Unnamed: 0', 'title', 'text', and 'label'. 
- The first few rows of the dataset were inspected using news.head().
- Null values were checked using news.isnull().sum() and found that there were no missing values in the dataset.
- The data types and non-null counts were examined using news.info().
- Pie chart visualization of the distribution of news labels (real vs. fake).
 
To prepare the text data for classification, the following preprocessing steps were applied:
  1.	Lowercasing Text:
  - The text data in the 'text' column was converted to lowercase to ensure uniformity in text processing and analysis.
  2.	Stop Words Removal:
  - NLTK's English stopwords were used to filter out common words that do not carry significant meaning for classification purposes.
  3.	Lemmatization:
  - Lemmatization was performed using NLTK's WordNetLemmatizer to reduce words to their base or root form.



2.	Feature Extraction:

After preprocessing, TF-IDF (Term Frequency-Inverse Document Frequency) vectorization was applied to convert text into numerical features. This technique calculates the importance of a word in a document relative to the entire corpus.
3.	Model Training & Testing:

The preprocessed data was split into training and validation sets (80-20 split) for model training and testing. Several machine learning models were trained and evaluated:

  1.	Naive Bayes Classifier:
  - Accuracy: 87.85%
  - Mean Squared Error: 12.15%
  - Confusion Matrix: [[495 120] 
[ 34 618]]

  2.	Logistic Regression Classifier:
  - Accuracy: 91.63%
  - Mean Squared Error: 8.37%
  - Confusion Matrix: [[574 41]
 [ 65 587]]
 
3.	Support Vector Machine (SVM) Classifier:
  - Accuracy: 93.37%
  - Mean Squared Error: 6.63%
  - Confusion Matrix: [[572 43] 
[ 41 611]]

4.	Saving the model:

Each trained model was saved using joblib for future use:
  - Naive Bayes Model: naive_bayes_model.joblib
  - Logistic Regression Model: logistic_regression_model.joblib
  - SVM Model: svm_model.joblib
5.	Conclusion:

The fake news detection project successfully implemented various preprocessing techniques, feature extraction methods, and machine learning models to classify news articles as real or fake. The SVM model achieved the highest accuracy of 93.37%, demonstrating its effectiveness in detecting fake news. The saved models can be deployed for real-time fake news detection applications.
