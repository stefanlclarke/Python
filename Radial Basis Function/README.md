This is a radial basis function for classifying data into 2 groups. In the notebook, 2-D data on the unit square is generated and classified in 2 different ways. I then run my radial basis fucntion on them and display the results.

A radial basis function first uses K-means clustering to separate the datapoints into K clusters, such that distances between points in each cluster are mnimized. K is specified by the user. It centres a gaussian at the mean of each cluster, and your hypothesis function is h(x) = sign(symsum(W[i] * exp( - gamma* norm(x - mu[i])^2 , from i==1 to k). Here, mu[i] is the mean of cluster i and W[i], gamma are weights learned by a learning algorithm.

The algorithm switches between adjusting for W and adjusting for gamma each iteration. The best gamma is found by in sample gradient descent, and the best W is found by (pseudo) - solving a set of K linear equations in W[i] and Y[i], which you will hopefully spot in the code.

This is the video I used to teach myself about this subject, and I would recommend it to anyone else curious. https://www.youtube.com/watch?v=O8CfrnOPtLc

Thanks for reading! :)
