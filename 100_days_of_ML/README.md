#### Documenting my ML learnings -inspired by Avik Jain


DAY 1
----

**Refer to this notebook** : [part_1_data_processing.ipynb](https://github.com/ajitjadhav10/My-Learnings/blob/main/100_days_of_ML/notebooks/part_1_data_processing.ipynb)

- We start with importing the important libraries
- Then we pre-process the data and create separate dataframes for dependent(Y) and independent variable(X)


Key concepts:
- The inability of the machine learning method to capture the true relationship is called **bias**
- Bias is the measurement of how accurately a model can fit the training dataset. If the error is large, then we say that it has high bias
- The difference in fits between (test)datasets is called **variance**. Refer the image below, LHS represents how the sqiggly line fits the training set and the RHS represents how the line fits the testing set, this difference in the fitting is called Variance.
- ![](https://github.com/ajitjadhav10/My-Learnings/blob/3e854aa0c7f7b550a7d7464799c97a6fd69201d0/100_days_of_ML/Extra/Screen%20Shot%202022-04-07%20at%204.10.47%20PM.png)
- So the squiggly line shown above has **low bias**(as it is flexible and is able to adapt to the curves in the realtionship between height and weight
- But it has high **variance** because it has vast difference in sums of squares for different datasets.
- Hence, we cannot accurately tell if the squiggly line will perform well with every dataset,
- In the below image we can see that a straight line has high bias and low variance.

- Hence, the strainght line might only provide us with good predictions, and not great predictions. But they will be consistently good.
- Also, as the sqiggly line fits the training dataset really well and not the testing dataset, we say that the squiggly line is overfit.

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

Dummy Variables: These are variables which we bring in, in place of categorical variables because categorical variables cannot be be included in mathematical equations.

- Understanding p-values
- Cost function for Linear regression(The goal is to minimize the cost function)

Day 9
---
- Learning about Gradient Descent

Day 10
---
Continuing with Multiple Linear Regression

Day 11
---
- What are p values and what is statistical significance?

Let's take an example of a coin toss and we have two hypothesis for this:
1. H(0)-It is a fair coin(null hypothesis)
2. H(1)-It is not a fair coin


 - *So we start off by assuming that the null hypothesis is true.* Then we toss the coin 6 times one after the other and each time we get tails, but after the 4th toss, the probability of getting a tails goes below 5%(as it is 3% or 0.03 for the 5th try) which is extremely unlikely.

Following are the probability of getting a Tail, if we toss the coin 6 times one after the other;<br>
 - 1st T-0.5
 - 2nd T-0.25
 - 3rd T-0.12
 - 4th T-0.06
 ----------
 - 5th T-0.03
 - 6th T-0.01


 - Hence if the probability of something happening is 5% or less (i.e alpha=0.05) then it is highly unlikely to happen from a random sample, we reject the null hypothesis H(0). So we can say that we have **95%** confidence that this situation where we have 6 consecuetive tails will become true. We can set the confidence level to anything according to the requirement of our experiment. In medical field in some cases we need the confidence interval to be 99%.

Now, I'll be looking at a step-by-step guide at building a model:
1. All in
2. Backward Elimination
3. Forward Selection
4. Bidirectional Elimination
5. Score Comparison


In 'All in' we use all the predictors from the dataset, following are the cases where you have to use this method:
- when you are asked to use all the predictors by a client
- when you have no other option and are required to use all of them
- when you are preparing for backward elimination

Backward elimination:
- First, Select a significance level to stay in the model(eg. SL=0.05)
- Second, Fit the model with all the predictors(as mentioned earlier that we need to use all the predictors while preparing for backward elimination)
- Third, select the predictors with the **highest**, i.e p-value>SL
- Fourth, remove the predictor which you had selected in setp 3
- Fifth, fit the model with the rest of the predictors.

If in step 3, there are no variables with p-value>SL you directly go to fitting your model(i.e your model is prepared)



Forward selection:
- First, Select a significance level to stay in the model(eg. SL=0.05)
- Second, create a Simple Regression model with all independent variables and then select the one with the lowest p-value
- Third, with the variable selected in step 2 add one variable and fit it in all possible models, after this add another variable to the step 2 variable fit it in all possible models. Do this for all variables.
- Fourth, we select the predictor with the lowest p-value(i.e the one with two variables which gave us the lowest p-value in the previous step), if this pvalue<SL,then go step 3 again and now add a third variable to it and follow the same steps. We keep doing this, till the time p-value < SL condition is not true.
- So we select the model just before the one where the codition was not satisfied.

Bidirectional Elimination:
- Select a SL to enter and stay in the model eg: SLENTER=0.05, SLSTAY=0.05
- Perform the steps of Forward Selection(here p-value<SLENTER to enter)
- Now, perform the steps of Backward Elimination(old variables must have p-value<SLSTAY to stay) 
- When we reach a point where no new variables can enter or old variables can exit then or model is ready

![](https://github.com/ajitjadhav10/My-Learnings/blob/f215840bf56eaa22338971fa3645d4eb27e67857/100_days_of_ML/Extra/Screen%20Shot%202022-03-15%20at%202.01.04%20PM.png)


Day 12
---
Building a Multiple Regression model, refer the python notebook here:

Day 13
---
- Continuing with Multiple Regression model which I started yesterday
- Practicing Linear Regression on iris dataset

Day 14
---
- Polynomial Regression, refer the python notebook here:


Day 15
---
- Continuing with Polynomial Regression

Day 16
---
- ![](https://github.com/ajitjadhav10/My-Learnings/blob/ff17fb0dfba939c983d06905656534c6477c9fa9/100_days_of_ML/Extra/Screen%20Shot%202022-03-26%20at%2012.18.32%20PM.png)
- Polynomial Regression is needed when we have non linear data as Linear regression will not be able to give us a best-fit line.
- It is extremely important to select the optimum value for the degree of the polynomial.
- If the degree of polynomial is too high, then the model will overfit the data and incase the degree is too small, it'll underfit the data.

Day 17
---
Continuing with Polynomial Regression

Day 18
---
 Support Vector Regression
 - Vladimir Vapnik
![](https://github.com/ajitjadhav10/My-Learnings/blob/236f5a617cb560b5100a0f5906b4d0262ba467f2/100_days_of_ML/Extra/Screen%20Shot%202022-03-31%20at%202.34.07%20PM.png)


Day 19
---
Decision Tree

- It consists of CART i.e Classification Trees and Regression Trees
- Focusing on Regression Trees right now
- Refer this video to leaarn more about Decision Trees: https://www.youtube.com/watch?v=sLXtCwxg5kI

Day 20
---
- implementing a Decision Tree Regression Model, refer this notebook: [Decision Tree Regression Notebook](https://colab.research.google.com/drive/1IGHq_aUAQ8jXt_E3Xf_nN0XBSmT18ANK#scrollTo=IbO5FW7T8siW)

Day 21
---
-Continuing with Decision Tree algorithm
- Refer this video for understanding Decision trees: [Decision Trees, Clearly Explained] (https://www.youtube.com/watch?v=g9c66TUylZ4)

Day 22
---
- Random Forest Regression
- Random Forest Regression is a form of Ensemble Learning
- When we use multiple algorithms together, or one algorithm multiple times, it is called ensemble learning.

- Step 1: pick random k data points from the training dataset
- Step 2: Build a decision tree based on these data points
- Choose the number of Ntrees, and then repeat step 1 and 2
- For a new data point, make each of the Ntrees predict the value of Y for the data point, and assign the new data point the average across all of the predicted Y values


 
                                                                            
                                                                            
                                                                            
