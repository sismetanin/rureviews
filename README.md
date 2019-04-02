# RuReviews: An Automatically Annotated Sentiment Analysis Dataset for Product Reviews in Russian

## Overview
This repository contains an automatically collected dataset for sentiment analysis of product reviews in Russian. 

### Pre-trained Word Embeddings
The sentiment classification model was trained on the top of pre-trained Word2Vec embeddings. Texts were pre-processed by [Ekphrasis](https://github.com/cbaziotis/ekphrasis) toll, which helps to perform spell correction, word normalization and segmentation and allows to specify which tokens should be omitted, normalized or annotated with special tags. 

**Pre-trained 300 dimensional embeddings may be downloaded at the following link: [rer.300d.txt](https://yadi.sk/d/CwxIRiOZo-ss4A)**. 

### Documentation and How to report bugs
* Keras documentation: [https://keras.io/documentation/](https://keras.io/documentation/).
* Ekphrasis documentation: [https://github.com/cbaziotis/ekphrasis](https://github.com/cbaziotis/ekphrasis).
* Scikit-learn documentation: [http://scikit-learn.org/stable/documentation.html](http://scikit-learn.org/stable/documentation.html). 
* If you find any issues, please open a bug here on GitHub.