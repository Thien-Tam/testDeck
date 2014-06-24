---
title       : MPG Prediction
subtitle    : Dumb linear model mpg ~ cyl + wt (just for creating a funny Shiny App !)
author      : A random Coursera Student
job         : Lifelong Learner
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Available Data

The mtcars dataset is one among the datasets packages. It is the one used in the Regression Models Project and thus I decided to continue to use it in the Developing Data Products project.
<p>
Basically, we just use the three following features form the mtcars dataset to help us predict MPG according to our dumb lieanr regression model:
* wt: weight of the car in thousands of pounds 
* cyl: number of cylinders in the car's engine
* mpg: gas mileage in miles per gallon

--- .class #id 

## The Model

I have created a very simple linear regression model based on the number of cylinders and weight of cars to predict the respective MPG:

```r
model <- lm(mpg ~ wt + cyl, data = mtcars)
model
```

```
## 
## Call:
## lm(formula = mpg ~ wt + cyl, data = mtcars)
## 
## Coefficients:
## (Intercept)           wt          cyl  
##       39.69        -3.19        -1.51
```


--- .class #id 

## Results


```r
model.summary <- summary(model)
model.summary[4]
```

```
## $coefficients
##             Estimate Std. Error t value  Pr(>|t|)
## (Intercept)   39.686     1.7150  23.141 3.043e-20
## wt            -3.191     0.7569  -4.216 2.220e-04
## cyl           -1.508     0.4147  -3.636 1.064e-03
```

```r
model.summary[8]
```

```
## $r.squared
## [1] 0.8302
```


My model is just a dumb one and pretty much false... but it's it is just designed to be a funny demonstration of some Shiny Application features.

--- .class #id

## Testing on shinyapps.io

Here's a link to the interactive web version of this Shiny App:   
http://thien-tam.shinyapps.io/project

The user may choose the number of cylinders and weight of his dream car to get a prediction of the corresponding MPG.

NB: It seems I just cannot deploy on shinyapps.io... You can still copy both server.R and ui.R and run the app on your own computer to see it work. Enjoy ! ;-)
