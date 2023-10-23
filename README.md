# Project Overview

This project aims to analyze how users evaluate restaurants using review data from [Tripadvisor](https://www.tripadvisor.com/). Especially, this is a topic analysis on restaurants in Zurich using BERTopic. Taks are divided in the following 4 steps:

1. Get restaurants list and html files from Tripadvior
2. Parse html files
3. Make dataset
4. Conduct topic analysis using BERTopic


# Requirenments

* python >=3.7
* selenium 3.141.0
* beautifulsoup4 4.11.1
* bertopic 0.15.0

The bertopic library can be installed as follows (see https://maartengr.github.io/BERTopic).
```
pip install bertopic
```

# How to use
There is a Jupyter Notebook corresponding to the above task. You can download these notebooks and just run the code step by step.

[1_getHtml.ipynb](https://github.com/kmkm0113/Essentials_project/blob/main/1_getHtml.ipynb)
- Get the list of restaurants with the following conditions: located in Zurich, offers dinner, and offers Swiss dishes
- Get html files of reviews of above restaurants
- **Note**: This task takes a lot of time because because we space out access to the website, taking into account server load.

[2_parseHtml.ipynb](https://github.com/kmkm0113/Essentials_project/blob/main/2_parseHtml.ipynb)
- Parse each html file and extract the following information: review date, rating, content (text)

[3_makeDataset.ipynb](https://github.com/kmkm0113/Essentials_project/blob/main/3_makeDataset.ipynb)
- Filter restaurants: with more than 50 reviews, "Swiss" is included in the top 2 genres
- Preprocessing: Remove newline tag ("\n")
- **Note**: This project uses BERTopic, which is based on sentence-transformer for embedding. Therefore, no preprocessing is needed. See "Should I preprocess the data" in [FAQ](https://maartengr.github.io/BERTopic/faq.html#should-i-preprocess-the-data).

[4_extractTopics.ipynb](https://github.com/kmkm0113/Essentials_project/blob/main/4_extractTopics.ipynb)
- Get embeddings of reviews
- Fit BERTopic model
- Visualize the extracted topics


