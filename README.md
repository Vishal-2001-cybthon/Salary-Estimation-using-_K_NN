# Salary-Estimation-using-_K_NN
SalaryEstimation_K_NN

# Finding the Problem -
Application
Predicting whether this Job applicant got
Salary above 50K or Not from Previous
Company - HR

# Collecting Dataset
Based on Age, Education Number, Capital
Gain, Hours per week to estimate the
salary is above 50K or below 50K

# Load & Summarize Dataset
Load Dataset from the directory &
Summarize the details such as no. of rows
and Columns & Content
dataset = pandas.read_csv('dataset.csv')
dataset.shape
dataset.head(5)

# Mapping Data from to Text to
Binary Numbers
If the data is <=50K or >=50K, kind of text,
Here we need to Map <50K as 0 & >50K as 1

# Segregating Dataset into X & Y
iloc - It helps us select a value that
belongs to a particular row or column
X = dataset.iloc[:, :-1].values
Y = dataset.iloc[:, -1].values

# Splitting Dataset to Train & Test Useful for validation
train_test_split(X, Y, test_size = 0.25,
random_state = 0)

#Feature Scaling
Since both the features have different
scales, there is a chance that higher
weightage is given to features with higher
magnitude. This will impact the
performance of the machine learning
algorithm and obviously, we do not want
our algorithm to be biassed towards one
feature.
we scale our data to make all the features
contribute equally to the result
Types
Standardization
Here the values are centered around the
mean with a unit standard deviation. This
means that the mean of the attribute
becomes zero and the resultant
distribution has a unit standard deviation.
Normalization
Normalization is a scaling technique in
which values are shifted and rescaled so
that they end up ranging between 0 and 1.
It is also known as Min-Max scaling

# Algorithm K-Nearest Neighbor
Based on Minkowski Distance Metric we
gonna classify the data points |
p = 1 , Manhattan Distance
p = 2 , Euclidean Distance
Euclidean Distance
Euclidean distance is calculated as the
square root of the sum of the squared
differences between a new point (x) and
an existing point (y)
Manhattan Distance
This is the distance between real vectors
using the sum of their absolute difference
Hamming Distance
It is used for categorical variables. If the
value (x) and the value (y) are the same,
the distance D will be equal to 0 .
Otherwise D=1

# Finding the Best K-Value -
number of neighbors
Choose the K Value where we are getting
least mean error
From this figure, we can observe that K
Value range from 15 to 35, our mean error
is low

#Training
Training our Model for Pre-processed
Dataset model.fit(X_train, y_train)

# Validation Obtaining the accuracy of the Model Confusion Matrix

# Prediction
Observing how our model is classifying
our new data
result = model.predict(sc.transform(
newEmp))

