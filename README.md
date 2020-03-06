# Data_Science_Visualization
# HarvardX: PH125.2x | Data Science: Visualization

## Abstract

This is the second in a series of courses in a Professional Certificate in Data Science program. The courses in the Professional Certificate program are designed to prepare you to do data analysis in R, from simple computations to machine learning. If you need a refresher of some basic R, check out Data Science: R Basics, the first course in this series.

The textbook for the Data Science course series is [freely available online](https://rafalab.github.io/dsbook/).

## Learning Objectives
- Data visualization principles to better communicate data-driven findings
- How to use ggplot2 to create custom plots
- The weaknesses of several widely used plots and why you should avoid them

## Course Overview

### Section 1: Introduction to Data Visualization and Distributions
You will get started with data visualization and distributions in R.

### Section 2: Introduction to ggplot2
You will learn how to use ggplot2 to create plots.

### Section 3: Summarizing with dplyr
You will learn how to summarize data using dplyr.

### Section 4: Gapminder
You will see examples of ggplot2 and dplyr in action with the Gapminder dataset.

### Section 5: Data Visualization Principles
You will learn general principles to guide you in developing effective data visualizations.

## Section 1 Overview

Section 1 introduces you to Data Visualization and Distributions.

After completing Section 1, you will:
- understand the importance of data visualization for communicating data-driven findings.
- be able to use distributions to summarize data.
- be able to use the average and the standard deviation to understand the normal distribution.
- be able to assess how well a normal distribution fits the data using a quantile-quantile plot.
- be able to interpret data from a boxplot.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/introduction-to-data-visualization.html)

## Assessment 1 (Data Types)

1. Variable names

Let’s start by reviewing how to extract the variable names from a dataset using the names function. What are the two variable names used in the heights dataset?
```
library(dslabs)
data(heights)
names(heights)
```
```
## [1] "sex"    "height"
```
2. Variable type

We saw that sex is the first variable. We know what values are represented by this variable and can confirm this by looking at the first few entires:
```
library(dslabs)
data(heights)
head(heights)
```
```
	sex     height
	<fctr>  <dbl>
1	Male	75
2	Male	70
3	Male	68
4	Male	74
5	Male	61
6	Female	65
6 rows
```
What data type is the sex variable?

- [ ] A. Continuous
- [X] B. Categorical
- [ ] C. Ordinal
- [ ] D. None of the above

3. Numerical values

Use the unique and length functions to determine how many unique heights were reported.
```
library(dslabs)
data(heights)
```
```
x <- heights$height
length(unique(x))
```
```
## [1] 139
```
4. Tables

Use the table function to compute the frequencies of each unique height value. Because we are using the resulting frequency table in a later exercise we want you to save the results into an object and call it tab.
```
library(dslabs)
data(heights)
```
```
x <- heights$height
tab <- table(x)
```
5. Indicator variables

In the previous exercise we computed the variable tab which reports the number of times each unique value appears. For values reported only once tab will be 1. Use logicals and the function sum to count the number of times this happens.
```
library(dslabs)
data(heights)
```
```
tab <- table(heights$height)
sum(tab==1)
```
```
## [1] 63
```
6. Data types - heights

Since there are a finite number of reported heights and technically the height can be considered ordinal, which of the following is true:

- [X] A. It is more effective to consider heights to be numerical given the number of unique values we observe and the fact that if we keep collecting data even more will be observed.
- [ ] B. It is actually preferable to consider heights ordinal since on a computer there are only a finite number of possibilities.
- [ ] C. This is actually a categorical variable: tall, medium or short.
- [ ] D. This is a numerical variable because numbers are used to represent it.

## Assessment 2 (Distribution)

1. Distributions - 1
    
In the murders dataset, the region is a categorical variable and the following is its distribution:

