431 Assignment 2
================
Thomas E. Love
Due **2017-09-22** at noon. Version: 2017-09-20

-   [Question 1 - When is "more data" not necessarily a good thing?](#question-1---when-is-more-data-not-necessarily-a-good-thing)
-   [Question 2](#question-2)
-   [Question 3](#question-3)
-   [The `LBWunicef` Data, for Questions 4-8](#the-lbwunicef-data-for-questions-4-8)
-   [Question 4](#question-4)
-   [Question 5](#question-5)
-   [Question 6](#question-6)
-   [Question 7](#question-7)
-   [Question 8](#question-8)
-   [Question 9](#question-9)

This assignment should be submitted through [Canvas](https://canvas.case.edu/). We recommend the use of the [YOURNAME-hw\_template.Rmd](https://raw.githubusercontent.com/THOMASELOVE/431homework/master/YOURNAME-hw_template.Rmd) and we suggest you review the [What We'd Ideally See in a Homework Assignment Submission](https://github.com/THOMASELOVE/431homework) for some additional tips on writing your Markdown file and submitting your work. I'll also remind you that spell-check is available in R Studio by hitting F7.

Question 1 - When is "more data" not necessarily a good thing?
==============================================================

Read the Introduction and Chapter 1 of Nate Silver's *The Signal and the Noise*. One possible takeaway, particularly from the Introduction, suggested, for example in a review by Jonah Sinick, might be that increased access to information can do more harm than good.

Tell us about an example in your own field/work/experience where a "surplus" of information made (or makes) it easier for people dealing with a complex system to cherry-pick information that supports their prior positions. What were the implications of your example in terms of lessons that can be learned? If you can connect your example to some of the lessons described in the Chapter 1 discussion of the failure to predict the 2008 catastrophe on the US economy, that would be welcome.

Please feel free to supply as many supporting details as are useful to you in relating the story. An appropriate response to Question 1 will use complete English sentences with proper grammar and syntax, will cite a link or two to a Web URL or other published work, and be 350 ± 150 words long.

Question 2
==========

Please answer **exercise 1.50** from Section 1.9 of the Diez et al. *OpenIntro Stats 3* text, which is described in the [Course Syllabus](https://thomaselove.github.io/431syllabus/). The question we want you to answer is entitled "Mix-and-match" and asks you to describe the distributions in three histograms, then match them to box plots.

Question 3
==========

A study of 100 subjects unfortunately contained 5 people with missing data. This was coded as `99` in the data set. Assume that the true value for the mean is 45, and for the standard deviation is 5.6, with a minimum of 16 and maximum of 65, based on treating these `99` values as if they were `NA`s. If the statistician instead went ahead and analyzed the data as if the `99`s were real, would it make the following parameter estimates *larger*, *smaller* or *stay the same*?

1.  The mode, or most commonly observed value
2.  The median
3.  The mean
4.  The standard deviation
5.  The range

The `LBWunicef` Data, for Questions 4-8
=======================================

I found data (last updated Nov 2014) at [a UNICEF data site](http://data.unicef.org/nutrition/low-birthweight.html), that described the percentage of low birth weight (less than 2,500 grams) infants for a number of nations (actually, counties and territories, but I'll refer to them as nations here) around the world. I then built the `LBWunicef.csv` data set which includes the following elements.

-   `nation` = the nation's name
-   `lbw.pct` = the nation's low birth weight percentage
-   `least.dev` = whether or not the nation is regarded by the United Nations Population Division as one of the "least developed" countries on Earth (note that `least.dev` = 1 if the nation is in the "least developed countries" group and `least.dev` = 0 otherwise.

-   I'll also note that the `gg_qq` and `skew1` functions in the `Love-boost.R` script will be used in our answer sketch, so you might consider using `source("Love-boost.R")` in your code to make those functions available. Remember that you'll have to download the `Love-boost.R` script from the website into the directory in R where you are storing your R project for Assignment 2.
-   The `LBWunicef.csv` file and the `Love-boost.R` script are part of the general Data and Code materials at <https://github.com/THOMASELOVE/431data>

Import the `LBWunicef.csv` file into R Studio, turn it into a tibble, then use that result to answer questions 4-9.

Question 4
==========

How many nations have non-missing low birth weight percentage estimates?

Question 5
==========

Which nations have the three largest low birth weight percentages? Are each of these considered by the UN to be \`\`least developed'' nations or not?

Question 6
==========

Create a histogram of the low birth weight percentages, then superimpose a normal density function with the same mean and standard deviation in red. Based on your plot, is the standard deviation or the inter-quartile range a more appropriate measure of variation in the low birth weight rates? Why?

Question 7
==========

Create a normal Q-Q plot for the low birth weight percentage estimates. Would you say that the data are approximately Normally distributed, or not approximately Normally distributed? Justify your answer by interpreting what you see in your plot, and whatever summary statistics you deem to be useful in making your decision.

Question 8
==========

Display an effective graph comparing the two development groups (least developed nations vs. all other nations) in terms of their percentages of low birth weight births. What conclusions can you draw about the distribution of low birth weight rates across the two development groups? Be sure to label your graph so it stands alone, and also supplement your graph with separate text discussing your conclusions.

Question 9
==========

Generate a "random" sample of 75 observations from a Normal distribution with mean 100 and standard deviation 10 using R. The `rnorm` function is likely to be helpful. Now, display a normal Q-Q plot of these data, using the `ggplot2` package from the `tidyverse`. How well does the Q-Q plot approximate a straight line?

Repeat this task for a second sample of 150 Normally distributed observations, again with a mean of 100 and a standard deviation of 10. Then repeat it again for samples of 25 and 225 Normally distributed observations with a different mean and variance. Which of the four Q-Q plots you have developed better approximates a straight line and what should we expect the relationship of sample size with this phenomenon to be?
