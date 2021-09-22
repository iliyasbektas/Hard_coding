## Hard coding

In this project, I create hashing algorithms from scratch and apply k-means clustering algorithm to Amazon food review data.

For this task, we are dealing with hashing algorithms. In particular we will implement hash functions and an algorithm called HyperLogLog (HLL). This reference may be useful also.

There are many scenarios where we need to know (or at least estimate) the cardinality of a dataset, e.g., statistical purposes. Consider the need to determine the number of distinct people visiting a website. For famous social media (e.g., Facebook, Instagram) or e-commerce sites (e.g., Amazon, ASOS), this task could be computationally expensive because of the large number of users. Doing this with traditional methods (e.g., SQL query) on a dataset as massive as the sites mentioned above could take days and large amounts and memory. Is it not a better idea to approximately estimate the number of distinct users? HyperLogLog is an algorithm that allows us to make decent guesses when counting vast numbers of distinct elements, with very little computation or memory required.



We can download the datasets here: https://drive.google.com/file/d/19SD2db0dH2A0QLJOmBHnkbqOX6SbERcY/view

Our goal is to: 

1) Use  hash function, implement a HyperLogLog structure.
2) Read the dataset sequentially and add it to our HyperLogLog.
3) At the end we have to provid The cardinality of the dataset and The error of your filter.

2. Clustering

We play with a dataset gathering reviews (~560k) of fine foods from Amazon. The reviews include much information. We focus on the reviews' plain text and try to cluster the products (~74k).

To solve this task, we must:

1) Implement the k-means clustering algorithm (not ++: random initialization). We ask you to write the algorithm from scratch following what you learned in class.
2) Run the algorithm on the food data. Then, use the already implemented version of k-means++, are there any differences in results?
3) Analyse the obtained clusters:
Identify the kind of products in the cluster (e.g., chips, tea, coffee) using a visualization called word cloud.

Provide the number of product in each cluster

Compute the reviews' score distribution in each cluster. Once you get them, test if their mean differences are statistically significant!

Get the number of unique users writing reviews in each cluster


Before running the algorithm, we should consider the following:

How do we represent the data? (e.g., do I use a binary representation or TF-IDF?)

How do we pre-process data? Since we aim to characterize products by their review, do we want to consider words that appear in too many or too few documents?
After organizing our data, we will realize that tens of thousands of words compose your vocabulary. In this case, we s use the SVD method to reduce the dimensionality of the dataset. This operation is typically used to denoise the data and implies the loss of some information. For this reason, we first reduce our dataset to a few hundred components (e.g., 100). Then, we use the following np.cumsum(explained_variance_ratio_) to verify the total amount of variance we retain with an increasing number of components. We can pick a number of components that retain> 60% of the variance. 

3. Algorithmic question

We are given an array with A with n integer numbers.

Let s = min{ A[1], ..., A[n] } and b = max { A[1], ..., A[n] }.
Let r = b - s
We Prove that we can sort A in time O(n + r).


