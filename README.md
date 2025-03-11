**Advertising Multiple Linear Regression Project:**

I created this project to familiarize myself with multiple linear regression in terms of machine learning. I am working my way through Andrew Ng's machine learning specialization on Coursera and 
wanted to try to make my own project.

**Data set:**
  The data set consists of 4 rows: TV advertising money, Radio advertising money, Newspaper advertising money, and Total Sales. I made the first three rows (TV,Radio,Newspaper) the features in my multiple
  linear regression and Total Sales my target variable. 

**Reading/Storing data:**
  In this project I had to read in the advertising.csv which I did using the pandas library read_csv() function however I need to be in the right working directory. I imported the os library
  and called the chdir() function in order to get to the right directory with my advertising.csv file. I stored the first three rows of the data in the x dataset and the last row (sales) in the y dataset. I 
  realized after running the gradient descent that I would have to normalize my dataset.

**Normalize data:**
  I normalized the data by getting the mean and standard deviation and computing (x-mean)/std which made the range of numbers much easier to work with and increased the efficiency of the gradient descent.

**Initialize data:**
  I intialized the initial parameters for the gradient descent which in retrospect I will do after I create the gradient descent. I created a vector of zeros for w and set b to 0. Alpha was set at 0.01 and number
  of iterations at 1000.


