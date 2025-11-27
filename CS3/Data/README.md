## How to obtain the data

1) Download the ACL IMDb Movie Reviews zipfile (Large Movie Review Dataset v1.0) from: https://ai.stanford.edu/~amaas/data/sentiment/
2) Download the IMDb Title Basics zpfile (title.basics.tsv.gz) from: https://datasets.imdbws.com/
3) Extract the title.basics.tsv from the zip file (don't need to unzip the reviews data as the dataset creation pipeline in the SCRIPTS code will do this for you)
4) Open up the SCRIPTS code on Colab
5) Upload the aclImd zip file and title.basics.tsv from your local device to your Colab content folder
6) Make sure the path length for the 2 datasets you uploaded to Colab is correctly typed into the dataset creation pipeline. Can copy and paste the path name from the content folder on the left.
7) Run the dataset creation pipeline from the scripts folder
8) This new merged dataset will be stored locally in your content folder on Colab and called "imdb_sentiment_with_genres.parquet"
