# BBC-News-Sub-categorization

*****************************************************************************

The following repository has implementations of text mining, clustering, graphs and networks, topic modelling codes in R to further categorize the categories of news on BBC.

*****************************************************************************

The dataset used is BBC news dataset -- 'bbc-fulltext' (http://mlg.ucd.ie/datasets/bbc.html)

It has 5 sub-topics in it - business, entertainment, politics, sport and tech

Note the following: 
1. '10combined' is a subset of dataset 'bbc-fulltext' in which ten files of each sub topic has been taken to have a small diversified dataset.
2. Names of all the files in the business, entertainment, politics, sport and tech sub-topics have been changed to format -- 'bus_001', 'ent_001', 'pol_001', 'spo_001', 'tec_001 ' (The code for changing the file names has also been attached in a folder called others)

*****************************************************************************
For Text Mining, the data was first loaded followed by creating a custom transformation function. This function takes a function as input, the input function should specify what transformation needs to be done. In this case, the input function would be one that replaces all instances of a character by spaces. In addition to that functions from the tm library were used like-- tolower, removeNumbers etc.

We continue exploring the corpus to find 'typos' that can be replaced. After performing more suitable functions, we come with a clean corpus. Stemming is then performed on it. Now, we convert the corpus to document term matrix aka DTA. We mine texts from this DTA -- find frequency, sorting, cumulative frequencies, findAssocs. We then plot a histogram and a wordcloud using the most frequent words.

*****************************************************************************

For Clustering, the operations on the corpus are similar to the previous experiment in terms of cleaning the document and converting the corpus into a DTM. We then perform convert the DTM to a standard matrix and then perform hclust which does agglomerative hierarchical clustering. We also perfrom Kmeans Clustering on it with variable values of K. 

*****************************************************************************

For Topic Modelling, the operations on the corpus are similar to the previous experiment in terms of cleaning the document and converting the corpus into a DTM. We then collapse the matrix by summing columns, extract the filenames for rownames etc. We then use the 'topicmodels' package and in that use the LDA function with the Gibbs sampling option, initialise the parameters and run the LDA function and write the results to the file with top 6 topics. 

*****************************************************************************

For Network Graphs, the aim is to find suitable relationships between different documents in the collection of interest. The operations on the corpus are similar to the previous experiment in terms of cleaning the document and converting the corpus into a DTM. We then calculate cosine similarity. We write files to disk for mapping rows to filenames, cosine similarity, adjacency matrix etc.
Now, we visualize the relationship using Gephi. Gephi (https://gephi.org/) is an open source, Java based network analysis and visualisation tool. The final output is stored as png file and the .gephi file is also attached.

Note: For inputting the adjacency matrix file into gephi, replace all the ',' to ';' from the AdjacencyMatrix.csv and then open the file in gephi with undirected graphs.

*****************************************************************************

Thank you Kailash Awati for the inspiration/code and beautifully explaining concepts in your blog -- https://eight2late.wordpress.com




