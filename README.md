# Apply Word2vec on Harry Potter Series :smile:
https://medium.com/@patrickhk/practice-ntlk-word2vec-pca-wordcloud-jieba-on-harry-potter-series-and-chinese-content-ca6f845b3293

I will briefly demonstrate how to apply NLTK (Natural Language Toolkit) and Word2Vec to do some basic analysis on Harry Potter Series, then visualize the relation of word vectors by PCA/wordcloud.

Let’s go to Word2vec, I will use the Word2vec package from gensim to demonstrate. What we does in Word2vec is to put the words into an embedding space so similar words will have closer distance.<br/>

Word2vec expects the input as a list of sentences, we can create a function to read the txt, tokenize and create the list. We can make use of gensim.utils.simple_preprocess and yield function to do this. We can adjust some threshold to keep word with min or max characters. For example if min_len=2 , the word “a” will not be kept in your model.<br/>
![p1](https://cdn-images-1.medium.com/max/800/1*PXM3S4nsmvlcS29t2-aRTQ.png)<br/>

Then we pass the content into gensim.models.Word2Vec, we can fine tune the hyperparameters such as window size and embedding size. Generally speaking the higher the embedding size, the larger capacity the model to learn the semantic relationship between word vectors. Training is very fast in Word2Vec, much faster than in LSTM due to different structure.<br/>

![p2](https://cdn-images-1.medium.com/max/800/1*ePr30n-4QHDyi_QecdNuUQ.png)<br/>

## See the cosine similarity of words:
We can see which words are most similar to our target words. Being similar doesn’t mean must have similar meaning, we can regard them as having some sort of relationship.<br/>
![p3](https://cdn-images-1.medium.com/max/800/1*XXnGWDg1N6a54d13eWllqA.png)<br/>

We try the word “fight” in our Word2vec model and get the above 10 words. The top 3 results “kill, die, control” are obviously related to “fight”. Initially I have no idea what is kedavra and avada, then I google and find that “Avada Kedavra” is the spell to make Instant death in Harry Potter world. Well, these two words are definitely related to “fight” for sure. <br/>

## Find the odd one our of a list of words:
Except finding the most similar words, we can also find the odd word<br/>
![p4](https://cdn-images-1.medium.com/max/800/1*S2vMlYrM_zQDAujC8iEUQA.png)<br/>
I am glad the model doesn’t return “harry” for me.<br/>

## Get the cosine similarity between words:
![p5](https://cdn-images-1.medium.com/max/800/1*hw9LbrHqlfhndEq5Rk97tA.png)<br/>
We can get the similarity value between words for comparison. When I was young, people always hope Hermione can be together with Harry. You know what, according to this model maybe Harry should be married with Ron as they are more related to each other.

-------------------------------------------------------------------------------------------------------------------------------------
### More about me
[[:pencil:My Medium]](https://medium.com/@patrickhk)<br/>
[[:house_with_garden:My Website]](https://www.fiyeroleung.com/)<br/>
[[:space_invader:	My Github]](https://github.com/fiyero)<br/>
