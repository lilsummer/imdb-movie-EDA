.===================================================================================
# Predict IMDB movie rating

    by Xi Guo   
    11/29/2017

[My blog](https://fulltimevirus.wordpress.com)

===================================================================================
# Summary:

IMDB movie data (5000 rows) were scrapped and analyzed using python.

To predict the IMDB ratings, we first extracted some features from movie posters, and selected 40 best features to build a ridge regression model.

The final model has an mean squared error (MSE) of 0.7.

The results of the prediction is in **ridge_40_feature_result.csv**

===================================================================================
# 1-Visulization-EDA: 

[Click here to see a wrapped ipynb version](http://nbviewer.jupyter.org/github/lilsummer/imdb-movie-EDA/blob/master/1-visualization-EDA.ipynb)

===================================================================================
# 2-model-tensorflow-improve-add-feature: 

* Training and testing data were split in 8:2 ratio. Cross validation were used internally in search of the best number of features. 

* We used regression model on tensorflow to predict the ratings. The best model is the ridge regression model with 40 features. In this case, deep learning might not be necessary since the data set is small. 

The feature extraction step is in **3-extract-feature-poster.ipynb**

[Click here to see a wrapped ipynb version](https://nbviewer.jupyter.org/github/lilsummer/imdb-movie-EDA/blob/master/2-model-tensorflow-improve-feature.ipynb)

===================================================================================
# 3-Extract-features-poster: 

* This illustrates the steps to extract major colors from movie posters by using kmeans clustering.

[Click here to see a wrapped ipynb version](http://nbviewer.jupyter.org/github/lilsummer/imdb-movie-EDA/blob/master/3-extract-feature-poster.ipynb)

===================================================================================
# 4-added-feature

* A small analysis on the extracted RGB features.

[Click here to see a wrapped ipynb version](http://nbviewer.jupyter.org/github/lilsummer/imdb-movie-EDA/blob/master/4-added-feature.ipynb)
