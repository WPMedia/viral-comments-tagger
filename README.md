# Predicting the Popularity of News Comments

## Task
Predict the total number of comments a thread will receive (Popularity) based on the comments received in the first 30 minutes.

## Dataset
We built a Post News Comments dataset contains more than 20 million threading conversations with 300 million utterances that are labelled with rich features covers social, news, linguistic and temporal dimensions. 
```
s3://wp-dw-sandbox/yuy/tmp_yuy_30_mins_comments_v7/
```
### Features
* **Social:** dontagree, like, flag_*[9]
* **(To-Do) News:** type, category, section, pub_date, author
* **Linguistic:** polarity_scores_*[4], readability_flesch_kincaid_grade, readability_gunning_fog, readability_automated_readability_index, readability_coleman_liau_index, readability_sentence_count, readability_lexicon_count, readability_char_count, readability_sentence_avg_length, readability_lexicon_avg_length
* **Temporal:** day_of_week, hour_of_day, post_gap (in seconds)

## Experiments

### Linear Regression
see LR.ipynb

### Recurrent Neural Networks
see RNN.ipynb

### Flatten Features (Comment Level -> Thread Level)
For the regression model, the feature set is flattened by getting mean and sum on the thread level for most features. The temporal features are only kept for the first comment in each thread.

### Rescale Target Values
We experimented with rescaling the target value (total thread reply count) by

![alt text](https://latex.codecogs.com/svg.latex?%5Chat%7By%7D%3D%20%5Cbegin%7Bcases%7D%201%26%20y%20%5Cgeq%20k%5C%5C%20y%20/%20k%26%20y%20%3C%20k%20%5Cend%7Bcases%7D
)

where k is the ceiling value.

The experiment results show that rescaled target values help avoid vanishing & exploding gradient in RNN.
