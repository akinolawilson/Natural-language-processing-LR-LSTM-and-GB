# NLP and sentiment analysis: Mobile phone data reviews 
___________________________________________________________________________________________________________________________________________________________________________________
## File content
This repository contains the notebooks that process, transform and model a dataset based on mobile phone reviews, sourced from [here](https://www.kaggle.com/masaladata/14-million-cell-phone-reviews). Three different modelling strategies are applied to the dataset in order to predict the sentiment of the review data and extract business intelligence (BI) from the data structure. 
<br>
The dataset is first prepared in a mannor which favours latter computation. Given the scope (1.4 million) and complexity (over 30 different author languages), the data is first reduced to contain only those authored in English. Moving on, the original sentiment is given on a scale of [0,10]. To reduce the task down to a more appropriate target space,  given the task of sentiment analysis, the data's score distribution is investigated to identify boundaries that are used to classify the sentiment polarities into three ordinal targets; {negative, neutral, positive}.    
<br>
The data is decomposed into two subsets, the auxiliary and textual components. The auxilliary data refers to any additional features excluding the textual information. It is used to extract market sentiment with regards to the origin country, website domain, manufacturers, mobile phone line and extact mobile model. The ensemble family described below produce a hierachical ranking of which events, with respect to each category, contribute the most to the given sentiement.
<br>
___________________________________________________________________________________________________________________________________________________________________________________
### Model architectures
<br><br>
## Auxiliary data
- Extreme gradient boosting 
- Light gradient boosting
- Ordered categorical graident boosting
<br>
## Textual data
- Gaussian radial basis expansion logistic regressor
- Convolutional contiunous bag of words & auxilliary categorical data embeddding concatenated network
- Long short-term memory contiunous bag of words & auxilliary categorical data embeddding concatenated network
- Bidirectional long short-term memory with attention (Bahdanau) contiunous bag of words & auxilliary categorical data embeddding concatenated network
___________________________________________________________________________________________________________________________________________________________________________________
