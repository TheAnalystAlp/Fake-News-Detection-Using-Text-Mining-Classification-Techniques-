Background of the project
In today’s digital landscape, misinformation and fake news spread rapidly, impacting public opinion, brand reputation, and even financial markets. Political statements, in particular, are often scrutinized, and misleading content can have serious social and economic consequences. Our company needs a reliable solution to automatically flag potentially false or misleading political statements to support decision-making and protect stakeholders.

Problem Statement
•	Manual fact-checking is time-consuming, costly, and unable to keep up with the volume of political content online.
•	Misinformation damages public trust and can lead to reputational risk and financial loss.
•	Current tools lack specificity or accuracy in identifying fake news in political texts.
 
Methodology
1. Data Preprocessing
•	HTML tag cleaning using BeautifulSoup
•	Text normalization and noise removal (e.g., mentions, URLs, special characters)
•	Tokenization, lowercasing, stopword removal
•	Lemmatization to preserve meaningful base forms
•	Application of a cleaner function to process the “statement” column
•	Dropping irrelevant columns to focus on textual content
•	Binary label mapping for simplified classification
2. Feature Extraction
•	TF-IDF Vectorization using unigrams and bigrams
•	Minimum document frequency (min_df = 0.00163) to reduce noise and dimensionality
3. Class Imbalance Handling
•	SMOTE applied to training set to counter class imbalance

Models Built
Logistic Regression
•	Performs well on high-dimensional sparse data
•	Interpretable and computationally efficient
•	Chosen for its robustness in binary classification
Random Forest Classifier
•	Captures complex, non-linear patterns
•	Handles noisy text data better but is less interpretable
•	Tuned using GridSearchCV with 5-fold cross-validation

Model Performance
Model	Accuracy	Precision	Recall	F1-Score
Logistic Regression	66.76%	0.6610	0.6841	0.6724
Random Forest	66.49%	0.6783	0.6737	0.6760

The Logistic Regression model achieves 66.8% accuracy with a higher recall rate, meaning it’s more effective at detecting fake news than alternatives tested.
While promising, the model still needs improvement to reach real-world reliability thresholds.

Limitations
•	Loss of Nuance: Binary classification removes subtlety from the original 6-level labels.
•	Semantic Blindness: TF-IDF ignores context, word order, and meaning (e.g., “not true” vs. “true”).
•	Data Imbalance: The fake and true classes were unevenly distributed; SMOTE was used to address this.
•	Number Removal: Important numeric information (e.g., death tolls) was lost during preprocessing.

 Future Improvements
•	Use contextual embeddings like Word2Vec, GloVe, or transformer models (e.g., BERT) for semantic understanding.
•	Include metadata features (e.g., speaker, party affiliation, source credibility).
•	Implement ensemble methods or neural networks for improved performance.
•	Improve performance thresholds (current accuracy ~0.70 is insufficient for real-world use).

Technologies Used
•	Python (Pandas, NumPy, Scikit-learn, NLTK, SpaCy)
•	TF-IDF Vectorization
•	SMOTE for class balancing
•	BeautifulSoup
•	Machine Learning Algorithms

Benefits to the Business World
•	Brand Reputation: Monitor reviews and social media to spot fake claims, enabling quick PR response.
•	Content Moderation: Automatically flag suspicious posts on social platforms and e-commerce sites to curb misinformation and fraud.
•	Financial Intelligence: Detect fake news influencing stock prices to protect investors and analysts from market manipulation.
•	Media Verification: Support journalists and fact-checkers by pre-screening content for faster verification.
•	Customer Support: Identify fraudulent queries to streamline ticket handling and compliance checks.

