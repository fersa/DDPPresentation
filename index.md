---
title       : Developing Data Products
subtitle    : Project Presentation
author      : Fernando Salazar
job         : PhD Student
framework   : io2012      # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, bootstrap, quiz]            # {mathjax, quiz, bootstrap}
mode        : selfcontained     # {standalone, draft}
knit        : slidify::knit2slides
---

## The application

- Makes use of a dataset containing $7$ inputs $X1...X7$ and one output $Y$ 
- Builds a **Random Forest (RF)** model to predict the value of the target variable $Y$ as a funcion
of the inputs
- Plots the true target values (points) together with the predictions (line)
- Plots the difference between output and prediction (Error)
- Computes the Root Mean Squared Error (RMSE) and the Maximum Absolute Error both for the
 training and the test sets    

For more details on Random Forest, see:
- A basic and intuitive intro: http://goo.gl/syNeFT
- An advanced and rigorous description, by its creator Leo Breiman: http://goo.gl/wQiDTc  

--- .class #id 

## Options and requirements

The **dataset** is already pre-processed and stored with the app, which reads it and transforms it into a **data frame**.   

The user can select the **amount of data for training** the RF model. The rest is devoted to check the prediction accuracy (**test set**). 

The user can also set the value of the parameters which control the model training process:
- **mtry** is the number of variables to try in each split
- **ntree** is the number of trees in the forest

The app requiers the library **randomForest** to build the model, and **ggplot2** to generate the plots. Both are **available on CRAN** 


--- .class #id  

## Sample plot (1/2)

```r
 trainRatio = 50 # Percentage of data for the training set
 mtry = 3
 ntree = 100
```



![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4.png) 

The vertical line highlights the division between the training set (left) and the test set (right)

--- .class #id

## Sample plot (2/2)

```r
 trainRatio = 80 # Percentage of data for the training set
 mtry = 2
 ntree = 500
```



![plot of chunk unnamed-chunk-7](assets/fig/unnamed-chunk-7.png) 

![plot of chunk unnamed-chunk-8](assets/fig/unnamed-chunk-8.png) 

Too many training samples lead to over-fitting. See the larger error for the test set

