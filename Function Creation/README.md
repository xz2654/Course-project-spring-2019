## Function Creation: Using interpretable vector representation for search similar terms.

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
