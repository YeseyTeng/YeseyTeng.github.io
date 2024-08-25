---
layout: post
author: Name
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
Provide an overview of your team's project business goals and objectives and state the objective that you are working on. 

The dataset has been obtained from Kaggle and pertains to the conversion records of inquirers for course enrolment at X Education. This institution offers a diverse range of courses including Banking, Investment and Insurance, Human Resource Management, Media and Advertising, Service Excellence, Travel and Tourism, Financial Management, International Business, and others.

The dataset provides a comprehensive overview of inquirers, encompassing their demographics such as city and country, occupations, online behavior (e.g., time spent on website and page views per visit), lead sources, asymmetrical information, and most importantly, their conversion status (i.e., whether they converted or not).

Our primary business goals revolve around increasing the conversion rate, which are further divided into four sub-objectives.  Business Objective 1 involves analyzing the factors that influence conversion success.  Business Objective 2 aims to identify the factors that can increase the time spent on the website.  Business Objective 3 is to comprehend the strengths and weaknesses of the institution.  Lastly, Business Objective 4 focuses on analyzing the effectiveness of marketing strategies.


## Work Accomplished
Document your work done to accomplish the outcome

### Data Preparation
To achieve a comprehensive understanding of the institution's strengths and weaknesses (objective 3), we will employ text analytics capabilities within KNIME and Python to conduct a detailed analysis of reviews and comments.  This analysis will involve sentiment classification, enabling us to identify the core topics and sentiments expressed by our customers.  By gaining these insights, we can develop targeted strategies to enhance our offerings and optimize conversion rates.

At first, we employ KNIME for text review on first glance by the following steps:
  1.	CSV reader
  2.	String to document
  3.	Text processing:
      3a.	Stop word filter is used only
      3b.	Punctuation Erasure, N Chars Filter, Case Converter and Stop word filter are used
      3c.	Punctuation Erasure, N Chars Filter, Case Converter, Stop word filter and Porter Stemmer are used
  4.	Keygraph Keyword extractor
  5.	Tag Cloud

3b text proecessing is applied at the end 
### Modelling
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

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
