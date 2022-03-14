#### Documenting my ML learnings -inspired by Avik Jain


DAY 1
----

**Refer to this notebook** : [part_1_data_processing.ipynb](https://github.com/ajitjadhav10/My-Learnings/blob/main/100_days_of_ML/notebooks/part_1_data_processing.ipynb)

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

**Refer this notebook**: [part_2_simple_linear_regression.ipynb](https://github.com/ajitjadhav10/My-Learnings/blob/main/100_days_of_ML/notebooks/part_2_simple_linear_regression.ipynb)

y=b(0)+(b1)x

y is the dependent variable
x is the independent variable

In Simple Linear Regression, we try to predict the value of the dependent variable based on the value of the independent variable. x and y are assumed to be linearly related.

in Simple Linear regression there is only one independent variable.

- b1 is the co-efficient of independent variable(it is also known as the slope of the line).
- b0 is a constant, it is also knows as the y-intercept
![Simple Linear Regression](https://github.com/ajitjadhav10/My-Learnings/blob/8e3ac261ea1812c40d9da284e92de0d121e3bf44/100_days_of_ML/Extra/Screen%20Shot%202022-03-08%20at%205.16.50%20PM.png)


1. Linear Regression with one variable/Univariate linear regression
y=(b0)+(b1)x 

Day 6
---
**Cost function:**
b0 and b1(also denoted by theta(0) or theta(1) in some books or videos) are known as the parameters.


How to choose the values for b0 and b1?
Idea: Choose b(0) and b(1) such that h(x) (y and h(x) denote the same thing here, i.e the predicted variable) is close to y for our training examples(x,y)

So what a linear regression model does is that it creates many trend lines and calculates the **(sum of the squares of the errors)** (also called as Squared error)for each line. So we need to find the trend line which is closest to the given data (i.e the line which has the smallest error). 

And the squared error function is also known as the **Cost function**.

The line which has the minimum value for **Cost function**/MSE is the best fit line.

Have a look at the simple regression model through the link given above.


Day 7
---
Here, I'll be starting with **Multiple linear regression**

![](https://github.com/ajitjadhav10/My-Learnings/blob/21a6121ec2dda50f15e34c8fcfcdaf607b4c5117/100_days_of_ML/Extra/Screen%20Shot%202022-03-11%20at%209.22.06%20PM.png)

In Multiple Linear Regression there are multiple independent variables and one dependent variable as shown in the equation above.

Following are the following 5 assumptions of Linear Regression:
1. Linearity
2. Homoscedasticity
3. Multivariate normality
4. Independence of errors
5. Lack of multicollinearity

Day 8
---

Dummy Variables

- Understanding p-values
- Cost function for Linear regression(The goal is to minimize the cost function)

Day 9
---
- Learning about Gradient Descent
