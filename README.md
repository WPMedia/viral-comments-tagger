# viral-comments-tagger
 Predicting the Popularity of News Comments  

## Dataset
We built a Post News Comments dataset contains more than 20 million threading conversations with 300 million utterances that are labelled with rich features covers social, news, linguistic and temporal dimensions. 

### Features
* Social: dontagree, like, flag[9]
* (To-Do) News: type, category, section, pub_date, author
* Linguistic: polarity_scores[4], readability_flesch_kincaid_grade, readability_gunning_fog, readability_automated_readability_index, readability_coleman_liau_index, readability_sentence_count, readability_lexicon_count, readability_char_count, readability_sentence_avg_length, readability_lexicon_avg_length
* Temporal: day_of_week, hour_of_day, post_gap (in seconds)

## Experiments

### Linear Regression (LR.ipynb)

### Recurrent Neural Networks (RNN.ipynb)
