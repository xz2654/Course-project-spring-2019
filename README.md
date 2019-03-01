# Course project (spring 2019)

NimbleMiner is open-sourced application that allows users to interact with word embedding to rapidly create lexicons of similar terms, conduct weakly supervised labeling, and implement text mining. 

The methods that the application uses are described in this [paper](https://github.com/mtopaz/Course-project-spring-2019/blob/master/refs/JBI.2019.NimbleMiner.pdf).

![Image](https://github.com/mtopaz/Course-project-spring-2019/blob/master/Fig1.jpg)

You will also need the links below to complete your project:
* [Application NimbleMiner](https://github.com/mtopaz/NimbleMiner)


## Assignment 1: Using multiple models in parallel to improve search quality in NimbleMiner application.

The NimbleMiner app builds and uses one word2vec model for an iterative search for terms. 

You should complete the following tasks:
1. Build additional word embedding models - Glove and elmo.
1. Use three models (word2vec, Glove and elmo) in parallel during each search iteration. Think  how to combine the search results of these three models. 
1. Compare the effectiveness of using one and multiple models .

For carrying out a project, please note the following instructions:

1. Create new fork of the [NimbleMiner app repository](https://github.com/mtopaz/NimbleMiner).

2. Change the code in NimbleMiner.R:

2.1. Build additional models:

* In the app (NimbleMiner.R) see the function buildModels() with training the word2vec model. 
* Write the functions buildModel_Glove() and buildModel_Elmo() to NimbleMiner.R for building new models. The output model files should be named trainGlove and trainElmo accordingly.
* Edit the call parameters of these functions in buildModels() function. This function will be called by user click on button 'Build model' (tab. 1.Model builder). You can add additional user settings and messages to the app. 

2.2. Search for similar terms in models:

* In the app (NimbleMiner.R) see the function findSimilarTerms() with search term in word2vec model. 
* Update  function findSimilarTerms() by search in additional models. This function will be called by user click on button 'Find similar terms for new simclins' (tab. 2. Simclin explorer). You can add additional user settings and messages to the app. 

3. Make commit in your fork and pull request for merge.

## Assignment 2: Using interpretable vector representation for search similar terms.

For completing this assiggnment you should implement using new word embedding model according this [paper](https://github.com/mtopaz/Course-project-spring-2019/blob/master/refs/JBI.2019.Similar-words.pdf). This paper suggests method for building word vectors, which the meaning and relative importance of dimensions is transparent to inspection.

You should complete the following tasks:
1. Build additional word embedding model according this paper.
1. Use this model for search similar terms.
1. Compare the effectiveness of using this and word2vec models.

For carrying out a project, please note the following instructions:

1. Create new fork of the [NimbleMiner app repository](https://github.com/mtopaz/NimbleMiner).

2. Change the code in NimbleMiner.R:

2.1. Build additional model:

* In the app (NimbleMiner.R) see the function buildModels() with training the word2vec model. 
* Write the function buildModel_WS().
* Edit the call parameters of these functions in buildModels() function. This function will be called by user click on button 'Build model' (tab. 1.Model builder). You can add additional user settings and messages to the app. 

2.2. Search for similar terms in models:

* In the app (NimbleMiner.R) see the function findSimilarTerms() with search term in word2vec model. 
* Update  function findSimilarTerms() by search in additional model. This function will be called by user click on button 'Find similar terms for new simclins' (tab. 2. Simclin explorer). You can add additional user settings and messages to the app. 

3. Make commit in your fork and pull request for merge.

**References:**
_Smalheiser, N. R., Cohen, A. M., & Bonifield, G. (2019). Unsupervised Low-Dimensional Vector Representations for Words, Phrases and Text that are Transparent, Scalable, and produce Similarity Metrics that are not Redundant with Neural Embeddings. Journal of biomedical informatics, 103096._

## Assignment 3: Using external vocabularies to build start set of simclins. 

Integrate terminology (like [SNOMED](https://en.wikipedia.org/wiki/SNOMED_CT) or [wordnet](https://wordnet.princeton.edu/)) to jump-start similar word search (Step 1-2): Currently, users need to add starting target words on their own. What if we have integrated some kind of vocabulary that will match user’s entered first words to a larger set of synonyms that might make their life easier.  

We can query existing terminologies or synonym lists (like the ones downloadable [here](http://arrowsmith.psych.uic.edu/arrowsmith_uic/word_similarity_metrics.html) from this [article](https://github.com/mtopaz/Course-project-spring-2019/blob/master/refs/JBI.2019.NimbleMiner.pdf)) from medical or general domains to accomplish that- and there are several potentially creative ways of going about it. 

## Assignment 4: Using features extraction methods for search additional similar terms.

For notes review in stage 5, we need to find ways to highlight important features (in our case these are words and expressions) from machine learning that are associated with positive predictions. Common feature selection methods are least absolute shrinkage and selection operator (LASSO) or minimum redundancy-maximum relevance (mRMR) (like [here](https://www.ncbi.nlm.nih.gov/pubmed/30153212)). This [paper](https://www.kdd.org/kdd2016/papers/files/rfp0573-ribeiroA.pdf) present an interesting approach and an R package for feature selection and a neat user interface. We can have “voting” between the models for the most informative features. Other options are welcome.    

## Assignment 5: Improving machine learning modeling (stage 4, fig 1).

We need to find ways to keep the user out of choosing the best machine learning model for labeled text classification. We might think of running several machine learning models (like decision trees, random forests, SVM, recurrent neural network) and then selecting the best performing model for predictions. Alternatively, we might think of combining several models and then creating “averaged” predictions. There are several other alternatives we can discuss. 

Good luck!
