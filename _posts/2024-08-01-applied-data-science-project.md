---
layout: post
author: Name
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
The dataset has been obtained from Kaggle and pertains to the conversion records of inquirers for course enrolment at X Education. This institution offers a diverse range of courses including Banking, Investment and Insurance, Human Resource Management, Media and Advertising, Service Excellence, Travel and Tourism, Financial Management, International Business, and others.

The dataset provides a comprehensive overview of inquirers, encompassing their demographics such as city and country, occupations, online behavior (e.g., time spent on website and page views per visit), lead sources, asymmetrical information, and most importantly, their conversion status (i.e., whether they converted or not).

Our primary business goals revolve around increasing the conversion rate, which are further divided into four sub-objectives.  Business Objective 1 involves analyzing the factors that influence conversion success.  Business Objective 2 aims to identify the factors that can increase the time spent on the website.  Business Objective 3 is to comprehend the strengths and weaknesses of the institution.  Lastly, Business Objective 4 focuses on analyzing the effectiveness of marketing strategies.


## Work Accomplished
To achieve a comprehensive understanding of the institution's strengths and weaknesses (objective 3), we will employ text analytics capabilities within KNIME and Python to conduct a detailed analysis of reviews and comments.  This analysis will involve sentiment classification, enabling us to identify the core topics and sentiments expressed by our customers.  By gaining these insights, we can develop targeted strategies to enhance our offerings and optimize conversion rates.

### Data Preparation
Initially, we employed KNIME for a preliminary text review using the following steps:
  1.	CSV Reader: Loaded the review data from a CSV file.
  2.	String to Document: Converted text strings into KNIME documents.
  3.	Text Processing:
      o	Option 1: Applied a stop word filter to remove common words.
      o	Option 2: Utilized a more comprehensive text cleaning process, including punctuation removal, N-character filtering,                   case conversion, and stop word removal.
      o	Option 3: Implemented a similar process as Option 2, but also included Porter stemming to reduce words to their root                   form.
  4.	Keygraph Keyword Extractor: Identified key terms within the processed text.
  5.	Tag Cloud: Visualized the frequency of extracted keywords.

Option 2, excluding stemming, was applied at the end of the process as it provided more nuanced sentiment information. Stemming was not included in the text processing to avoid potential ambiguity in keyword extraction. For example, stemming "expensive" to "expens" could lead to confusion, as it could be interpreted as either "expenses" or "expensive."
![214_Data Preparation](https://github.com/user-attachments/assets/c89f47e4-55df-4b67-934f-5fe263283eb9)


### Modelling
Following data cleaning, we identified key themes in the reviews related to opportunities, skills, professors' experience, staff supportive and helpful, highly recommended, time, online learning, expensive fees, and other relevant topics.
To gain deeper insights into the positive and negative sentiments expressed in the reviews, we employed sentiment classification.
Two models were trained and compared to determine the most effective approach:
  1.	Model from Scratch: A model was trained from the dataset.
  2.	Transfer Learning with DistrilBERT: A pre-trained DistrilBERT model was fine-tuned on our dataset, leveraging its            existing knowledge."

Model 1 : Model from Scratch
By using Python, we uploaded the dataset and train the dataset.  By training the model, we split the data into an 80/20 training/testing ratio.  TF-IDF vectorization was then applied to convert the text data into numerical representation that could be understood by machine learning algorithm.  Finally, a logistic regression model was trained on the training set and evaluated on the testing set to assess its performance in classifying sentiment.

Model 2 : Transfer learning with DistilBERT
DistilBERT was chosen for this project due to its use as a pre-trained model with a large amount of text data, allowing it to capture rich linguistic information.  Additionally, it is a smaller and faster version of BERT, while still maintaining a significant amount of BERT's original performance and yielding comparable results. 

Same steps as Model 1 were applied, with an additional step taken to ensure that all vectors are at the same size.  This step involved padding and masking.  Padding was used to ensure that all vectors are the same size and that all sentences are of the same length for efficient batch processing.  Masking was applied to ignore the padding tokens during processing, preventing the learning from artificial tokens created during the padding step.

Topic Modeling
To identify the key topic within positive and negative reviews, topic modeling using Latent Dirichlet Allocation (LDA) was applied to extract the top 5 topics from positive and negative text review.  The result as per below:

Top 5 Positive text review
![Topic Modelling_Top 5 Positive review by LDA](https://github.com/user-attachments/assets/d17b8347-7a2c-4f5e-9131-aca1af5b1167)

Top 5 Negative text review
![Topic Modelling_Top 5 Negative review by LDA](https://github.com/user-attachments/assets/af1baf83-d386-49ea-aff1-498df04820d8)

### Evaluation



![Model 1_Evaluation](https://github.com/user-attachments/assets/3240a21c-9a4b-40fe-9de4-6410574126e1)


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis
Explain the analysis and recommendations

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
