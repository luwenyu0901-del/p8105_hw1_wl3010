Homework 1
================
WL3010
2025-09-20

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax
for authoring HTML, PDF, and MS Word documents. For more details on
using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that
includes both content as well as the output of any embedded R code
chunks within the document. You can embed an R code chunk like this:

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Including Plots

You can also embed plots, for example:

![](Homework1_wl3010_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.

## Problem 1

We load the dataset and make a scatterplot:

``` r
library(moderndive)
library(ggplot2)

data("early_january_weather")

p <- ggplot(early_january_weather, aes(x = time_hour, y = temp, color = humid)) +
  geom_point(alpha = 0.6) +
  labs(title = "Temperature vs Time (colored by Humidity)",
       x = "Hour",
       y = "Temperature (F)",
       color = "Humidity") +
  theme_minimal()

p
```

![](Homework1_wl3010_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

``` r
# save plot to file
ggsave("scatterplot_temp_time.png", plot = p, width = 7, height = 5)
```
