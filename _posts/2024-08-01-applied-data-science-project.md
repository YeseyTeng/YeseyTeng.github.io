---
layout: post
author: Name
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## PROJECT BACKGROUND
The dataset has been obtained from Kaggle and pertains to the conversion records of inquirers for course enrolment at X Education. This institution offers a diverse range of courses including Banking, Investment and Insurance, Human Resource Management, Media and Advertising, Service Excellence, Travel and Tourism, Financial Management, International Business, and others.

The dataset provides a comprehensive overview of inquirers, encompassing their demographics such as city and country, occupations, online behavior (e.g., time spent on website and page views per visit), lead sources, asymmetrical information, and most importantly, their conversion status (i.e., whether they converted or not).

Our primary business goals revolve around increasing the conversion rate, which are further divided into four sub-objectives.  Business Objective 1 involves analyzing the factors that influence conversion success.  Business Objective 2 aims to identify the factors that can increase the time spent on the website.  Business Objective 3 is to comprehend the strengths and weaknesses of the institution.  Lastly, Business Objective 4 focuses on analyzing the effectiveness of marketing strategies.


## WORK ACCOMPLISHED
To achieve a comprehensive understanding of the institution's strengths and weaknesses (objective 3), we will employ text analytics capabilities within KNIME and Python to conduct a detailed analysis of reviews and comments.  This analysis will involve sentiment classification, enabling us to identify the core topics and sentiments expressed by our customers.  By gaining these insights, we can develop targeted strategies to enhance our offerings and optimize conversion rates.

### DATA PREPARATION
Initially, we employed KNIME for a preliminary text review using the following steps:
  1.	CSV Reader: Loaded the review data from a CSV file.
  2.	String to Document: Converted text strings into KNIME documents.
  3.	Text Processing:
  - Option 1: Applpied stop word filter
  - Option 2:  Applied  more comprehensive text cleaning process (including punctuation removal, N-character filtering, case conversion, and stop word removal)
  - Option 3: Implemente similar process as Option 2, but included Porter Stemming to reduce the words to root form 
  4.	Keygraph Keyword Extractor: Identified key terms within the processed text.
  5.	Tag Cloud: Visualized the frequency of extracted keywords.

Option 2, excluding stemming, was applied at the end of the process as it provided more nuanced sentiment information. Stemming was not included in the text processing to avoid potential ambiguity in keyword extraction. For example, stemming "expensive" to "expens" could lead to confusion, as it could be interpreted as either "expenses" or "expensive."

