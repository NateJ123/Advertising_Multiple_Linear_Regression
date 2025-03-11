**Advertising Multiple Linear Regression Project:**

I created this project to familiarize myself with multiple linear regression in terms of machine learning. I am working my way through Andrew Ng's machine learning specialization on Coursera and 
wanted to try to make my own project.

**Data set:**
  The data set consists of 4 rows: TV advertising money, Radio advertising money, Newspaper advertising money, and Total Sales. I made the first three rows (TV,Radio,Newspaper) the features in my multiple
  linear regression and Total Sales my target variable. 

**Variables**
  x = matrix of rows and columns that makes up the training dataset
  y = row vector for our target variable sales for training dataset
  x_test = the last 50 rows of the dataset (also matrix) for testing purposes
  y_test = the last 50 rows of the dataset (row vector) for testing purposes
  w = row vector for the weights of our features
  b = scalar for bias 
  alpha = our learning rate for how big of steps our model takes
  num_iters = number of iterations for our model
  

**Reading/Storing data:**
  In this project I had to read in the advertising.csv which I did using the pandas library read_csv() function however I need to be in the right working directory. I imported the os library
  and called the chdir() function in order to get to the right directory with my advertising.csv file. I stored the first three rows of the data in the x dataset and the last row (sales) in the y dataset. I also broke up my data into both training and testing. The dataset had 199 rows so I made the training dataset 149 rows and the testing dataset was the last 50 rows. I realized after running the gradient descent that I would have to normalize my dataset.

**Normalize data:**
  I normalized the data by getting the mean and standard deviation and computing (x-mean)/std which made the range of numbers much easier to work with and increased the efficiency of the gradient descent.

**Initialize data:**
  I intialized the initial parameters for the gradient descent which in retrospect I will do after I create the gradient descent. I created a vector of zeros for w and set b to 0. Alpha was set at 0.01 and number
  of iterations at 1000.
  
**Compute Cost**
  I created a function to compute the cost that takes in the parameters w,x,y,and b with w being a row vector, x being a matrix, b being a scalar, and y being a row vector. It iterates over the length of the dataset and sums up the squared error and then divides by 2m (m being the length of the dataset). This function returns the total cost (the value of the cost function at a certaion point of gradient descent).

**Calculated partial derivatives**
  I created a function to calculate the partial derivatives in respect to w and b. This function has two for loops because you need to iterate through both the rows and the columns. I realized after 
  implementing it this way that you could use the sum function to speed up the time via vectorization which I will attempt in my next project. Once again it takes in the parameters w,x,y,b. This function returns w_der and b_der which are the derivatives of w and b respectively.

**Gradient Descent**
  I made the gradient descent function which takes in the parameters x,y,w,b,number of iterations, alpha, the cost function I made, and the partial derivatives function I made. It iterates over the number of iterations specified when calling the model. I call the gradients function to get the derivatives of w and b which I use to update w and b by subtracting the derivative multiplied by alpha from the original w or b. I also have a list called J_history that is getting appended with the cost function every iteration for graphing purposes later. This function returns w_F (final w), b_F (final b), and J_history (cost function history). I also have an if statement that will print the iteration number and cost function value at that iteration for every 10% of the number of iterations.

**Calling Gradient Descent and Graphing**
  I called gradient descent with the variables I initialized and saw that after 900 iterations the cost function came down to 1.39. The interesting thing is after only 400 the cost function was at 1.39 which means it has hit a local minima (possibly the global minimum) by 400 iterations with our specified learning rate (0.01). I graphed the cost function on the y-axis and the number of iterations on the x-axis to show how the cost function decreases over iterations. This was very useful because it helped me see if my gradient descent was working or not visually. I then ran a for loop over the number of rows in the test dataset to show the actual data value versus the prediction of the data value (the model was not trained with these 50 rows). I then graphed two lines, one being the predictions I made for the test data and the other being the actual values of y in the test data. The graph shows that the model predicts the total sales very well and that my model worked. 

**Conclusion**
  Overall the multiple linear regression was pretty successful with the cost function getting down to 1.39 and the predictions were pretty close. However, there are definitely efficiency upgrades I can make to my code. I am going to continue to run regressions on different datasets which is where I will be fixing my past errors and I am very happy with my model. My model was able to pretty accurately predict new total sales off of data it had not seen before. 


