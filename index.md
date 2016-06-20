---
title       : Boston Red Sox - Actual vs. Expected Wins
author      : Dave Richards
job         : Coursera - Developing Data Products
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---


## The App

![](RedSoxSnip.PNG)

---

## Calculating Expected Wins

We use the Pythagorean Expectation formula, which was invented by baseball writer and statistician Bill James. You can read more about the formula at https://en.wikipedia.org/wiki/Pythagorean_expectation. 

The formula is:  

$$ExpWins = \frac{R^2}{R^2 + RA^2}\ \cdot G$$  

where R = runs scored, RA = runs allowed, and G = games played

---

## Calculating Expected Wins -- example


In 1901, the Red Sox played 138 games, in which they scored 759 runs and allowed 608 runs. Plugging the numbers into the formula, we get:

$$ExpWins = \frac{759^2}{759^2 + 608^2}\ \cdot 138$$ 


```r
round((((759^2) / (759^2 + 608^2)) * 138), 2)
```

```
## [1] 84.06
```

This compares with the Red Sox' actual win total of 79.

---

## Differences Between Expected and Actual Wins

Empirically, this formula correlates fairly well with how baseball teams actually perform. Differences between expected and actual wins might be explained by one or more of these factors:

* statisticians have found this formula to have a fairly routine error, generally about three games off
* luck
* quality of relief pitching
* skill of the manager
* regression towards the mean: teams that win a lot of games tend to be underrepresented by the formula (meaning they "should" have won fewer games), and teams that lose a lot of games tend to be overrepresented (they "should" have won more)

Details at https://en.wikipedia.org/wiki/Pythagorean_expectation

