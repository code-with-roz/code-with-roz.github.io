---
layout: post
title: kNN Clustering 
categories: [Clustering]
---

K-Nearest Neighbors (KNN) clustering is an unsupervised machine learning algorithm that can be used to classify data points based on their similarity to other points in the dataset. It is a simple yet effective method for grouping data into clusters, or "neighbourhoods," based on the distance between points in feature space.

If we were to think about in a simpler context, imagine you have a bunch of toy cars, and you want to group them together based on what they look like. You could group all the red cars together, all the blue cars together, and so on. We instinctively carry out clustering in our everyday lives by categories the objects around us. Knowing that a “dog” falls under the category of “animals” and can be further classified as a “canine” under the “mammal” category is an example of sophisticated clustering processes that our minds conduct in a split second that came about from the extensive learning we underwent while in school. Primary is looking for a lot more sophisticated than you thought, isn’t it? KNN clustering is a way for the computer to do this automatically, without you having to tell it which cars go in which group.

Our goal as data scientists is to program such clustering processes into machines, and after countless iterations refine the resulting clusters so that if new data is fed into this machine, it can accurately place the new data points in the right categories based on the similarity (or dissimilarity) metric programmed into the process.

The KNN algorithm works by identifying the K nearest neighbours to a given data point and assigning the point to the cluster with the most common class among those neighbours. The value of K is a hyperparameter that must be chosen by the user, and it determines the number of neighbours that will be considered when making a classification. A larger value of K will result in a smoother, more generalizable model, while a smaller value of K will result in a model that is more sensitive to local variations in the data.

Let's look at an example of arbitrary data....


![](/images/reverie-demo.png)


One of the key advantages of the KNN algorithm is its simplicity. It requires no assumptions about the distribution of the data or the number of clusters, and it is easy to implement and understand. Additionally, KNN is a non-parametric method, meaning that it does not make any assumptions about the functional form of the data, making it a flexible and robust choice for many types of data.

However, the KNN algorithm is not without its limitations. One major drawback is that it can be computationally expensive, particularly for large datasets. The algorithm must calculate the distance between each data point and all of the other points in the dataset, which can be time-consuming. Additionally, the KNN algorithm can be sensitive to the scale of the features, meaning that variables with a larger scale can dominate the distance calculation and dominate the classification.

One way to mitigate these limitations is to use a variant of the KNN algorithm known as K-Means. K-Means is a centroid-based clustering algorithm that uses a fixed number of clusters and iteratively refines the locations of the cluster centers to minimize the distance between points in the same cluster. K-Means is generally faster and more efficient than KNN, but it requires the user to specify the number of clusters in advance, which may not always be known (dereministic).

Despite its simplicity, the KNN algorithm can be a powerful tool for clustering and classification tasks. It is a straightforward and intuitive method that can be applied to a variety of datasets and problem types. While it may not always be the most efficient or accurate choice, it is an important algorithm to understand and consider in the toolkit of a machine learning practitioner.

References: 
Original Source code and data: Prof...., University of Pretoria.
Article: Myhre et. al (2018)




