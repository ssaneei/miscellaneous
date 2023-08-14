# miscellaneous

Here you see an infrastructure to use for a systematic way of transforming a large set of words in a semantic space into a smaller set of clusters with meaningful interpretations, which can be useful for further analysis or understanding of the underlying semantic relationships among words.


1. Projection into Common Semantic Space: 
  The process starts with 10,470 words in a semantic feature space.
  These words are projected into a 4-dimensional common semantic principal component (PC) space.
  This is likely done to reduce the dimensionality and capture the most important semantic information.

2. Robust Convex Hull Estimation:
  An iterative convex hull estimation procedure is used to identify the most important words in the 4-dimensional semantic PC space.
  At each iteration, 80% of the words (8,376 words) are randomly selected, and the convex hull (a geometric shape encapsulating these points) is calculated in the     4D semantic space.
  This process is repeated 100 times to obtain a set of words that appeared on the convex hull in at least one iteration.

3. Word Clustering:
   The 458 words from the previous step are then subjected to k-means clustering in the 4-dimensional semantic space.
   K-means is a clustering algorithm that groups data points into clusters based on their similarity.
   
4. Selecting Number of Clusters:
   To determine the number of clusters, the authors compute the fraction of variance that the clusters collectively explain in the mean semantic model for each         significant semantic area defined by the PrAGMATiC atlas.
   The goal is to find the smallest number of clusters that account for at least 10% of the variance in each PrAGMATiC area. In this case, the chosen number of clusters is 12.
   
5. Maximizing Cluster Stability:
   To ensure the stability of the clusters, the k-means clustering is repeated 100 times, and the model with the highest average variance explained across the         PrAGMATiC areas is selected.
   K-means++ initialization is used for each repetition to enhance the quality of clustering.
   
6. Manual Labeling of Clusters:
   Finally, after obtaining the stable clusters, labels are assigned to these clusters by inspecting the words that appear in each cluster.
   This manual labeling step helps interpret the meaning and context of each cluster.
