.===================================================================================
# Predict IMDB movie rating

    by Xi Guo   
    
    11/29/2017


===================================================================================
# Summary:

IMDB movie data (5000 rows) were scrapped and analyzed using python.

To predict the IMDB ratings, we first extracted some features from movie posters, and selected 40 best features to build a ridge regression model.

The final model has an mean squared error (MSE) of 0.7.



===================================================================================
# STEP 2: 

Load 5000+ movie titles from the JSON file 'movie_budget.json'

Then search those titles from IMDB website to get the real IMDB movie links

It will generate a JSON file 'fetch_imdb_url.json' containing movie-link pairs

$ scrapy crawl fetch_imdb_url -o fetch_imdb_url.json


===================================================================================
# STEP 3: 

Scrape 5000+ IMDB movie information

This step will load the JSON file 'fetch_imdb_url.json', go into each movie page, and grab data

This step will generate a JSON file 'imdb_output.json' (20M) containing detailed info of 5000+ movies

It will also download all available posters for all movies.

A total of 4907 posters can be downloaded (998MB). Note that I am not sure if I can upload all those posters into github,
so I only uploaded a few. You can see from my code how to use scrapy to grab them all. 

$ scrapy crawl imdb -o imdb_output.json


===================================================================================
# STEP 4: 

Perform face recognition to count face numbers from all posters

This step will save result into JSON file 'image_and_facenumber_pair_list.json'

$ python detect_faces_from_posters.py

