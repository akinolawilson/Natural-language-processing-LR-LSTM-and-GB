# NLP and sentiment analysis: Mobile phone data reviews 
_________________________________________________________________________________________________________________________________________________________________________________
## File content
This repository contains the notebooks that process, transform and model a dataset based on mobile phone reviews, sourced from [here](https://www.kaggle.com/masaladata/14-million-cell-phone-reviews). Three different modelling strategies are applied to the dataset in order to predict the sentiment of the review data and extract business intelligence (BI) from the data structure. 
<br><br>
The dataset is first prepared in a mannor which favours latter computation. Given the scope (1.4 million) and complexity (over 30 different author languages), the data is first reduced to contain only those authored in English. Moving on, the original sentiment is given on a scale of [0,10]. To reduce the task down to a more appropriate target space,  given the task of sentiment analysis, the data's score distribution is investigated to identify boundaries that are used to classify the sentiment polarities into three ordinal targets; {negative, neutral, positive}.    
<br>
_________________________________________________________________________________________________________________________________________________________________________________
## Model architectures
The data is decomposed into two subsets, the auxiliary and textual components. The auxilliary data refers to any additional features excluding the textual information. It is used to extract market sentiment with regards to the origin country, website domain, manufacturers, mobile phone line and extact mobile model. The ensemble family described below produce a hierachical ranking of which events, with respect to each category, contribute the most to the given sentiement.
<br>
### Auxiliary data
- Extreme gradient boosting 
- Light gradient boosting
- Ordered categorical gradient boosting
<br>
The textual component is first modelled using a classical statistical model, a logistic regressor combined with a Gaussian radial basis function expansion of the feature space. 3 different textual parameterisations are trial; unigram, bigram and trigram tokenisations. To improve upon the model, three deep networks that utilise the entire dataset are built. The novel attention mechanism is applied in the most complex model, leading to the most desirable results.

### Textual data
- Gaussian radial basis expansion logistic regressor
- Convolutional contiunous bag of words & auxilliary categorical data embeddding concatenated network
- Long short-term memory contiunous bag of words & auxilliary categorical data embeddding concatenated network
- Bidirectional long short-term memory with attention (Bahdanau) contiunous bag of words & auxilliary categorical data embeddding concatenated network
<br>
_________________________________________________________________________________________________________________________________________________________________________________

## Future work

Explainability is key during the application of sentiment analysis in a business environment. It enables informed decision making with respect to the data anaylsis and it's interpretation. A variational autoencoder trained on the textual information can result in such explainability. To achieve this, the collection of attributes described at the start of the Data_exploration_and_preprocessing.ipynb need to have their relative position in the tokenized extracts tag. These will enable a variational autoencoder to learn sentiment about the given attributes.  


