# Adike

This project is about building a sneaker recommendation system based on consumers/experts reviews.

### Source:
https://runrepeat.com

I scraped more than _800_ Adidas and Nike reviews from the above source consisting of summarized reviews broken into 3 sections:
* Bottom line
* Reasons __to__ buy
* Reasons __not to__ buy

## EDA

While scraping with Beautiful Soup I found out some inconsistencies in the HTML of the source and as a result I couldn't extract reviews for all the listed sneakers. I was able to get information for _472_ __Adidas__ and _372_ __Nike__ sneakers.

I cleaned the data using NLTK to prepare for NLP:
* Removed punctuations
* Lowercased
* Removed numbers
* Removed stop words
* Lemmatized
* Tokenized

I used LDA topic modeling, word clouds and vectorization with CountVectorizer for further data exploration and stop words selection. Time being the main factor, I stopped with these results:

* Bottom line

![topic1](https://github.com/JonBebi/Adike/blob/master/Visualizations/Bottom_line/topic1.png "Topic 1")
![topic2](https://github.com/JonBebi/Adike/blob/master/Visualizations/Bottom_line/topic2.png "Topic 2")
![topic3](https://github.com/JonBebi/Adike/blob/master/Visualizations/Bottom_line/topic3.png "Topic 3")
![topic4](https://github.com/JonBebi/Adike/blob/master/Visualizations/Bottom_line/topic4.png "Topic 4")
![top10](https://github.com/JonBebi/Adike/blob/master/Visualizations/Bottom_line/top10.png "Top 10 words")

* Reasons __not to__ buy

![topic1](https://github.com/JonBebi/Adike/blob/master/Visualizations/Con/topic1.png "Topic 1")
![topic2](https://github.com/JonBebi/Adike/blob/master/Visualizations/Con/topic2.png "Topic 2")
![topic3](https://github.com/JonBebi/Adike/blob/master/Visualizations/Con/topic3.png "Topic 3")
![topic4](https://github.com/JonBebi/Adike/blob/master/Visualizations/Con/topic4.png "Topic 4")
![top10](https://github.com/JonBebi/Adike/blob/master/Visualizations/Con/top10.png "Top 10 words")

* Reasons __to__ buy

![topic1](https://github.com/JonBebi/Adike/blob/master/Visualizations/Pro/topic1.png "Topic 1")
![topic2](https://github.com/JonBebi/Adike/blob/master/Visualizations/Pro/topic2.png "Topic 2")
![topic3](https://github.com/JonBebi/Adike/blob/master/Visualizations/Pro/topic3.png "Topic 3")
![topic4](https://github.com/JonBebi/Adike/blob/master/Visualizations/Pro/topic4.png "Topic 4")
![top10](https://github.com/JonBebi/Adike/blob/master/Visualizations/Pro/top10.png "Top 10 words")

## Modeling

I used NearestNeighbors cosine similarity to generate recommendations based on each review section. I created a function to pop-up in 4 different tabs in the browser:
* the most similar sneaker in my list compared to the user's input
* the first recommendation of that sneaker based on the bottom line
* the first recommendation of that sneaker based on the reasons not to buy
* the first recommendation of that sneaker based on the reasons to buy

I have some lines of code commented out in case I get the same recommendation for different review sections.

Unfortunately the source would not open the pages after a few tries. I did put a sleep timer to account for it, but it looks like it didn't help.
