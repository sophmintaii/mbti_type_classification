# MBTI TYPE CLASSIFICATION

## Authors
* [Myntiuk Sofiia](https://github.com/sophmintaii)
* [Sydorenko Valeriia](https://github.com/Lero4ka13) 

## Datasets
* [Social media posts & MBTI types](https://www.kaggle.com/datasnaek/mbti-type)
* [Twitter slang](https://www.kaggle.com/gogylogy/twitterslang)

## Description
Myers-Briggs Type Indicator (MBTI) differentiates people into 16 types, assigning values for four categories: Introversion or Extraversion, Sensing or Intuition, Thinking or Feeling, Judging or Perceiving. To get the most common type name, one takes a letter from each of the dichotomies’ values and abbreviates them into the result (e.g., ENFJ, ISTP).

However, it appears to be pretty hard to get the exact type based on the social media posts. It may be since most people write texts in a pretty similar way. Also, some of the dichotomies may be affecting writing style more than the others, so, for example, if we can correctly determine whether the author is extroverted or introverted, it may be more challenging to find them on the Sensing-Intuition scale.

In the process of consulting the literature, we discovered that there are also four subcategories of personality types, and it may be easier to distinguish between them instead of all the 16 types.

Henceforth, we decided to look not only into classification into exact four-letter types but also to investigate whether the classification will perform better for mentioned subcategories and dichotomies.

Moreover, we realized that there are not only words that play a role in telling apart personality types, but also some text features that may be lost after preprocessing, such as text length, emojis and emoticons, punctuation, sentiment, capitalization, slang usage. Consequently, we decided to add some handcrafted features to show their usefulness for type determination.

## Project pipeline
* Extract handcrafted features:
  * text length
  * capitalization
  * punctuation usage
    * general 
    * exclamation marks
  * slang usage
  * sentiment of the text
  * emoticons usage
* Preprocess the text:
  * cleaning
    * links
    * MBTI types names
    * numbers
    * emojis
    * redundant spaces
    * punctuation
    * stop-words
  * lemmatization
* Vectorization - used TF-IDF
* Model training and evaluation:
  * Complement Naive Bayes Classifier
  * Random Forest Classifier
  * LightGBM

For more details, model scores and other results, see ```mbti_prediction.ipynb```.

## Prerequirements and usage
```bash
pip3 install -r requirements.txt 
```
```bash
jupyter notebook mbti_prediction.ipynb
```

