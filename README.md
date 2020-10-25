# RuReviews: An Automatically Annotated Sentiment Analysis Dataset for Product Reviews in Russian

This repository contains an automatically collected dataset for sentiment analysis of product reviews in Russian, which were created within the paper ["Sentiment Analysis of Product Reviews in Russian using Convolutional Neural Networks"](https://ieeexplore.ieee.org/document/8807792). Additionally, we published pre-trained word embeddings.

The paper with a comprehensive description of these models can be found [here](http://www.dialog-21.ru/media/5017/smetaninsi-029.pdf).
Citation:
```
@INPROCEEDINGS{Smetanin-SA-2019,
  author={Sergey Smetanin and Michail Komarov},
  booktitle={2019 IEEE 21st Conference on Business Informatics (CBI)},
  title={Sentiment Analysis of Product Reviews in Russian using Convolutional Neural Networks},
  year={2019},
  volume={01},
  number={},
  pages={482-486},
  doi={10.1109/CBI.2019.00062},
  ISSN={2378-1963},
  month={July}
}
```

## Dataset Overview

The training dataset was collected from reviews on top-ranked goods form the major e-commerce site in Russian, where user-ranked scores were used as class labels on a 5-point scale. Since the same words in different product categories may have different sentiment polarity, it was decided to collect reviews only from one category, namely "Women’s Clothes and Accessories" category. It helped to get the collected dataset to consists of 821k automatically labelled reviews.

According to the obtained data, in some cases, it is complex task to correctly evaluate reviews with the same texts. For example, the review text “Fine” (translation from Russian into English) has 42.45% reviews with a score of “5”, 36% reviews with a score of “4”, 29.25% reviews with a score of “3”, and 0.94% reviews with a score of “2”. It is clear that such contradictions in the training dataset tend to affect the classification score. Therefore, we decided to mark these reviews with the class labels, which are the most common for these texts in the collected dataset. Moreover, sometimes it is also difficult to distinguish reviews with the close score values, e.g. reviews with score “1” and “2” or with score “4” and “5”. To overcome this issue, we transformed 5-point scale to 3-point scale by combining reviews with “1” and “2” into one “negative” class and reviews with “3” and “5” scores into another one “positive” class. Thus, the 5-star rating scale collapsed into 3 classes: negative, neutral, and positive reviews.

Since the data were collected from the top-ranked goods with high average rating, the amount of positive reviews considerably exceeded the amount of neutral and negative reviews. At the same time, we have no information about real-life class distribution for reviews, that is why we decided to use an undersampling technique to deal with imbalanced data. For each class 30k of reviews were randomly selected to make balanced dataset.

## Pre-Trained Word Embeddings
The sentiment classification model was trained on the top of pre-trained Word2Vec embeddings. Texts were pre-processed by [Ekphrasis](https://github.com/cbaziotis/ekphrasis) toll, which helps to perform spell correction, word normalization and segmentation and allows to specify which tokens should be omitted, normalized or annotated with special tags. 

**Pre-trained 300 dimensional embeddings may be downloaded at the following link: [rer.300d.txt](https://yadi.sk/d/CwxIRiOZo-ss4A)**. 

## Documentation and How to report bugs
* Keras documentation: [https://keras.io/documentation/](https://keras.io/documentation/).
* Ekphrasis documentation: [https://github.com/cbaziotis/ekphrasis](https://github.com/cbaziotis/ekphrasis).
* Scikit-learn documentation: [http://scikit-learn.org/stable/documentation.html](http://scikit-learn.org/stable/documentation.html). 
* If you find any issues, please open a bug here on GitHub.

## License
See [LICENSE](LICENSE).
