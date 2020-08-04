# Tag recommendation using Word-embeddings and Weighted graph

Application if deployed ![here](https://tag-recommender.herokuapp.com/)

### Instructions:

This application predicts related tags to a given input word, based on weighted graph generated from ![Data Science Stack Exchange](https://api.stackexchange.com/2.2/questions?page=1&pagesize=100&order=desc&sort=activity&site=datascience)
Data Collection - REST API and extract tags from json format of requested url.

##### Consider the following example of extracted tags.
[Row 1] k-means, clustering, python
[Row 2] machine-learning, neural-network, python
[Row 3] machine-learning, keras, neural-network, python
...

From this list of tags, a Weighted Graph can be constructed where each tag in each row of data
is related to other tags in the same row and the edge weight in the graph is incremented each
time the tags co-occur.

Another approach is Skip-gram architectue of word-embeddings. This has been implemented in .ipybn file

##### Codes and Data

1. Weighted_graph_tags_predict.ipybn contains `data extraction with REST API, graph construction with NetworkX and skip-gram architecture for tags prediction using pytorch`

2. webapp/Data/ :- contains pickle file of graph constructed of similar words, test.txt and test2.txt contains all related raw words extracted from Data Science Stack Exchange.

3. tagsenv :- environment for the project.

##### Instructions to run

From the root directory of the repo.

1. Run `$ pip install -r requirements.txt`

2. $pip install pytorch (only for skip-gram architecture in Ipybn)

3. to run app locally :- got to application.py, and `uncomment app.run` and finally run `python application.py`