![214_Data Preparation](https://github.com/user-attachments/assets/c89f47e4-55df-4b67-934f-5fe263283eb9)


### MODELLING
Following data cleaning, we identified key themes in the reviews related to opportunities, skills, professors' experience, staff supportive and helpful, highly recommended, time, online learning, expensive fees, and other relevant topics.
To gain deeper insights into the positive and negative sentiments expressed in the reviews, we employed sentiment classification by applying Python.
Two models were trained and compared to determine the most effective approach:
  1.	Model from Scratch: A model was trained from the dataset.
  2.	Transfer Learning with DistrilBERT: A pre-trained DistrilBERT model was fine-tuned on our dataset, leveraging its            existing knowledge."

### Model 1 : Model from Scratch
By using Python, we uploaded the dataset and train the dataset.  By training the model, we split the data into an 80/20 training/testing ratio.  TF-IDF vectorization was then applied to convert the text data into numerical representation that could be understood by machine learning algorithm.  Finally, a logistic regression model was trained on the training set and evaluated on the testing set to assess its performance in classifying sentiment.

### Model 2 : Transfer learning with DistilBERT
DistilBERT was chosen for this project due to its use as a pre-trained model with a large amount of text data, allowing it to capture rich linguistic information.  Additionally, it is a smaller and faster version of BERT, while still maintaining a significant amount of BERT's original performance and yielding comparable results. 

Same steps as Model 1 were applied, with an additional step taken to ensure that all vectors are at the same size.  This step involved padding and masking.  Padding was used to ensure that all vectors are the same size and that all sentences are of the same length for efficient batch processing.  Masking was applied to ignore the padding tokens during processing, preventing the learning from artificial tokens created during the padding step.


### EVALUATION
### Model 1 : Model from Scratch
The logistic regression in model 1 achieved an 82.5% accuracy on the test set.
Regarding class-specific performance:
-  True Negative Rate: 50% of negative reviews were correctly identified.
-  True Positive Rate: 89% of positive reviews were correctly identified.

Overall, the model performed well with an 83% accuracy rate. However, negative class prediction was much less accurate than positive, as indicated by an F1-score of 50% for the negative class.  Furthermore, the macro average F1-score was higher than the weighted average, suggesting an imbalance in performance between the positive and negative classes.

![Model 1_Evaluation](https://github.com/user-attachments/assets/3240a21c-9a4b-40fe-9de4-6410574126e1)

In model 1, the positive review (new text review) is predicted accurately, however negative review (new text review) is wrongly predicted as negative. This misclassification indicates a challenge in the model's ability to differentiate between positive and negative sentiments effectively.

![Model 1_Text Prediction](https://github.com/user-attachments/assets/a8864247-0ccc-4431-ad1c-f53a92c41fe1)


### Model 2 : Transfer learning with DistilBERT
The logistic regression in model 2 achieved an 93.8% accuracy on the test set.
Regarding class-specific performance:
-  True Negative Rate: 91% of negative reviews were correctly identified.
-  True Positive Rate: 95% of positive reviews were correctly identified.
    
Overall, the model achieved high accuracy, precision, recall, and F1-scores, exceeding 90% for both positive and negative classes.  This robust performance is further evidenced by the overall accuracy of 94%.  The similarity between macro and weighted averages indicates that the model effectively handled class imbalance, demonstrating its ability to perform well across both positive and negative classification.

![Model 2_Evaluation](https://github.com/user-attachments/assets/db33f971-f381-48f7-aad8-1b290be19663)


In contrast to Model 1, Model 2 successfully predicted both positive and negative new text reviews accurately (same new text review as Model 1).  This suggests that Model 2 is better equipped to handle the nuances of sentiment analysis.

![Model 2_Text Prediction](https://github.com/user-attachments/assets/406b4554-b580-4e98-8dd3-415f09254441)


## RECOMMENDATION AND ANALYSIS
Leveraging transfer learning, Model 2 demonstrated superior performance in predicting both positive and negative reviews, achieving a higher accuracy rate than Model 1. This highlights the effectiveness of transfer learning in enhancing the model's ability to accurately classify sentiments.  

## Topic Modeling to identify strengths and weaknesses
Further identify the key topic within positive and negative reviews, Latent Dirichlet Allocation (LDA) was applied to extract the top 5 topics from positive and negative text review from model 2.  The result as per below:

Top 5 Positive text review
![Topic Modelling_Top 5 Positive review by LDA](https://github.com/user-attachments/assets/d17b8347-7a2c-4f5e-9131-aca1af5b1167)

Top 5 Negative text review
![Topic Modelling_Top 5 Negative review by LDA](https://github.com/user-attachments/assets/af1baf83-d386-49ea-aff1-498df04820d8)

X Education has received positive feedback for its experienced professors and supportive staff as well as better opportunities.  These are key strengths that contribute to a positive learning experience for students.  To attract more students, the school should emphasize the expertise and unique teaching methods of its professors.

However, high tuition fees have been identified as a potential barrier to enrolment.  To address this, X Education should conduct a comprehensive review of its fees and compare them to industry standards.  This will help ensure that the fees are reasonable and competitive.  Additionally, implementing promotions such as early bird discounts or group discounts can make the school's offerings more attractive to potential students, especially those who may be budget conscious.

While 72.5% of text reviews are positive, the conversion rate of 38.5% is lower than expected, suggesting a potential gap between customer satisfaction and actual purchasing behavior.  This discrepancy could be attributed to factors such as data bias due to a limited dataset.  To gain a more accurate understanding of customer sentiment, it is essential to analyze a larger volume of feedback using a trained model capable of handling a wider range of expressions and nuances.


## AI Ethics
Few AI Ethics are concerned when workings with data science project:
1.	Privacy:
A public dataset from reliable website has been used for this project to ensure compliance with the data privacy laws and regulations, including GDPR (General Data Protection Regulation) and CCPA (California Consumer Privacy Act).  "To further ensure compliance with PDPA (Perosnal Data Protection Act), we verified that our dataset did not contain any personally identifiable information, such as home addresses, dates of birth, or other sensitive data.

2.	Fairness
To mitigate potential bias in the dataset we selected, we ensured that the dataset does not contain any information related to sensitive attributes such as gender or race.  With excluding this sensitive data, we can avoid bias that could influence the model’s prediction and prevent the model from perpetuating bias or discrimination.

3.	Accuracy
Inaccurate predictions/analysis resulted inaccurate conclusion and lead to inadequate decision is make.  Hence, validation of accuracy and evaluation of the model performance is critical to allow users to understand the accuracy and also the limitations of the approaches applied.

4.	Transparency
Detail steps from dataset selection, data preparation, modelling until analysis and recommendations are encouraged to communicate to users are important.  With the transparency approach, this not only enhance the users understanding and clarity of data but also establish credibility and reassures users that the model's outcomes are reliable and not influenced by hidden biases or errors.

5.	Accountability
In practical, it is important to develop responsibility framework for each project to determine the person who accountability to the model applied and implementation.  This can ensure feedback from users are follow-up and also continuous improvement of the model.


## Source Codes and Datasets
[Upload your model files and dataset into a GitHub repo and add the link here. ](https://github.com/YeseyTeng/NYP_ITD214_Project)
