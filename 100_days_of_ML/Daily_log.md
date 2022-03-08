
DAY 1
----

Refer to this notebook : [part_1_data_processing.ipynb](https://github.com/ajitjadhav10/My-Learnings/blob/main/100_days_of_ML/notebooks/part_1_data_processing.ipynb)

- We start with importing the important libraries
- Then we pre-process the data and create separate dataframes for dependent(Y) and independent variable(X)


DAY 2
---
Continuing with data processing

- I replaced all the missing values in a column with the average of the rest of the values

DAY 3
---
Continuing with data processing

- Encoding categorical values in independent and dependent variable variable

Day 4
---
Splitting the data into training data and testing data. We'can split the data into train and test dataset by using the train_test_split library from sklearn.model_selection.(refer to the notebook mentioned in 'Day 1' for the code)

Day 5
---
**Feature Scaling**

**Why do we need feature scaling?**
- It means scaling all the features of our data so that they take all the values in the same scale. This is done so that no feature dominates the other features in our model.
- It is done after splitting the data into train set and test set because, as test set is supposed to be data which is completely new for the model, if we do feature scaling before the split then, the model will have some information about the test data(this is called as data leakage), which is not what we want.

- Two main techniques of feature scaling are **Standardization** and **Normalisation**
![](Extra/Screen%20Shot%202022-03-08%20at%201.08.53%20PM.png)


- Which technique to select out of the two for feature scaling?
  - Normalisation can be used when most of the features of the dataset have a normal distribution.
  - Whereas Standardisation work in all conditions.

-Following the code snippet of scaling using standardization:

from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
X_train[:,3:]=sc.fit_transform(X_train[:,3:])*<br>*
X_test[:,3:]=sc.fit_transform(X_test[:,3:])


**Simple Linear Regression**

y=b(0)+(b1)x

y is the dependent variable
x is the independent variable

in Simple Linear regression there is only one independent variable.

- b1 is the co-efficient of independent variable(it is also known as the slope of the line).
- b0 is a constant, it is also knows as the y-intercept
![](Extra/Screen%Shot%2022-03-08%at%5.16.50%PM.png)
