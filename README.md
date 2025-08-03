
<p align="center"><img width="1000" height="1000" alt="Fake News Banner" src="https://github.com/user-attachments/assets/7a2d4cdb-2403-4ef6-96ac-98c52021ec8e" />

Full report:https://github.com/TheAnalystAlp/Fake-News-Detection-Using-Text-Mining-Classification-Techniques-/blob/main/Fake%20News%20Detection%20Using%20Text%20Mining%26Classification%20Techniques.pdf

# 1.Background of the project

In today’s digital landscape, misinformation and fake news spread rapidly, impacting public opinion, brand reputation, and even financial markets. Political statements, in particular, are often scrutinized, and misleading content can have serious social and economic consequences. Our public relations company needs a reliable solution to automatically flag potentially false or misleading political statements to support decision-making and protect stakeholders.

# 2.Problems the Company Is Facing
* Manual fact-checking is time-consuming, costly, and unable to keep up with the volume ofcontent online.
* Misinformation damages public trust and can lead to reputational risk.
* Current tools lack specificity or accuracy in identifying fake news in political texts.
 
# 3.Method of Approach 
a.Data Preprocessing
* HTML tag cleaning using BeautifulSoup
* Text normalization and noise removal (e.g., mentions, URLs, special characters)
* Tokenization, lowercasing, stopword removal
* Lemmatization to preserve meaningful base forms
* Application of a cleaner function to process the “statement” column
* Dropping irrelevant columns to focus on textual content
* Binary label mapping for simplified classification
b. Feature Extraction
* TF-IDF Vectorization using unigrams and bigrams
* 	Minimum document frequency (min_df = 0.00163) to reduce noise and dimensionality
c. Class Imbalance Handling
*  MOTE applied to training set to counter class imbalance

# 4.Models Built(below models are commonly used text classification)
a.Logistic Regression
* Performs well on high-dimensional sparse data
* Interpretable and computationally efficient
* Chosen for its robustness in binary classification
b.Random Forest Classifier
* Captures complex, non-linear patterns
* Handles noisy text data better but is less interpretable
* Tuned using GridSearchCV with 5-fold cross-validation
  
# 5.Model Performances&Conclusion
After analyzing the dataset, we observed that misleading political statements often used vague or emotionally charged language. The Logistic Regression model, with 66.8% accuracy and strong recall, performed best at identifying such patterns compared to other models. While promising, the results highlight the need for more advanced, context-aware models to achieve real-world reliability.

Here is the predictions of a saved model.(based on the real_life_test Data Set-*new data set for prediction*)
<img width="2286" height="500" alt="Predicted results" src="https://github.com/user-attachments/assets/2a558033-b35c-4389-a833-dccce82f50fa" />

# 6.Limitations
* Loss of Nuance: Binary classification removes subtlety from the original 6-level labels.
* Semantic Blindness: TF-IDF approach ignores context, word order, and meaning (e.g., “not true” vs. “true”).
* Data Imbalance: The fake and true classes were unevenly distributed; SMOTE was used to address this.
* Number Removal: Important numeric information (e.g., audience numbers) was lost during preprocessing.

# 7.Future Improvements
* Use contextual embeddings like Word2Vec, GloVe, or transformer models (e.g., BERT) for semantic understanding.
* Include metadata features (e.g., speaker, party affiliation, source credibility).
* Implement ensemble methods or neural networks for improved performance.
* Improve performance thresholds (current accuracy ~0.70 is insufficient for real-world use).

# 8.Technologies Used
* Python (Pandas, NumPy, Scikit-learn, NLTK, SpaCy)
* TF-IDF Vectorization
* SMOTE for class balancing
* BeautifulSoup
* Machine Learning Algorithms

# 9.Benefits to the Business World-(If applied)
By detecting fake news and comments, we may even address real-world business problems such as misinformation spread,brand reputation damage, market manipulation, and inefficient content moderation and fraudulent queries..

* Protects Brand Reputation: Monitors reviews and 	** **social media platforms** to detect fake claims and review bombing, enabling timely PR responses.
* Improves Content Moderation: Automatically flags suspicious or misleading posts on 	**social platforms** and 	**e-commerce sites** to reduce misinformation and fraud.
* Enhances Financial Integrity: Detects fake news on 	**financial websites** that may manipulate stock prices, helping safeguard investors and analysts.
* Supports Media Verification: Assists 	**journalists** and fact-checkers by pre-screening political statements for quicker and more accurate verification.
* Streamlines Customer Support: Identifies fraudulent or irrelevant queries early, optimizing 	**ticket handling processes** and ensuring regulatory compliance.


Feel free to reach me at; Linkedin:www.linkedin.com/in/alp-tuna

My Website:https://alptheanalyst.wixsite.com/alptuna

My E-Mail:alptuna.professional@gmail.com

Link for the Colab file:https://colab.research.google.com/drive/1oXrwRaj9hJYkiJVktSucdZ0gkGIsQ_VA 

Data Sets

train:https://github.com/TheAnalystAlp/Fake-News-Detection-Using-Text-Mining-Classification-Techniques-/blob/main/train.csv

real_life_test:https://github.com/TheAnalystAlp/Fake-News-Detection-Using-Text-Mining-Classification-Techniques-/blob/main/real_life_test.csv

Credits: Special thanks to Kunwar Madan(DBS-Senior Lecturer in Computing) who introduced us with this subject and broaden our minds.