![Unknown](https://user-images.githubusercontent.com/17474099/75705803-6b2deb80-5cbc-11ea-86d8-5e3a187694e2.png)

To the closet 5%, what proportion of the states are in the North Central region?

- [ ] A. 75%
- [ ] B. 50%
- [X] C. 20%
- [ ] D. 5%

2. Distributions - 2

Which of the following is true:

- [ ] A. The graph above is a histogram.
- [X] B. The graph above shows only four numbers with a bar plot.
- [ ] C. Categories are not numbers, so it does not make sense to graph the distribution.
- [ ] D. The colors, not the height of the bars, describe the distribution.

3. The plot below shows the eCDF for male heights:

![Unknown](https://user-images.githubusercontent.com/17474099/75706117-f6a77c80-5cbc-11ea-8689-ceb860f0f133.png)

Based on the plot, what percentage of males are shorter than 75 inches?

- [ ] A. 100%
- [X] B. 95%
- [ ] C. 80%
- [ ] D. 72 inches

4. To the closest inch, what height m has the property that 1/2 of the male students are taller than m and 1/2 are shorter?

- [ ] A. 61 inches
- [ ] B. 64 inches
- [X] C. 69 inches
- [ ] D. 74 inches

5. Here is an eCDF of the murder rates across states:

![Unknown](https://user-images.githubusercontent.com/17474099/75706458-80574a00-5cbd-11ea-806e-30358d1613ae.png)

Knowing that there are 51 states (counting DC) and based on this plot, how many states have murder rates larger than 10 per 100,000 people?

- [X] A. 1
- [ ] B. 5
- [ ] C. 10
- [ ] D. 50

6. Based on the eCDF above, which of the following statements are true:

- [ ] A. About half the states have murder rates above 7 per 100,000 and the other half below.
- [ ] B. Most states have murder rates below 2 per 100,000.
- [ ] C. All the states have murder rates above 2 per 100,000.
- [X] D. With the exception of 4 states, the murder rates are below 5 per 100,000.

7. Below is a histogram of male heights in our heights dataset:

![Unknown](https://user-images.githubusercontent.com/17474099/75706795-168b7000-5cbe-11ea-97af-639fa5d34b47.png)

Based on this plot, how many males are between 62.5 and 65.5?

- [ ] A. 5
- [ ] B. 24
- [X] C. 44
- [ ] D. 100

8. About what percentage are shorter than 60 inches?

- [X] A. 1%
- [ ] B. 10%
- [ ] C. 25%
- [ ] D. 50%

9. Based on the density plot below, about what proportion of US states have populations larger than 10 million?

![index](https://user-images.githubusercontent.com/17474099/75769618-c86e7f00-5d46-11ea-9b94-9ae8d2330565.png)

- [ ] A. 0.02
- [X] B. 0.15
- [ ] C. 0.50
- [ ] D. 0.55

10. Below are three density plots. Is it possible that they are from the same dataset?

![index](https://user-images.githubusercontent.com/17474099/75769820-171c1900-5d47-11ea-9a2f-660e714bb1f5.png)

Which of the following statements is true:
- [ ] A. It is impossible that they are from the same dataset.
- [ ] B. They are from the same dataset, but the plots are different due to code errors.
- [ ] C. They are the same dataset, but the first and second plot undersmooth and the third oversmooths.
- [X] D. They are the same dataset, but the first is not in the log scale, the second undersmooths and the third oversmooths.

## Assessment 3 (Normal Distribution)

1. Proportions

Histograms and density plots provide excellent summaries of a distribution. But can we summarize even further? We often see the average and standard deviation used as summary statistics: a two number summary! To understand what these summaries are and why they are so widely used, we need to understand the normal distribution.

The normal distribution, also known as the bell curve and as the Gaussian distribution, is one of the most famous mathematical concepts in history. A reason for this is that approximately normal distributions occur in many situations. Examples include gambling winnings, heights, weights, blood pressure, standardized test scores, and experimental measurement errors. Often data visualization is needed to confirm that our data follows a normal distribution.

Here we focus on how the normal distribution helps us summarize data and can be useful in practice.

One way the normal distribution is useful is that it can be used to approximate the distribution of a list of numbers without having access to the entire list. We will demonstrate this with the heights dataset.

Load the height data set and create a vector x with just the male heights:
```
library(dslabs)  
data(heights)  
```
```
x <- heights$height[heights$sex == "Male"]  
```
What proportion of the data is between 69 and 72 inches (taller than 69 but shorter or equal to 72)?
```
library(dslabs)
data(heights)
```
```
x <- heights$height[heights$sex == "Male"]
mean(x>69 & x<=72)
```
```
## [1] 0.3337438
```
2. Averages and Standard Deviations

Suppose all you know about the height data from the previous exercise is the average and the standard deviation and that its distribution is approximated by the normal distribution. We can compute the average and standard deviation like this:
```
library(dslabs)  
data(heights)  
```
```
x <- heights$height[heights$sex=="Male"]  
avg <- mean(x)  
stdev <- sd(x)  
```
Suppose you only have avg and stdev below, but no access to x, can you approximate the proportion of the data that is between 69 and 72 inches?

Use the normal approximation to estimate the proportion the proportion of the data that is between 69 and 72 inches.
Note that you can’t use x in your code, only avg and stdev. Also note that R has a function that may prove very helpful here - check out the pnorm function (and remember that you can get help by using ?pnorm)
```
library(dslabs)
data(heights)
```
```
x <- heights$height[heights$sex=="Male"]
avg <- mean(x)
stdev <- sd(x)
pnorm(72, avg, stdev) - pnorm(69, avg, stdev)
```
```
## [1] 0.3061779
```
3. Approximations

Notice that the approximation calculated in the second question is very close to the exact calculation in the first question. The normal distribution was a useful approximation for this case.

However, the approximation is not always useful. An example is for the more extreme values, often called the “tails” of the distribution. Let’s look at an example. We can compute the proportion of heights between 79 and 81.
```
library(dslabs)  
data(heights)  
```
```
x <- heights$height[heights$sex == "Male"]  
mean(x > 79 & x <= 81)  
```
```
## [1] 0.004926108
```
Use normal approximation to estimate the proportion of heights between 79 and 81 inches and save it in an object called approx.
Report how many times bigger the actual proportion is compared to the approximation.
```
library(dslabs)
data(heights)
```
```
x <- heights$height[heights$sex == "Male"]
exact <- mean(x > 79 & x <= 81)
avg <- mean(x)
stdev <- sd(x)
approx <- pnorm(81, avg, stdev) - pnorm(79, avg, stdev)
exact/approx
```
```
## [1] 1.614261
```
4. Seven footers and the NBA

Someone asks you what percent of seven footers are in the National Basketball Association (NBA). Can you provide an estimate? Let’s try using the normal approximation to answer this question.

First, we will estimate the proportion of adult men that are 7 feet tall or taller.

Assume that the distribution of adult men in the world as normally distributed with an average of 69 inches and a standard deviation of 3 inches.
Using this approximation, estimate the proportion of adult men that are 7 feet tall or taller, referred to as seven footers. Print out your estimate; don’t store it in an object.
```
1 - pnorm(7*12, 69, 3)
```
```
## [1] 2.866516e-07
```
5. Estimating the number seven footers

Now we have an approximation for the proportion, call it p, of men that are 7 feet tall or taller.

We know that there are about 1 billion men between the ages of 18 and 40 in the world, the age range for the NBA.

Can we use the normal distribution to estimate how many of these 1 billion men are at least seven feet tall? Use your answer to the previous exercise to estimate the proportion of men that are seven feet tall or taller in the world and store that value as p.
Then round the number of 18-40 year old men who are seven feet tall or taller to the nearest integer. (Do not store this value in an object.)
```
p <- 1 - pnorm(7*12, 68, 3)

round(p * 1*10^9)
```
```
## [1] 48
```
6. How many seven footers are in the NBA?

There are about 10 National Basketball Association (NBA) players that are 7 feet tall or higher.

Use your answer to exercise 4 to estimate the proportion of men that are seven feet tall or taller in the world and store that value as p. 

Use your answer to the previous exercise (exercise 5) to round the number of 18-40 year old men who are seven feet tall or taller to the nearest integer and store that value as N.

Then calculate the proportion of the world’s 18 to 40 year old seven footers that are in the NBA. (Do not store this value in an object.)
```
p <- 1-pnorm(7*12,69,3)
N <- round(p*10^9)
10/N
```
```
## [1] 0.03484321
```
7. Lebron James’ height

In the previous exerceise we estimated the proportion of seven footers in the NBA using this simple code:
```
p <- 1 - pnorm(7*12, 69, 3)  
N <- round(p * 10^9)  
10/N  
```
```
## [1] 0.03484321
```
Repeat the calculations performed in the previous question for Lebron James’ height: 6 feet 8 inches. There are about 150 players, instead of 10, that are at least that tall in the NBA.

Report the estimated proportion of people at least Lebron’s height that are in the NBA.
```
## Change the solution to previous answer
p <- 1 - pnorm(6*12+8, 69, 3)
N <- round(p * 10^9)
150/N
```
```
## [1] 0.001220842
```
8. Interpretation 

In answering the previous questions, we found that it is not at all rare for a seven footer to become an NBA player.

What would be a fair critique of our calculations?
- [ ] A. Practice and talent are what make a great basketball player, not height.
- [ ] B. The normal approximation is not appropriate for heights.
- [X] C. As seen in exercise 3, the normal approximation tends to underestimate the extreme values.  It's possible that there are more seven footers than we predicted.
- [ ] D. As seen in exercise 3, the normal approximation tends to overestimate the extreme values. It’s possible that there are less seven footers than we predicted.

## Assessment 4 (Quantiles, percentiles, and boxplots)

1. Vector lengths

When analyzing data it’s often important to know the number of measurements you have for each category. Define a variable male that contains the male heights. Define a variable female that contains the female heights. Report the length of each variable.
```
library(dslabs)
data(heights)
```
```
male <- heights$height[heights$sex=="Male"]
female <- heights$height[heights$sex=="Female"]

length(male)
```
```
## [1] 812
```
```
length(female)
```
```
## [1] 238
```
2. Percentiles

Suppose we can’t make a plot and want to compare the distributions side by side. We can’t just list all the numbers. Instead, we will look at the percentiles. Create a five row table showing female_percentiles and male_percentiles with the 10th, 30th, 50th, ., 90th percentiles for each sex. Then create a data frame with these two as columns.
```
library(dslabs)
data(heights)
```
```
male <- heights$height[heights$sex=="Male"]
female <- heights$height[heights$sex=="Female"]

male_percentiles <- quantile(male, seq(0.1, 0.9,0.2))
female_percentiles <- quantile(female, seq(0.1, 0.9,0.2))

df <- data.frame(female = female_percentiles, male = male_percentiles)
df
```
```
        female          male
        <dbl>           <dbl>
10%	61.00000	65.00000
30%	63.00000	68.00000
50%	64.98031	69.00000
70%	66.46417	71.00000
90%	69.00000	73.22751
5 rows
```
3. Interpretating Boxplots - 1

Study the boxplots summarizing the distributions of populations sizes by country.

Which continent has the country with the largest population size?

![index](https://user-images.githubusercontent.com/17474099/75773033-5baab300-5d4d-11ea-878e-c54b7a7f94f4.png)

- [ ] A. Africa
- [ ] B. Americas
- [X] C. Asia
- [ ] D. Europe
- [ ] E. Oceania

4. Interpretating Boxplots - 2

Study the boxplots summarizing the distributions of populations sizes by country.

Which continent has median country with the largest population?

![index](https://user-images.githubusercontent.com/17474099/75773208-b93eff80-5d4d-11ea-8b56-35f618df0b83.png)

- [X] A. Africa
- [ ] B. Americas
- [ ] C. Asia
- [ ] D. Europe
- [ ] E. Oceania

5. Interpretating Boxplots - 3

Again, look at the boxplots summarizing the distributions of populations sizes by country. To the nearest million, what is the median population size for Africa?

![index](https://user-images.githubusercontent.com/17474099/75773370-0f13a780-5d4e-11ea-8efd-9f2ba5e0c595.png)

- [ ] A. 100 million
- [ ] B. 25 million
- [X] C. 10 million
- [ ] D. 5 million
- [ ] E. 1 million

6. Low quantiles

Examine the following boxplots and report approximately what proportion of countries in Europe have populations below 14 million:

![index](https://user-images.githubusercontent.com/17474099/75774043-649c8400-5d4f-11ea-917d-bdb8c62e79d9.png)

- [X] A. 0.75
- [ ] B. 0.50
- [ ] C. 0.25
- [ ] D. 0.01

7. Interquantile Range (IQR)
    
Based on the boxplot, if we use a log transformation, which continent shown below has the largest interquartile range?

![index](https://user-images.githubusercontent.com/17474099/75774893-391a9900-5d51-11ea-938b-daaf1b49415f.png)

- [ ] A. Africa
- [X] B. Americas
- [ ] C. Asia
- [ ] D. Europe
- [ ] E. Oceania

## Assessment 5 (Robust Summaries With Outliers)

1. Exploring the Galton Dataset - Average and Median

For this chapter, we will use height data collected by Francis Galton for his genetics studies. Here we just use height of the children in the dataset:
```
library(HistData)
data(Galton)
x <- Galton$child
```
Compute the average and median of these data. Note: do not assign them to a variable.
```
mean(x)
```
```
## [1] 68.08847
```
```
median(x)
```
```
## [1] 68.2
```
2. Exploring the Galton Dataset - SD and MAD

Now for the same data compute the standard deviation and the median absolute deviation (MAD).
```
sd(x)
```
```
## [1] 2.517941
```
```
mad(x)
```
```
## [1] 2.9652
```
3. Error impact on average

In the previous exercises we saw that the mean and median are very similar and so are the standard deviation and MAD. This is expected since the data is approximated by a normal distribution which has this propoerty.

Now suppose that suppose Galton made a mistake when entering the first value, forgetting to use the decimal point. You can imitate this error by typing:
```
library(HistData)
data(Galton)
x <- Galton$child
x_with_error <- x
x_with_error[1] <- x_with_error[1]*10
```
The data now has an outlier that the normal approximation does not account for. Let’s see how this affects the average.

Report how many inches the average grow after this mistake. Specifically, report the difference between the average of the data with the mistake x_with_error and the data without the mistake x.
```
mean(x_with_error)-mean(x)
```
```
## [1] 0.5983836
```
4. Error impact on SD

In the previous exercise we saw how a simple mistake can result in the average of our data increasing more than half a foot, which is a large difference in practical terms. Now let’s explore the effect this outlier has on the standard deviation.

Report how many inches the SD grows after this mistake. Specifically, report the difference between the SD of the data with the mistake x_with_error and the data without the mistake x.
```
x_with_error <- x
x_with_error[1] <- x_with_error[1]*10

sd(x_with_error)-sd(x)
```
```
## [1] 15.6746
```
5. Error impact on median

In the previous exercises we saw how one mistake can have a substantial effect on the average and the standard deviation.

Now we are going to see how the median and MAD are much more resistant to outliers. For this reason we say that they are robust summaries.

Report how many inches the median grows after the mistake. Specifically, report the difference between the median of the data with the mistake x_with_error and the data without the mistake x.
```
x_with_error <- x
x_with_error[1] <- x_with_error[1]*10

median(x_with_error)-median(x)
```
```
## [1] 0
```
6. Error impact on MAD

We saw that the median barely changes. Now let’s see how the MAD is affected.

Report how many inches the MAD grows after the mistake. Specifically, report the difference between the MAD of the data with the mistake x_with_error and the data without the mistake x.
```
x_with_error <- x
x_with_error[1] <- x_with_error[1]*10

mad(x_with_error)-mad(x)
```
```
## [1] 0
```
7. Usefulness of EDA

How could you use exploratory data analysis to detect that an error was made?
- [ ] A. Since it is only one value out of many, we will not be able to detect this.
- [ ] B. We would see an obvious shift in the distribution.
- [X] C. A boxplot, histogram, or qq-plot would reveal a clear outlier.
- [ ] D. A scatter plot would show high levels of measurement error.

8. Using EDA to explore changes

We have seen how the average can be affected by outliers. But how large can this effect get? This of course depends on the size of the outlier and the size of the dataset.

To see how outliers can affect the average of a dataset, let’s write a simple function that takes the size of the outlier as input and returns the average.

Write a function called error_avg that takes a value k and returns the average of the vector x after the first entry changed to k. Show the results for k=10000 and k=-10000.
```
x <- Galton$child

error_avg <- function(k){
  x[1] <- k
  mean(x)
}

error_avg(10000)
```
```
## [1] 78.79784
```
```
error_avg(-10000)
```
```
## [1] 57.24612
```
## Section 2 Overview

In Section 2, you will learn how to create data visualizations in R using ggplot2.

After completing Section 2, you will:
- be able to use ggplot2 to create data visualizations in R.
- be able to explain what the data component of a graph is.
- be able to identify the geometry component of a graph and know when to use which type of geometry.
- be able to explain what the aesthetic mapping component of a graph is.
- be able to understand the scale component of a graph and select an appropriate scale component to use.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/ggplot2.html)

## Assessment 6 (ggplot2)

Start by loading the dplyr and ggplot2 library as well as the murders and heights data.
```
library(dplyr)
library(ggplot2)
library(dslabs)
data(heights)
data(murders)
```
1. ggplot2 basics

With ggplot2 plots can be saved as objects. For example we can associate a dataset with a plot object like this
```
p <- ggplot(data = murders)
```
Because data is the first argument we don’t need to spell it out
```
p <- ggplot(murders)
```
or, if we load dplyr, we can also use the pipe:
```
p <- murders %>% ggplot()
```
Remember the pipe sends the object on the left of %>% to be the first argument for the function the right of %>%.
What is class of the object p?
```
class(p)
```
```
## [1] "gg"     "ggplot"
```
2. Printing

Remember that to print an object you can use the command print or simply type the object. For example
```
x <- 2
x
```
```
## [1] 2
```
```
print(x)
```
```
## [1] 2
```
Print the object p defined in exercise one and describe what you see.
- [ ] A. Nothing happens.
- [X] B. A blank slate plot.
- [ ] C. A scatter plot.
- [ ] D. A histogram.

3. Pipes

Using the pipe %>%, create an object p but this time associated with the heights dataset instead of the murders dataset.
```
# define ggplot object called p like in the previous exercise but using a pipe 
p <- heights %>% ggplot()

# What is the class of the object p you have just created?
class(p)
```
```
## [1] "gg"     "ggplot"
```
4. Layers

Now we are going to add a layers and the corresponding aesthetic mappings. For the murders data we plotted total murders versus population sizes. Explore the murders data frame to remind yourself what are the names for these two variables and select the correct answer. Hint: Look at ?murders.

- [ ] A. state and abb.
- [ ] B. total_murers and population_size.
- [X] C. total and population.
- [ ] D. murders and size.

5. geom_point 1

To create the scatter plot we add a layer with geom_point. The aesthetic mappings require us to define the x-axis and y-axis variables respectively. So the code looks like this:
```
murders %>% ggplot(aes(x = , y = )) + geom_point()
```
except we have to define the two variables x and y. Fill this out with the correct variable names.
```
## Fill in the blanks
murders %>% ggplot(aes(x =population , y =total )) +
  geom_point()
```

![index](https://user-images.githubusercontent.com/17474099/75776454-5c931300-5d54-11ea-8ec3-10c571a2459c.png)

6. geom_point 1

Note that if we don’t use argument names, we can obtain the same plot by making sure we enter the variable names in the right order like this:
```
murders %>% ggplot(aes(population, total)) +
  geom_point()
```

![index](https://user-images.githubusercontent.com/17474099/75776655-a8de5300-5d54-11ea-909b-872e45a057d5.png)

Remake the plot but now with total in the x-axis and population in the y-axis.
```
murders %>% ggplot(aes(total,population)) +
  geom_point()
```

![index](https://user-images.githubusercontent.com/17474099/75776868-1f7b5080-5d55-11ea-8281-67e19557d262.png)

7. geom_point text

If instead of points we want to add text, we can use the geom_text() or geom_label() geometries. The following code
```
murders %>% ggplot(aes(population, total)) + geom_label()
```
will give us the error message: Error: geom_label requires the following missing aesthetics: label

Why is this?

- [X] A. We need to map a character to each point through the label argument in aes.
- [ ] B. We need to let geom_label know what character to use in the plot.
- [ ] C. The geom_label geometry does not require x-axis and y-axis values.
- [ ] D. geom_label is not a ggplot2 command.

8. Rewrite the code from the previous exercise to add the state abbreviation as the label through aes.
```
library(dplyr)
library(ggplot2)
library(dslabs)
data(murders)
```
```
## edit the next line to add the label
murders %>% ggplot(aes(population, total, label=abb)) +
  geom_point()+
  geom_label()
```

![index](https://user-images.githubusercontent.com/17474099/75777094-a03a4c80-5d55-11ea-991c-ca4a05ed2ea2.png)

9. geom_point colors

Change the color of the labels through blue. How will we do this?

- [ ] A. Adding a column called blue to murders
- [ ] B. Because each label needs a different color we map the colors through aes
- [ ] C. Use the color argument in ggplot
- [X] D. Because we want all colors to be blue, we do not need to map colors, just use the color argument in geom_label

10. Rewrite the code above to make the labels blue.
```
murders %>% ggplot(aes(population, total,label= abb)) +
  geom_label(color='blue')
```

![index](https://user-images.githubusercontent.com/17474099/75777261-f14a4080-5d55-11ea-9ad7-1e4eb1af596a.png)

11. geom_labels by region

Now suppose we want to use color to represent the different regions. In this case which of the following is most appropriate:

- [ ] A. Adding a column called color to murders with the color we want to use
- [X] B. Mapping the colors through the color argument of aes because each label needs a different color
- [ ] C. Using the color argument in ggplot
- [ ] D. Using the color argument in geom_label because we want all colors to be blue so we do not need to map colors

12. geom_label colors

Rewrite the code above to make the label color correspond to the state’s region.
```
## edit this code
murders %>% ggplot(aes(population, total, label = abb,color=region)) +
  geom_label()
```

![index](https://user-images.githubusercontent.com/17474099/75777598-8816fd00-5d56-11ea-8c11-40a735fc9791.png)

13. Log-scale

Now we are going to change the x-axis to a log scale to account for the fact the distribution of population is skewed. Let’s start by define an object p holding the plot we have made up to now
```
p <- murders %>% 
  ggplot(aes(population, total, label = abb, color = region)) +
  geom_label() 
```
To change the y-axis to a log scale we learned about the scale_x_log10() function. Add this layer to the object p to change the scale and render the plot.
```
p <- murders %>% ggplot(aes(population, total, label = abb, color = region)) + geom_label()

p + scale_x_log10()
```

![Unknown](https://user-images.githubusercontent.com/17474099/75803699-24ed9080-5d7f-11ea-9054-fcb5966f97e2.png)
```
#Repeat the previous exercise but now change both axes to be in the log scale.
p + scale_x_log10() + scale_y_log10()
```

![Unknown-2](https://user-images.githubusercontent.com/17474099/75803897-739b2a80-5d7f-11ea-9d5a-18ec9b41bf29.png)   
    
14. Titles

Now edit the code above to add the title “Gun murder data” to the plot. Hint: use the ggtitle function.
```
p <- murders %>% ggplot(aes(population, total, label = abb, color = region)) +
  geom_label()
# add a layer to add title to the next line
p + scale_x_log10() + 
    scale_y_log10() + ggtitle("Gun murder data")
```

![Unknown](https://user-images.githubusercontent.com/17474099/75804082-c379f180-5d7f-11ea-8fe7-c12ca342f5d2.png)

15. Histograms

We are going to shift our focus from the murders dataset to explore the heights dataset.

We use the geom_histogram function to make a histogram of the heights in the heights data frame. When reading the documentation for this function we see that it requires just one mapping, the values to be used for the histogram.

What is the variable containing the heights in inches in the heights data frame?

- [ ] A. sex
- [ ] B. heights
- [X] C. height
- [ ] D. heights$height

16. A second example

We are now going to make a histogram of the heights so we will load the heights dataset. The following code has been pre-run for you to load the heights dataset:

Create a ggplot object called p using the pipe to assign the heights data to a ggplot object. Assign height to the x values through the aes function.
```
# define p here
p <- heights %>% ggplot(aes(height))
```
17. Histograms 2

Now we are ready to add a layer to actually make the histogram.

Add a layer to the object p (created in the previous exercise) using the geom_histogram function to make the histogram.
```
p <- heights %>% 
  ggplot(aes(height))
## add a layer to p
p + geom_histogram()
```

![Unknown](https://user-images.githubusercontent.com/17474099/75804614-8f530080-5d80-11ea-9430-b5cb2cc7fc37.png)

18. Histogram binwidth

Note that when we run the code from the previous exercise we get the following warning:
```
stat_bin() using bins = 30. Pick better value with binwidth.
```
Use the binwidth argument to change the histogram made in the previous exercise to use bins of size 1 inch.
```
p <- heights %>% 
  ggplot(aes(height))
## add the geom_histogram layer but with the requested argument
p + geom_histogram(binwidth=1)
```

![Unknown](https://user-images.githubusercontent.com/17474099/75804938-2750ea00-5d81-11ea-8c2f-f873808711bf.png)

19. Smooth density plot

Now instead of a histogram we are going to make a smooth density plot. In this case, we will not make an object p. Instead we will render the plot using a single line of code. In the previous exercise, we could have created a histogram using one line of code like this:
```
heights %>% 
  ggplot(aes(height)) +
  geom_histogram()
```

![Unknown](https://user-images.githubusercontent.com/17474099/75805458-2d939600-5d82-11ea-8986-d27f5aea89a1.png)

Now instead of geom_histogram we will use geom_density to create a smooth density plot.
Add the appropriate layer to create a smooth density plot of heights.
```
## add the correct layer using +
heights %>% 
  ggplot(aes(height)) +
  geom_density()
```

![Unknown](https://user-images.githubusercontent.com/17474099/75805621-76e3e580-5d82-11ea-82a2-2e2dad7c669c.png)

20. Two smooth density plots

Now we are going to make density plots for males and females separately. We can do this using the group argument within the aes mapping. Because each point will be assigned to a different density depending on a variable from the dataset, we need to map within aes. Create separte smooth density plots for males and females by defining group by sex.
```
## add the group argument then a layer with +
heights %>% 
  ggplot(aes(height,group = sex)) + geom_density()
```

![index](https://user-images.githubusercontent.com/17474099/76071763-0d88f000-5f97-11ea-86dc-b3a21fd96141.png)

21. Two smooth density plots 2

In the previous exercise we made the two density plots, one for each sex, using:
```
heights %>% 
  ggplot(aes(height, group = sex)) + 
  geom_density()
```
![index](https://user-images.githubusercontent.com/17474099/76071763-0d88f000-5f97-11ea-86dc-b3a21fd96141.png)

We can also assign groups through the color or fill argument. For example, if you type color = sex ggplot knows you want a different color for each sex. So two densities must be drawn. You can therefore skip the group = sex mapping. Using color has the added benefit that it uses color to distinguish the groups. Change the density plots from the previous exercise to add color.
```
## edit the next line to use color instead of group then add a density layer
heights %>% 
  ggplot(aes(height, color = sex))+
  geom_density()
```

![index](https://user-images.githubusercontent.com/17474099/76072011-7ec8a300-5f97-11ea-9e11-32a66d77f6a9.png)

22. Two smooth density plots 3

We can also assign groups using the fill argument. When using the geom_density geometry, color creates a colored line for the smooth density plot while fill colors in the area under the curve.

We can see what this looks like by running the following code:
```
heights %>% 
  ggplot(aes(height, fill = sex)) + 
  geom_density() 
```

![index](https://user-images.githubusercontent.com/17474099/76072191-cea76a00-5f97-11ea-929e-2e6455293778.png)

However, here the second density is drawn over the other. We can change this by using something called alpha blending. Set the alpha parameter to 0.2 in the geom_density function to make this change.
```
heights %>% 
  ggplot(aes(height, fill = sex)) + 
  geom_density(alpha=0.2) 
```

![index](https://user-images.githubusercontent.com/17474099/76072317-09a99d80-5f98-11ea-977e-5e6881a81c21.png)

## Section 3 Overview

Section 3 introduces you to summarizing with dplyr.

After completing Section 3, you will:
- understand the importance of summarizing data in exploratory data analysis.
- be able to use the “summarize” verb in dplyr to facilitate summarizing data.
- be able to use the “group_by” verb in dplyr to facilitate summarizing data.
- be able to access values using the dot placeholder.
- be able to use “arrange” to examine data after sorting.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/tidyverse.html#tidy-data)

## Assessment 7 (Summarizing with dplyr)

**Practice Exercise. National Center for Health Statistics**

To practice our dplyr skills we will be working with data from the survey collected by the United States National Center for Health Statistics (NCHS). This center has conducted a series of health and nutrition surveys since the 1960’s.

Starting in 1999, about 5,000 individuals of all ages have been interviewed every year and then they complete the health examination component of the survey. Part of this dataset is made available via the NHANES package which can be loaded this way:
```
library(NHANES)
data(NHANES)
```
The NHANES data has many missing values. Remember that the main summarization function in R will return NA if any of the entries of the input vector is an NA. Here is an example:
```
library(dslabs)
data(na_example)
mean(na_example)
```
```
## [1] NA
```
```
sd(na_example)
```
```
## [1] NA
```
To ignore the NAs, we can use the na.rm argument:
```
mean(na_example, na.rm = TRUE)
```
```
## [1] 2.301754
```
```
sd(na_example, na.rm = TRUE)
```
```
## [1] 1.22338
```
1. Blood pressure 1

Let’s explore the NHANES data. We will be exploring blood pressure in this dataset.

First let’s select a group to set the standard. We will use 20-29 year old females. Note that the category is coded with 20-29, with a space in front of the 20! The AgeDecade is a categorical variable with these ages.

To know if someone is female, you can look at the Gender variable.

Filter the NHANES dataset so that only 20-29 year old females are included and assign this new data frame to the object tab.
Use the pipe to apply the function filter, with the appropriate logicals, to NHANES.
Remember that this age group is coded with 20-29, which includes a space. You can use head to explore the NHANES table to construct the correct call to filter.
```
library(dplyr)
library(NHANES)
data(NHANES)
## fill in what is needed
tab <- NHANES %>% filter(AgeDecade==" 20-29" & Gender=="female")
```
2. Blood pressure 2

Now we will compute the average and standard deviation for the subgroup we defined in the previous exercise (20-29 year old females), which we will use reference for what is typical.

You will determine the average and standard deviation of systolic blood pressure, which are stored in the BPSysAve variable in the NHANES dataset.

Complete the line of code to save the average and standard deviation of systolic blood pressure as average and standard_deviation to a variable called ref.
Use the summarize function after filtering for 20-29 year old females and connect the results using the pipe %>%. When doing this remember there are NAs in the data!
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
## complete this line of code.
ref <- NHANES %>% filter(AgeDecade == " 20-29" & Gender == "female") %>% summarize(average=mean(BPSysAve,na.rm=TRUE), standard_deviation=sd(BPSysAve,na.rm=TRUE))
```
3. Summarizing averages

Now we will repeat the exercise and generate only the average blood pressure for 20-29 year old females. For this exercise, you should review how to use the place holder . in dplyr.

Modify the line of sample code to assign the average to a numeric variable called ref_avg.
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
## modify the code we wrote for previous exercise.
ref_avg <- NHANES %>%
  filter(AgeDecade == " 20-29" & Gender == "female") %>%
  summarize(average = mean(BPSysAve, na.rm = TRUE), 
            standard_deviation = sd(BPSysAve, na.rm=TRUE)) %>% .$average
```
4. Min and max

Let’s continue practicing by calculating two other data summaries: the minimum and the maximum.

Again we will do it for the BPSysAve variable and the group of 20-29 year old females.

Report the min and max values for the same group as in the previous exercises.
Use filter and summarize connected by the pipe %>% again. The functions min and max can be used to get the values you want.
Within summarize, save the min and max of systolic blood pressure as min and max.
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
## complete the line
NHANES %>%
      filter(AgeDecade == " 20-29"  & Gender == "female") %>% summarize(min=min(BPSysAve,na.rm=TRUE),max=max(BPSysAve,na.rm=TRUE))
```
```
min     max
<int>   <int>
84	179
1 row
```
5. group_by

Now let’s practice using the group_by function.

What we are about to do is a very common operation in data science: you will split a data table into groups and then compute summary statistics for each group.

We will compute the average and standard deviation of systolic blood pressure for females for each age group separately. Remember that the age groups are contained in AgeDecade.

Use the functions filter, group_by, summarize, and the pipe %>% to compute the average and standard deviation of systolic blood pressure for females for each age group separately.

Within summarize, save the average and standard deviation of systolic blood pressure (BPSysAve) as average and standard_deviation.
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
##complete the line with group_by and summarize
NHANES %>%
      filter(Gender == "female") %>% group_by(AgeDecade) %>% summarize(average=mean(BPSysAve,na.rm=TRUE),standard_deviation = sd(BPSysAve,na.rm=TRUE))
```
```
AgeDecade       average      standard_deviation
<fctr>          <dbl>        <dbl>
0-9	        99.95041     9.071798
10-19	        104.27466    9.461431
20-29	        108.42243    10.146681
30-39	        111.25512    12.314790
40-49	        115.49385    14.530054
50-59	        121.84245    16.179333
60-69	        127.17787    17.125713
70+	        133.51652    19.841781
NA	        141.54839    22.908521
9 rows
```
6. group_by example 2

Now let’s practice using group_by some more. We are going to repeat the previous exercise of calculating the average and standard deviation of systolic blood pressure, but for males instead of females.

This time we will not provide much sample code. You are on your own!

Calculate the average and standard deviation of systolic blood pressure for males for each age group separately using the same methods as in the previous exercise.
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
NHANES %>%
      filter(Gender == "male") %>% group_by(AgeDecade) %>% summarize(average=mean(BPSysAve,na.rm=TRUE),standard_deviation = sd(BPSysAve,na.rm=TRUE))
```
```
AgeDecade       average      standard_deviation
<fctr>          <dbl>        <dbl>
0-9	        97.41912     8.317367
10-19	        109.59789    11.227769
20-29	        117.85084    11.274795
30-39	        119.40063    12.306656
40-49	        120.78390    13.968338
50-59	        125.75000    17.760536
60-69	        126.88578    17.478117
70+	        130.20172    18.657475
NA	        136.40000    23.534731
9 rows
```
7. group_by example 3

We can actually combine both of these summaries into a single line of code. This is because group_by permits us to group by more than one variable.

We can use group_by(AgeDecade, Gender) to group by both age decades and gender.

Create a single summary table for the average and standard deviation of systolic blood pressure using group_by(AgeDecade, Gender).

Note that we no longer have to filter!

Your code within summarize should remain the same as in the previous exercises.
```
library(NHANES)
data(NHANES)
```
```
NHANES %>% group_by(AgeDecade, Gender) %>% summarize(average=mean(BPSysAve,na.rm=TRUE),standard_deviation = sd(BPSysAve,na.rm=TRUE))
```
```
AgeDecade    Gender     average      standard_deviation
<fctr>       <fctr>     <dbl>        <dbl>
0-9	     female	99.95041     9.071798
0-9	     male	97.41912     8.317367
10-19	     female	104.27466    9.461431
10-19	     male	109.59789    11.227769
20-29	     female	108.42243    10.146681
20-29	     male	117.85084    11.274795
30-39	     female	111.25512    12.314790
30-39	     male	119.40063    12.306656
40-49	     female	115.49385    14.530054
40-49	     male	120.78390    13.968338
1-10 of 18 rows
```
8. Arrange

Now we are going to explore differences in systolic blood pressure across races, as reported in the Race1 variable.

We will learn to use the arrange function to order the outcome acording to one variable.

Note that this function can be used to order any table by a given outcome. Here is an example that arranges by systolic blood pressure.
```
NHANES %>% arrange(BPSysAve)
```
```
ID        SurveyYr    Gender     Age        AgeDecade     AgeMonths    Race1      Race3       Education
<int>     <fctr>      <fctr>     <int>      <fctr>        <int>        <fctr>     <fctr>      <fctr>
53661	  2009_10     male	 12	    10-19	  145	       Mexican	  NA	      NA	
58821	  2009_10     female	 51	    50-59	  613	       White	  NA	      9 - 11th Grade	
67253	  2011_12     female	 10	    10-19	  NA	       White	  White	      NA	
51893	  2009_10     female	 70	    70+	          843	       White	  NA	      9 - 11th Grade	
54375	  2009_10     male	 76	    70+	          912	       White	  NA	      High School	
54375	  2009_10     male	 76	    70+	          912	       White	  NA	      High School	
58941	  2009_10     male	 8	    0-9	          104	       Mexican	  NA	      NA	
67616	  2011_12     male	 63	    60-69	  NA	       White	  White	      9 - 11th Grade	
67616	  2011_12     male	 63	    60-69	  NA	       White	  White	      9 - 11th Grade	
67616	  2011_12     male	 63	    60-69	  NA	       White	  White	      9 - 11th Grade	
...
1-10 of 10,000 rows | 1-9 of 76 columns
```
If we want it in descending order we can use the desc function like this:
```
NHANES %>% arrange(desc(BPSysAve))
```
```
ID        SurveyYr    Gender     Age        AgeDecade     AgeMonths    Race1      Race3       Education
<int>     <fctr>      <fctr>     <int>      <fctr>        <int>        <fctr>     <fctr>      <fctr>
55311	  2009_10     female	 55	    50-59	  671	       Hispanic	  NA	      Some College	
67957	  2011_12     male	 50	    50-59	  NA	       Black	  Black	      9 - 11th Grade	
67957	  2011_12     male	 50	    50-59	  NA	       Black	  Black	      9 - 11th Grade	
62727	  2011_12     female	 80	    NA	          NA	       White	  White	      Some College	
62727	  2011_12     female	 80	    NA	          NA	       White	  White	      Some College	
53371	  2009_10     male	 68	    60-69	  817	       White	  NA	      9 - 11th Grade	
58276	  2009_10     female	 80	    NA	          NA	       White	  NA	      College Grad	
65475	  2011_12     female	 44	    40-49	  NA	       Black	  Black	      High School	
60848	  2009_10     male	 80	    NA	          NA	       Other	  NA	      College Grad	
68301	  2011_12     male	 59	    50-59	  NA	       White	  White	      High School	
...
1-10 of 10,000 rows | 1-9 of 76 columns
```
In this example, we will compare systolic blood pressure across values of the Race1 variable for males between the ages of 40-49.

Compute the average and standard deviation for each value of Race1 for males in the age decade 40-49.
Order the resulting table from lowest to highest average systolic blood pressure.
Use the functions filter, group_by, summarize, arrange, and the pipe %>% to do this in one line of code.
Within summarize, save the average and standard deviation of systolic blood pressure as average and standard_deviation.
```
library(dplyr)
library(NHANES)
data(NHANES)
```
```
NHANES %>%
      filter(AgeDecade ==" 40-49" & Gender == "male")  %>% group_by(Race1) %>% summarize(average=mean(BPSysAve,na.rm=TRUE),standard_deviation = sd(BPSysAve,na.rm=TRUE))%>% arrange(average)
```
```
Race1       average        standard_deviation
<fctr>      <dbl>          <dbl>
White	    119.9188	   13.42355
Other	    120.4000	   16.20241
Hispanic    121.6098	   11.06770
Mexican	    121.8500	   13.93756
Black	    125.8387	   17.06707
5 rows
```
## Section 4 Overview

In Section 4, you will look at a case study involving data from the Gapminder Foundation about trends in world health and economics.

After completing Section 4, you will:
- understand how Hans Rosling and the Gapminder Foundation use effective data visualization to convey data-based trends.
- be able to apply the ggplot2 techniques from the previous section to answer questions using data.
- understand how fixed scales across plots can ease comparisons.
- be able to modify graphs to improve data visualization.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/gapminder.html#case-study-new-insights-on-poverty)

## Assessment 8 (Exploring the Gapminder Dataset)

1. Life expectancy vs fertility - part 1

The [Gapminder Foundation](https://www.gapminder.org/) is a non-profit organization based in Sweden that promotes global development through the use of statistics that can help reduce misconceptions about global development.

- Using ggplot and the points layer, create a scatter plot of life expectancy versus fertility for the African continent in 2012.
- Remember that you can use the R console to explore the gapminder dataset to figure out the names of the columns in the dataframe.
- In this exercise we provide parts of code to get you going. You need to fill out what is missing. But note that going forward, in the next exercises, you will be required to write most of the code.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)
head(gapminder)
```
```
   country             year       infant_mortality      life_expectancy     fertility     population
   <fctr>              <int>      <dbl>                 <dbl>               <dbl>         <dbl>
1  Albania	       1960	  115.40	        62.87	            6.19	  1636054	
2  Algeria	       1960	  148.20	        47.50               7.65	  11124892	
3  Angola	       1960	  208.00	        35.98	            7.32	  5270844	
4  Antigua and Barbuda 1960	  NA	                62.97	            4.43	  54681	
5  Argentina	       1960	  59.87	                65.39	            3.11	  20619075	
6  Armenia	       1960	  NA	                66.86	            4.55	  1867396	
6 rows | 1-7 of 10 columns
```
```
## fill out the missing parts in filter and aes
gapminder %>% filter(continent=="Africa" & year=="2012") %>%
  ggplot(aes(fertility,life_expectancy)) +
  geom_point()
```
![index](https://user-images.githubusercontent.com/17474099/76077478-1252a180-5fa1-11ea-8a6f-ab77face26e4.png)

2. Life expectancy vs fertility - part 2 - coloring your plot

Note that there is quite a bit of variability in life expectancy and fertility with some African countries having very high life expectancies. There also appear to be three clusters in the plot.

Remake the plot from the previous exercises but this time use color to dinstinguish the different regions of Africa to see if this explains the clusters. Remember that you can explore the gapminder data to see how the regions of Africa are labeled in the dataframe!
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)

gapminder %>% filter(continent=="Africa" & year=="2012") %>%
  ggplot(aes(fertility,life_expectancy, color=region)) +
  geom_point()
```

![index](https://user-images.githubusercontent.com/17474099/76077664-6e1d2a80-5fa1-11ea-8fb1-256ad41ec093.png)

3. Life expectancy vs fertility - part 3 - selecting country and region

While many of the countries in the high life expectancy/low fertility cluster are from Northern Africa, three countries are not.

- Create a table showing the country and region for the African countries (use select) that in 2012 had fertility rates of 3 or less and life expectancies of at least 70.
- Assign your result to a data frame called df.
```
library(dplyr)
library(dslabs)
```
```
data(gapminder)
head(gapminder)
```
```
   country             year       infant_mortality      life_expectancy     fertility     population
   <fctr>              <int>      <dbl>                 <dbl>               <dbl>         <dbl>
1  Albania	       1960	  115.40	        62.87 	            6.19	  1636054	
2  Algeria	       1960	  148.20	        47.50	            7.65	  11124892	
3  Angola	       1960	  208.00	        35.98	            7.32	  5270844	
4  Antigua and Barbuda 1960	  NA	                62.97	            4.43	  54681	
5  Argentina	       1960	  59.87	                65.39	            3.11	  20619075	
6  Armenia	       1960	  NA	                66.86	            4.55	  1867396	
6 rows | 1-7 of 10 columns
```
```
df <- gapminder %>% filter(continent=="Africa" & year=="2012" & fertility <=3 & life_expectancy>=70) %>%
  select(country,region)
```
4. Life expectancy and the Vietnam War - part 1

The Vietnam War lasted from 1955 to 1975. Do the data support war having a negative effect on life expectancy? We will create a time series plot that covers the period from 1960 to 2010 of life expectancy for Vietnam and the United States, using color to distinguish the two countries. In this start we start the analysis by generating a table.

- Use filter to create a table with data for the years from 1960 to 2010 in Vietnam and the United States.
- Save the table in an object called tab.
```
library(dplyr)
library(dslabs)
```
```
data(gapminder)

head(gapminder)
```
```
   country             year       infant_mortality      life_expectancy     fertility     population
   <fctr>              <int>      <dbl>                 <dbl>               <dbl>         <dbl>
1  Albania	       1960	  115.40	        62.87	            6.19	  1636054	
2  Algeria	       1960	  148.20	        47.50	            7.65	  11124892	
3  Angola	       1960	  208.00	        35.98	            7.32	  5270844	
4  Antigua and Barbuda 1960	  NA	                62.97	            4.43	  54681	
5  Argentina	       1960	  59.87	                65.39	            3.11	  20619075	
6  Armenia	       1960	  NA	                66.86	            4.55	  1867396	
6 rows | 1-7 of 10 columns
```
```
tab <- gapminder %>% filter(year>=1960 & year<=2010 & country%in%c("Vietnam","United States"))
```
5. Life expectancy and the Vietnam War - part 2

Now that you have created the data table in Exercise 4, it is time to plot the data for the two countries.

- Use geom_line to plot life expectancy vs year for Vietnam and the United States. The data table is stored in tab.
- Use color to distinguish the two countries.
```
p <- tab %>% ggplot(aes(year,life_expectancy,color=country)) + geom_line()
p
```

![index](https://user-images.githubusercontent.com/17474099/76078449-ffd96780-5fa2-11ea-8f57-93389b4435bf.png)

6. Life expectancy in Cambodia

Cambodia was also involved in this conflict and, after the war, Pol Pot and his communist Khmer Rouge took control and ruled Cambodia from 1975 to 1979. He is considered one of the most brutal dictators in history. Do the data support this claim?

Use a single line of code to create a time series plot from 1960 to 2010 of life expectancy vs year for Cambodia.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)

gapminder %>% filter(year>=1960 & year <= 2010 & country=="Cambodia") %>% ggplot(aes(year,life_expectancy)) + geom_line()
```

![index](https://user-images.githubusercontent.com/17474099/76078812-b50c1f80-5fa3-11ea-8301-e3f67e12470b.png)

7. Dollars per day - part 1

Now we are going to calculate and plot dollars per day for African countries in 2010 using GDP data.

In the first part of this analysis, we will create the dollars per day variable.
- Use mutate to create a dollars_per_day variable, which is defined as gdp/population/365.
- Create the dollars_per_day variable for African countries for the year 2010.
- Remove any NA values.
- Save the mutated dataset as daydollars.
```
library(dplyr)
library(dslabs)
```
```
data(gapminder)
daydollars <- gapminder %>% mutate(dollars_per_day=gdp/population/365)%>% filter(year==2010 & continent=="Africa" & !is.na(dollars_per_day))
```
8. Dollars per day - part 2

Now we are going to calculate and plot dollars per day for African countries in 2010 using GDP data.

In the second part of this analysis, we will plot the smooth density plot using a log (base 2) x axis.
- The dataset including the dollars_per_day variable is preloaded as daydollars.
- Create a smooth density plot of dollars per day from daydollars.
- Use a log (base 2) scale for the x axis.
```
daydollars %>% ggplot(aes(dollars_per_day)) + geom_density() + scale_x_continuous(trans="log2")
```

![index](https://user-images.githubusercontent.com/17474099/76079001-16cc8980-5fa4-11ea-87da-614f4318ae88.png)

9. Dollars per day - part 3 - multiple density plots

Now we are going to combine the plotting tools we have used in the past two exercises to create density plots for multiple years.
- Create the dollars_per_day variable as in Exercise 7, but for African countries in the years 1970 and 2010 this time.
- Make sure you remove any NA values.
- Create a smooth density plot of dollars per day for 1970 and 2010 using a log (base 2) scale for the x axis.
- Use facet_grid to show a different density plot for 1970 and 2010.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)

daydollars <- gapminder %>% mutate(dollars_per_day=gdp/population/365)%>% filter(year %in% c(1970,2010) & continent=="Africa" & !is.na(dollars_per_day))

daydollars %>% ggplot(aes(dollars_per_day)) + geom_density() + scale_x_continuous(trans='log2') + facet_grid(.~year)
```

![index](https://user-images.githubusercontent.com/17474099/76079192-74f96c80-5fa4-11ea-8fcf-1ccb1aa19636.png)

10. Dollars per day - part 4 - stacked histograms

Now we are going to edit the code from Exercise 9 to show stacked histograms of each region in Africa.

Much of the code will be the same as in Exercise 9:
- Create the dollars_per_day variable as in Exercise 7, but for African countries in the years 1970 and 2010 this time.
- Make sure you remove any NA values.
- Create a smooth density plot of dollars per day for 1970 and 2010 using a log (base 2) scale for the x axis.
- Use facet_grid to show a different density plot for 1970 and 2010.
- Make sure the densities are smooth by using bw = 0.5.
- Use the fill and position arguments where appropriate to create the stacked histograms of each region.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)

daydollars <- gapminder %>% mutate(dollars_per_day=gdp/population/365)%>% filter(year %in% c(1970,2010) & continent=="Africa" & !is.na(dollars_per_day))

daydollars %>% ggplot(aes(dollars_per_day,fill = region)) + geom_density(bw=0.5,position='stack') + scale_x_continuous(trans='log2') + facet_grid(.~year)
```

![index](https://user-images.githubusercontent.com/17474099/76079366-c86bba80-5fa4-11ea-8a1e-00ac6915239a.png)

11. Infant mortality scatter plot - part 1

We are going to continue looking at patterns in the gapminder dataset by plotting infant mortality rates versus dollars per day for African countries.
- Generate dollars_per_day using mutate and filter for the year 2010 for African countries.
- Remember to remove NA values.
- Store the mutated dataset in gapminder_Africa_2010.
- Make a scatter plot of infant_mortaility versus dollars_per_day for countries in the African continent.
- Use color to denote the different regions of Africa.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)
gapminder_Africa_2010 <- daydollars <- gapminder %>% mutate(dollars_per_day=gdp/population/365)%>% filter(year %in% c(2010) & continent=="Africa" & !is.na(dollars_per_day))

# now make the scatter plot

gapminder_Africa_2010 %>% ggplot(aes(dollars_per_day,infant_mortality,color = region)) + geom_point()
```

![index](https://user-images.githubusercontent.com/17474099/76079538-226c8000-5fa5-11ea-8a89-fb738049dfcf.png)

12. Infant mortality scatter plot - part 2 - logarithmic axis

Now we are going to transform the x axis of the plot from the previous exercise.
- The mutated dataset is preloaded as gapminder_Africa_2010.
- As in the previous exercise, make a scatter plot of infant_mortaility versus dollars_per_day for countries in the African continent.
- As in the previous exercise, use color to denote the different regions of Africa.
- Transform the x axis to be in the log (base 2) scale.
```
gapminder_Africa_2010 %>% ggplot(aes(dollars_per_day,infant_mortality, color=region)) + geom_point() + scale_x_continuous(trans='log2')
```

![index](https://user-images.githubusercontent.com/17474099/76079652-619ad100-5fa5-11ea-87ab-893c889572df.png)

13. Infant mortality scatter plot - part 3 - adding labels

Note that there is a large variation in infant mortality and dollars per day among African countries.

As an example, one country has infant mortality rates of less than 20 per 1000 and dollars per day of 16, while another country has infant mortality rates over 10% and dollars per day of about 1.

In this exercise, we will remake the plot from Exercise 12 with country names instead of points so we can identify which countries are which.
- The mutated dataset is preloaded as gapminder_Africa_2010.
- As in the previous exercise, make a scatter plot of infant_mortaility versus dollars_per_day for countries in the African continent.
- As in the previous exercise, use color to denote the different regions of Africa.
- As in the previous exercise, transform the x axis to be in the log (base 2) scale.
- Add a layer to display country names instead of points.
```
gapminder_Africa_2010 %>% ggplot(aes(dollars_per_day,infant_mortality, color=region,label = country)) + geom_point() + scale_x_continuous(trans='log2') +
    geom_text()
```

![index](https://user-images.githubusercontent.com/17474099/76079763-acb4e400-5fa5-11ea-9c68-a36471bafd20.png)

14. Infant mortality scatter plot - part 4 - comparison of scatter plots

Now we are going to look at changes in the infant mortality and dollars per day patterns African countries between 1970 and 2010.
- Generate dollars_per_day using mutate and filter for the years 1970 and 2010 for African countries.
- Remember to remove NA values.
- As in the previous exercise, make a scatter plot of infant_mortaility versus dollars_per_day for countries in the African continent.
- As in the previous exercise, use color to denote the different regions of Africa.
- As in the previous exercise, transform the x axis to be in the log (base 2) scale.
- As in the previous exercise, add a layer to display country names instead of points.
- Use facet_grid to show different plots for 1970 and 2010.
```
library(dplyr)
library(ggplot2)
library(dslabs)
```
```
data(gapminder)
gapminder  %>%
    filter(continent == "Africa" & year %in% c(1970,2010) & !is.na(gdp) & !is.na(year) & !is.na(infant_mortality)) %>%
    mutate(dollars_per_day = gdp/population/365) %>%
    ggplot(aes(dollars_per_day, infant_mortality, color = region,label = country)) +
    geom_point() +
    scale_x_continuous(trans = "log2") +
    geom_text() +
    facet_grid(year~.)
```

![index](https://user-images.githubusercontent.com/17474099/76079914-09b09a00-5fa6-11ea-8f39-f8556253ee2c.png)

## Section 5 Overview

Section 5 covers some general principles that can serve as guides for effective data visualization.

After completing Section 5, you will:
- understand basic principles of effective data visualization.
- understand the importance of keeping your goal in mind when deciding on a visualization approach.
- understand principles for encoding data, including position, aligned lengths, angles, area, brightness, and color hue.
- know when to include the number zero in visualizations.
- be able to use techniques to ease comparisons, such as using common axes, putting visual cues to be compared adjacent to one another, and using color effectively.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/data-visualization-principles.html)

## Assessment 9 (Data Visualization Principles, Part 1)

1: Customizing plots - Pie charts

Pie charts are appropriate:
- [ ] A. When we want to display percentages.
- [ ] B. When ggplot2 is not available.
- [ ] C. When I am in a bakery.
- [X] D. Never. Barplots and tables are always better.

2. Customizing plots - What’s wrong?

What is the problem with this plot?



A. The values are wrong. The final vote was 306 to 232.

B. The axis does not start at 0. Judging by the length, it appears Trump received 3 times as many votes when in fact it was about 30% more.

C. The colors should be the same.

D. Percentages should be shown as a pie chart.

3: Customizing plots - What’s wrong 2?.
Take a look at the following two plots. They show the same information: rates of measles by state in the United States for 1928.
distribution

A. Both plots provide the same information, so they are equally good.

B. The plot on the left is better because it orders the states alphabetically.

C. The plot on the right is better because it orders the states by disease rate so we can quickly see the states with highest and lowest rates.

D. Both plots should be pie charts instead.
Assessment 10 (Data Visualization Principles, Part 2)

1: Customizing plots - watch and learn
To make the plot on the right in the exercise from the last set of assessments, we had to reorder the levels of the states’ variables.

    Redefine the state object so that the levels are re-ordered by rate.
    Print the new object state and its levels so you can see that the vector is now re-ordered by the levels.

library(dplyr)
library(ggplot2)
library(dslabs)

dat <- us_contagious_diseases %>%
filter(year == 1967 & disease=="Measles" & !is.na(population)) %>% mutate(rate = count / population * 10000 * 52 / weeks_reporting)
state <- dat$state 
rate <- dat$count/(dat$population/10000)*(52/dat$weeks_reporting)

state <- reorder(state,rate)
print(state)

##  [1] Alabama              Alaska               Arizona             
##  [4] Arkansas             California           Colorado            
##  [7] Connecticut          Delaware             District Of Columbia
## [10] Florida              Georgia              Hawaii              
## [13] Idaho                Illinois             Indiana             
## [16] Iowa                 Kansas               Kentucky            
## [19] Louisiana            Maine                Maryland            
## [22] Massachusetts        Michigan             Minnesota           
## [25] Mississippi          Missouri             Montana             
## [28] Nebraska             Nevada               New Hampshire       
## [31] New Jersey           New Mexico           New York            
## [34] North Carolina       North Dakota         Ohio                
## [37] Oklahoma             Oregon               Pennsylvania        
## [40] Rhode Island         South Carolina       South Dakota        
## [43] Tennessee            Texas                Utah                
## [46] Vermont              Virginia             Washington          
## [49] West Virginia        Wisconsin            Wyoming             
## attr(,"scores")
##              Alabama               Alaska              Arizona 
##           4.16107582           5.46389893           6.32695891 
##             Arkansas           California             Colorado 
##           6.87899954           2.79313560           7.96331905 
##          Connecticut             Delaware District Of Columbia 
##           0.36986840           1.13098183           0.35873614 
##              Florida              Georgia               Hawaii 
##           2.89358806           0.09987991           2.50173748 
##                Idaho             Illinois              Indiana 
##           6.03115170           1.20115480           1.34027323 
##                 Iowa               Kansas             Kentucky 
##           2.94948911           0.66386422           4.74576011 
##            Louisiana                Maine             Maryland 
##           0.46088071           2.57520433           0.49922233 
##        Massachusetts             Michigan            Minnesota 
##           0.74762338           1.33466700           0.37722410 
##          Mississippi             Missouri              Montana 
##           3.11366532           0.75696354           5.00433320 
##             Nebraska               Nevada        New Hampshire 
##           3.64389801           6.43683882           0.47181511 
##           New Jersey           New Mexico             New York 
##           0.88414264           6.15969926           0.66849058 
##       North Carolina         North Dakota                 Ohio 
##           1.92529764          14.48024642           1.16382241 
##             Oklahoma               Oregon         Pennsylvania 
##           3.27496900           8.75036439           0.67687303 
##         Rhode Island       South Carolina         South Dakota 
##           0.68207448           2.10412531           0.90289534 
##            Tennessee                Texas                 Utah 
##           5.47344506          12.49773953           4.03005836 
##              Vermont             Virginia           Washington 
##           1.00970314           5.28270939          17.65180349 
##        West Virginia            Wisconsin              Wyoming 
##           8.59456463           4.96246019           6.97303449 
## 51 Levels: Georgia District Of Columbia Connecticut ... Washington

levels(state)

##  [1] "Georgia"              "District Of Columbia" "Connecticut"         
##  [4] "Minnesota"            "Louisiana"            "New Hampshire"       
##  [7] "Maryland"             "Kansas"               "New York"            
## [10] "Pennsylvania"         "Rhode Island"         "Massachusetts"       
## [13] "Missouri"             "New Jersey"           "South Dakota"        
## [16] "Vermont"              "Delaware"             "Ohio"                
## [19] "Illinois"             "Michigan"             "Indiana"             
## [22] "North Carolina"       "South Carolina"       "Hawaii"              
## [25] "Maine"                "California"           "Florida"             
## [28] "Iowa"                 "Mississippi"          "Oklahoma"            
## [31] "Nebraska"             "Utah"                 "Alabama"             
## [34] "Kentucky"             "Wisconsin"            "Montana"             
## [37] "Virginia"             "Alaska"               "Tennessee"           
## [40] "Idaho"                "New Mexico"           "Arizona"             
## [43] "Nevada"               "Arkansas"             "Wyoming"             
## [46] "Colorado"             "West Virginia"        "Oregon"              
## [49] "Texas"                "North Dakota"         "Washington"

2: Customizing plots - redefining
Now we are going to customize this plot a little more by creating a rate variable and reordering by that variable instead.

    Add a single line of code to the definition of the dat table that uses mutate to reorder the states by the rate variable.
    The sample code provided will then create a bar plot using the newly defined dat.

library(dplyr)
library(ggplot2)
library(dslabs)

data(us_contagious_diseases)
dat <- us_contagious_diseases %>% filter(year == 1967 & disease=="Measles" & count>0 & !is.na(population)) %>%
  mutate(rate = count / population * 10000 * 52 / weeks_reporting) %>% mutate(state = reorder(state, rate))
dat %>% ggplot(aes(state, rate)) +
  geom_bar(stat="identity") +
  coord_flip()

3: Showing the data and customizing plots
Say we are interested in comparing gun homicide rates across regions of the US. We see this plot:

library(dplyr)
library(ggplot2)
library(dslabs)

data("murders")
murders %>% mutate(rate = total/population*100000) %>%
  group_by(region) %>%
  summarize(avg = mean(rate)) %>%
  mutate(region = factor(region)) %>%
  ggplot(aes(region, avg)) +
  geom_bar(stat="identity") +
  ylab("Murder Rate Average")

and decide to move to a state in the western region. What is the main problem with this interpretaion?

A. The categories are ordered alphabetically.

B. The graph does not show standard errors.

C. It does not show all the data. We do not see the variability within a region and it's possible that the safest states are not in the West.

D. The Northeast has the lowest average.

4: Making a box plot
To further investigate whether moving to the western region is a wise decision, let’s make a box plot of murder rates by region, showing all points.

    Make a box plot of the murder rates by region.
    Order the regions by their median murder rate.
    Show all of the points on the box plot.

library(dplyr)
library(ggplot2)
library(dslabs)

data("murders")
murders %>% mutate(rate = total/population*100000) %>%
  mutate(region=reorder(region, rate, FUN=median)) %>%
  ggplot(aes(region, rate)) +
  geom_boxplot() +
  geom_point()

Assessment 11 (Data Visualization Principles, Part 3)

    Tile plot - measles and smallpox
    The sample code given creates a tile plot showing the rate of measles cases per population. We are going to modify the tile plot to look at smallpox cases instead.

library(dplyr)
library(ggplot2)
library(RColorBrewer)
library(dslabs)

data(us_contagious_diseases)
head(us_contagious_diseases)

 
 
	
disease
<fctr>
	
state
<fctr>
	
year
<dbl>
	
weeks_reporting
<int>
	
count
<dbl>
	
population
<dbl>
1	Hepatitis A	Alabama	1966	50	321	3345787
2	Hepatitis A	Alabama	1967	49	291	3364130
3	Hepatitis A	Alabama	1968	52	314	3386068
4	Hepatitis A	Alabama	1969	49	380	3412450
5	Hepatitis A	Alabama	1970	51	413	3444165
6	Hepatitis A	Alabama	1971	51	378	3481798
6 rows

the_disease = "Measles"
dat <- us_contagious_diseases %>% 
   filter(!state%in%c("Hawaii","Alaska") & disease == the_disease) %>% 
   mutate(rate = count / population * 10000) %>% 
   mutate(state = reorder(state, rate))

dat %>% ggplot(aes(year, state, fill = rate)) + 
  geom_tile(color = "grey50") + 
  scale_x_continuous(expand=c(0,0)) + 
  scale_fill_gradientn(colors = brewer.pal(9, "Reds"), trans = "sqrt") + 
  theme_minimal() + 
  theme(panel.grid = element_blank()) + 
  ggtitle(the_disease) + 
  ylab("") + 
  xlab("")

    Modify the tile plot to show the rate of smallpox cases instead of measles cases.
    Exclude years in which cases were reported in fewer than 10 weeks from the plot.

library(dplyr)
library(ggplot2)
library(RColorBrewer)
library(dslabs)

data(us_contagious_diseases)
head(us_contagious_diseases)

 
 
	
disease
<fctr>
	
state
<fctr>
	
year
<dbl>
	
weeks_reporting
<int>
	
count
<dbl>
	
population
<dbl>
1	Hepatitis A	Alabama	1966	50	321	3345787
2	Hepatitis A	Alabama	1967	49	291	3364130
3	Hepatitis A	Alabama	1968	52	314	3386068
4	Hepatitis A	Alabama	1969	49	380	3412450
5	Hepatitis A	Alabama	1970	51	413	3444165
6	Hepatitis A	Alabama	1971	51	378	3481798
6 rows

the_disease = "Smallpox"
dat <- us_contagious_diseases %>% 
   filter(!state%in%c("Hawaii","Alaska") & disease == the_disease & !weeks_reporting<10) %>% 
   mutate(rate = count / population * 10000) %>% 
   mutate(state = reorder(state, rate))

dat %>% ggplot(aes(year, state, fill = rate)) + 
  geom_tile(color = "grey50") + 
  scale_x_continuous(expand=c(0,0)) + 
  scale_fill_gradientn(colors = brewer.pal(9, "Reds"), trans = "sqrt") + 
  theme_minimal() + 
  theme(panel.grid = element_blank()) + 
  ggtitle(the_disease) + 
  ylab("") + 
  xlab("")

    Time series plot - measles and smallpox
    The sample code given creates a time series plot showing the rate of measles cases per population by state. We are going to again modify this plot to look at smallpox cases instead.

library(dplyr)
library(ggplot2)
library(dslabs)
library(RColorBrewer)

data(us_contagious_diseases)

the_disease = "Measles"
dat <- us_contagious_diseases %>%
   filter(!state%in%c("Hawaii","Alaska") & disease == the_disease) %>%
   mutate(rate = count / population * 10000) %>%
   mutate(state = reorder(state, rate))
str(dat)

## 'data.frame':    3724 obs. of  7 variables:
##  $ disease        : Factor w/ 7 levels "Hepatitis A",..: 2 2 2 2 2 2 2 2 2 2 ...
##  $ state          : Factor w/ 51 levels "Mississippi",..: 9 9 9 9 9 9 9 9 9 9 ...
##   ..- attr(*, "scores")= num [1:51(1d)] 9.27 NA 24.15 9.37 19.16 ...
##   .. ..- attr(*, "dimnames")=List of 1
##   .. .. ..$ : chr  "Alabama" "Alaska" "Arizona" "Arkansas" ...
##  $ year           : num  1928 1929 1930 1931 1932 ...
##  $ weeks_reporting: int  52 49 52 49 41 51 52 49 40 49 ...
##  $ count          : num  8843 2959 4156 8934 270 ...
##  $ population     : num  2589923 2619131 2646248 2670818 2693027 ...
##  $ rate           : num  34.1 11.3 15.7 33.5 1 ...

avg <- us_contagious_diseases %>%
  filter(disease==the_disease) %>% group_by(year) %>%
  summarize(us_rate = sum(count, na.rm=TRUE)/sum(population, na.rm=TRUE)*10000)

dat %>% ggplot() +
  geom_line(aes(year, rate, group = state),  color = "grey50", 
            show.legend = FALSE, alpha = 0.2, size = 1) +
  geom_line(mapping = aes(year, us_rate),  data = avg, size = 1, color = "black") +
  scale_y_continuous(trans = "sqrt", breaks = c(5,25,125,300)) + 
  ggtitle("Cases per 10,000 by state") + 
  xlab("") + 
  ylab("") +
  geom_text(data = data.frame(x=1955, y=50), mapping = aes(x, y, label="US average"), color="black") + 
  geom_vline(xintercept=1963, col = "blue")

    Modify the sample code for the time series plot to plot data for smallpox instead of for measles.
    Once again, restrict the plot to years in which cases were reported in at least 10 weeks.

library(dplyr)
library(ggplot2)
library(dslabs)
library(RColorBrewer)

data(us_contagious_diseases)

the_disease = "Smallpox"
dat <- us_contagious_diseases %>%
   filter(!state%in%c("Hawaii","Alaska") & disease == the_disease & !weeks_reporting<10) %>%
   mutate(rate = count / population * 10000) %>%
   mutate(state = reorder(state, rate))
str(dat)

## 'data.frame':    1014 obs. of  7 variables:
##  $ disease        : Factor w/ 7 levels "Hepatitis A",..: 7 7 7 7 7 7 7 7 7 7 ...
##  $ state          : Factor w/ 51 levels "Rhode Island",..: 17 17 17 17 17 17 17 17 17 17 ...
##   ..- attr(*, "scores")= num [1:51(1d)] 0.382 NA 2.011 0.805 0.924 ...
##   .. ..- attr(*, "dimnames")=List of 1
##   .. .. ..$ : chr  "Alabama" "Alaska" "Arizona" "Arkansas" ...
##  $ year           : num  1928 1929 1930 1931 1932 ...
##  $ weeks_reporting: int  51 52 52 52 52 52 52 52 51 52 ...
##  $ count          : num  341 378 192 295 467 82 23 42 12 54 ...
##  $ population     : num  2589923 2619131 2646248 2670818 2693027 ...
##  $ rate           : num  1.317 1.443 0.726 1.105 1.734 ...

avg <- us_contagious_diseases %>%
  filter(disease==the_disease) %>% group_by(year) %>%
  summarize(us_rate = sum(count, na.rm=TRUE)/sum(population, na.rm=TRUE)*10000)

dat %>% ggplot() +
  geom_line(aes(year, rate, group = state),  color = "grey50", 
            show.legend = FALSE, alpha = 0.2, size = 1) +
  geom_line(mapping = aes(year, us_rate),  data = avg, size = 1, color = "black") +
  scale_y_continuous(trans = "sqrt", breaks = c(5,25,125,300)) + 
  ggtitle("Cases per 10,000 by state") + 
  xlab("") + 
  ylab("") +
  geom_text(data = data.frame(x=1955, y=50), mapping = aes(x, y, label="US average"), color="black") + 
  geom_vline(xintercept=1963, col = "blue")

    Time series plot - all diseases in California
    Now we are going to look at the rates of all diseases in one state. Again, you will be modifying the sample code to produce the desired plot.

    For the state of California, make a time series plot showing rates for all diseases.
    Include only years with 10 or more weeks reporting.
    Use a different color for each disease.

library(dplyr)
library(ggplot2)
library(dslabs)
library(RColorBrewer)

data(us_contagious_diseases)

us_contagious_diseases %>% filter(state=="California" & !weeks_reporting<10) %>% 
  group_by(year, disease) %>%
  summarize(rate = sum(count)/sum(population)*10000) %>%
  ggplot(aes(year, rate,color=disease)) + 
  geom_line()

    Time series plot - all diseases in the United States
    Now we are going to make a time series plot for the rates of all diseases in the United States. For this exercise, we have provided less sample code - you can take a look at the previous exercise to get you started.

    Compute the US rate by using summarize to sum over states.
    The US rate for each disease will be the total number of cases divided by the total population.
    Remember to convert to cases per 10,000.
    You will need to filter for !is.na(population) to get all the data.
    Plot each disease in a different color.

library(dplyr)
library(ggplot2)
library(dslabs)
library(RColorBrewer)

data(us_contagious_diseases)

us_contagious_diseases %>% filter(!is.na(population)) %>% 
  group_by(year, disease) %>%
  summarize(rate=sum(count)/sum(population)*10000) %>%
  ggplot(aes(year, rate,color=disease)) + geom_line()

