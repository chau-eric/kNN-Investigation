<h1>Investigation of Classification Methods for Fashion-MNIST (kNN)</h1>

<h2>Description</h2>
The goal of this report was to demonstrate that we could apply the machine learning techniques that we learned about by implementing and analyzing various machine learning algorithms applied to a particular dataset. The selected classifiers include the kNN, Logistic Regression, Feed-Forward Neural Network, and Decision Tree models.<br />
<b>note:</b> This was a group project done by 3 people, including myself. This repository only showcases the work that I contributed to, which is mainly the kNN classifier.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 
  - NumPy
  - Matplotlib
  - scikit-learn
- <b>[Fashion-MNIST dataset](https://github.com/zalandoresearch/fashion-mnist)</b> 

<h2>Environments Used </h2>

- <b>Jupyter Notebook</b>

<h2>kNN (k Nearest Neighbors)</h2>
The kNN classifier makes predictions based on the majority of the labels of the k nearest neighbors of that datapoint. Hyperparameters include k and p. k ranges from 1 to the size of the training set. p can be any positive real number, and it determines the distance formula used to calculate the nearest neighbors. We used scikit-learn’s KNeighborsClassifier.

<h2>Experimental Setup</h2>
The Fashion-MNIST dataset comes with a provided testing set of 10,000 data points and a training set of 60,000 data points. For each of the classifiers, the provided testing set will be used to test our final models, and the provided training data will be split 75% - 25% to create a validation set.<br />
For the kNN classifier, the main metric considered was classification error, and the main hyperparameter focused on was k. All kNN models for this experiment will utilize the default Euclidean distance formula. First, I did a comparison of both training and validation error using k = 1, 2, 5, 10, 50, 100, and 110. Once I reasonably concluded that smaller values of k seemed more optimal for both datasets, I tested again with k values 1-10 before selecting the value of k that resulted in the lowest error for the validation set. The training and predicting of the final model was timed as well.

<h2>Experimental Results</h2>
First I looked at training and validation error with values k = [1, 2, 5, 10, 50, 100, 110]. Based on its graph, it seemed that increasing k to be anything over 10 results in worse accuracy, with k = 5 providing the lowest error for the validation set. Therefore, I narrowed our search to values between 1 and 10.<br/>
<p align="center">
<img width="626" alt="Untitled" src="https://github.com/chau-eric/kNN-Investigation/assets/76719902/9fd2271f-91f6-47f3-8544-bc98bfe8b6f0">
</p>
With smaller values of k, we can see that k = 4, 6 produce the lowest errors for the validation set, however k = 4 also has a lower training error than k = 6. Therefore, I selected k = 4 to use on my final model, which resulted in an accuracy of 0.8473 on the testing set. This result took about 9000 ms to train and predict on a testing set size of 10,000 datapoints, making it the fastest model when compared with the other three. In general however, the neural network ends up performing the best in terms of both training and testing accuracy.
