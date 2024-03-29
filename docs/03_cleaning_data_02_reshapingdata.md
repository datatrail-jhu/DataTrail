
# Reshaping Data

### Data Formats

Tidy data generally exist in two forms: wide data and long data. Both types of data are used and needed in data analysis, and fortunately, there are tools that can take you from wide-to-long and from long-to-wide. This makes it easy to work with any tidy data set. We'll discuss the basics of what wide and long data are and how to go back and forth between the two in R. Getting data into the right format will be crucial later when summarizing data and visualizing it.

To help you visualize data as its being reshaped, we recommend you play around with the [TidyDataTutor](https://tidydatatutor.com/vis.html).

#### Wide Data

Wide data has a column for each variable and a row for each observation. Data are often entered and stored in this manner. This is because wide data are often easy to understand at a glance. For example, this is a wide data set:


![Wide dataset](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g2bfdb07292_0_151)

This is a dataset we've looked at in a previous lesson. As discussed previously, it's a rectangular and tidy dataset. Now, we can also state that it is a wide dataset. Here you can clearly see what measurements were taken for each individual and can get a sense of how many individuals are contained in the dataset.

Specifically, each individual is in a different row with each variable in a different column. At a glance we can quickly see that we have information about four different people and that each person was measured in four different ways.

#### Long Data

Long data, on the other hand, has one column indicating the type of variable contained in that row and then a separate row for the value for that variable. Each row contains a single observation for a single variable.  Below is an example of a long data set:


![Long dataset](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g38bb68a532_0_0)

This long dataset includes the exact same information as the previous wide dataset; it is just stored differently. It's harder to see visually how many different measurements were taken and on how many different people, but the same information is there.

While long data formats are less readable than wide data at a glance, they are a lot easier to work with during analysis. Most of the tools we'll be working with use long data. Thus, to go from how data are often stored (wide) to working with the data during analysis (long), we'll need to understand what tools are needed to do this and how to work with them.

### R Packages

Converting your data from wide-to-long or from long-to-wide data formats is referred to as **reshaping** your data and you can do this with the [tidyr](https://tidyr.tidyverse.org/) package. As with most helpful packages in R, there is more functionality than what is discussed here, so feel free to explore the additional resources at the bottom to learn even more.


![Reshaping data](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g38bb68a532_0_13)

For these examples, we'll work with the [`relig_income` dataset available in tidyr](https://tidyr.tidyverse.org/reference/relig_income.html). The data in this dataset includes the income ranges and religions from the Pew religion and income survey.

We can see the first few lines of this dataset using the following code:


```r
library(tidyr)

head(relig_income)
```

```
## # A tibble: 6 × 11
##   religion  `<$10k` `$10-20k` `$20-30k` `$30-40k` `$40-50k` `$50-75k` `$75-100k`
##   <chr>       <dbl>     <dbl>     <dbl>     <dbl>     <dbl>     <dbl>      <dbl>
## 1 Agnostic       27        34        60        81        76       137        122
## 2 Atheist        12        27        37        52        35        70         73
## 3 Buddhist       27        21        30        34        33        58         62
## 4 Catholic      418       617       732       670       638      1116        949
## 5 Don’t kn…      15        14        15        11        10        35         21
## 6 Evangeli…     575       869      1064       982       881      1486        949
## # ℹ 3 more variables: `$100-150k` <dbl>, `>150k` <dbl>,
## #   `Don't know/refused` <dbl>
```

Again, wide data are easy to decipher at a glance. We can see that we have different income levels but in reality, many of those columns contain the same variable (income) so these data are not tidy.

#### tidyr

Within tidyr, there are two functions to help you reshape your data.

* `pivot_longer()`: go from wide data to long data
* `pivot_wider()`: go from long data to wide data

To get started, you'll need to be sure that the `tidyr` package is installed and loaded into your RStudio session.

```r
install.packages("tidyr")
library(tidyr)
```

##### pivot_longer()

As data are often stored in wide formats, you'll likely use `pivot_longer()` a lot more frequently than you'll use `pivot_wider()`. This will allow you to get the data into a long format that will be easy to use for analysis.

In `tidyr`, `gather()` will take the `relig_income` dataset from wide to long, putting each column name into the first column and each corresponding value into the second column. Here, the first column will be called `income`. The second column will still be `count`.

The first argument in pivot_longer() tells which columns you'd like to pivot. In this case, we want to pivot all columns except the religion column

Let's take a look at this dataset to start:

```r
head(relig_income)
```

```
## # A tibble: 6 × 11
##   religion  `<$10k` `$10-20k` `$20-30k` `$30-40k` `$40-50k` `$50-75k` `$75-100k`
##   <chr>       <dbl>     <dbl>     <dbl>     <dbl>     <dbl>     <dbl>      <dbl>
## 1 Agnostic       27        34        60        81        76       137        122
## 2 Atheist        12        27        37        52        35        70         73
## 3 Buddhist       27        21        30        34        33        58         62
## 4 Catholic      418       617       732       670       638      1116        949
## 5 Don’t kn…      15        14        15        11        10        35         21
## 6 Evangeli…     575       869      1064       982       881      1486        949
## # ℹ 3 more variables: `$100-150k` <dbl>, `>150k` <dbl>,
## #   `Don't know/refused` <dbl>
```

Now let's `pivot_longer` and take a look again:


```r
## use pivot_longer() to reshape from wide to long
long_df <- relig_income %>%
  pivot_longer(!religion, names_to = "income", values_to = "count")

## take a look at first few rows of long data
head(long_df)
```

```
## # A tibble: 6 × 3
##   religion income  count
##   <chr>    <chr>   <dbl>
## 1 Agnostic <$10k      27
## 2 Agnostic $10-20k    34
## 3 Agnostic $20-30k    60
## 4 Agnostic $30-40k    81
## 5 Agnostic $40-50k    76
## 6 Agnostic $50-75k   137
```


![gather dataset](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g38bb68a532_0_205)

We can change what columns we want to include a different column select helpers:
See here for all about [select helpers](https://dplyr.tidyverse.org/reference/select.html).


```r
## use pivot_longer() to reshape from wide to long
relig_income %>%
  pivot_longer(contains("$"), names_to = "income", values_to = "count")
```

```
## # A tibble: 144 × 5
##    religion `>150k` `Don't know/refused` income    count
##    <chr>      <dbl>                <dbl> <chr>     <dbl>
##  1 Agnostic      84                   96 <$10k        27
##  2 Agnostic      84                   96 $10-20k      34
##  3 Agnostic      84                   96 $20-30k      60
##  4 Agnostic      84                   96 $30-40k      81
##  5 Agnostic      84                   96 $40-50k      76
##  6 Agnostic      84                   96 $50-75k     137
##  7 Agnostic      84                   96 $75-100k    122
##  8 Agnostic      84                   96 $100-150k   109
##  9 Atheist       74                   76 <$10k        12
## 10 Atheist       74                   76 $10-20k      27
## # ℹ 134 more rows
```

We can change the `names_to` and `values_to` arguments if we want the resulting column names to be different.

##### pivot_wider()

To return your long data back to its original form, you can use `pivot_wider()`. Here you specify two columns: the column that contains the names of what your wide data columns should be (`names_from`) and the column that contains the values that should go in these columns (`values_from`). The data frame resulting from `pivot_wider()` will have the original information back in the wide format (again, the columns will be in a different order). But, we'll discuss how to rearrange data in the next lesson!

```r
## use pivot_wider() to reshape from wide to long
wider_data <- pivot_wider(long_df, names_from = "income", values_from = "count")

## take a look at the wider data
head(wider_data)
```

## Transposing data

One more transformation you may need to do, has a function in base R to do it.
You may find you need your rows to be columns and your columns to be rows. In other words, you need to transpose your data table.

To do this, you can use the `t()` function. But! Note that although the `t()` function can be given a data frame, it will return a matrix. This means if you want your data frame to stay a data frame you need to follow your `t()` function with a `as.data.frame()`. This might look like this:


```r
# We need to load this so we can use %>%
library(magrittr)
```

```
## 
## Attaching package: 'magrittr'
```

```
## The following object is masked from 'package:tidyr':
## 
##     extract
```

```r
iris_transposed <- iris %>%
  t() %>%
  as.data.frame()
```

Our original `iris` data frame has 150 rows and 4 columns.


```r
dim(iris)
```

```
## [1] 150   5
```

Whereas our transposed `iris` data frame has 4 rows and 150 columns.


```r
dim(iris_transposed)
```

```
## [1]   5 150
```

The information in both `iris` and `iris_transposed` is the same, it's just in a different shape.


### Additional Resources

* [TidyDataTutor](https://tidydatatutor.com/vis.html)
* [tidyr](https://tidyr.tidyverse.org/), part of the [tidyverse](https://www.tidyverse.org/) and developed by [Hadley Wickham](http://hadley.nz/) and [Lionel Henry](https://github.com/lionel-)
* [tidyr tutorial](https://blog.rstudio.com/2014/07/22/introducing-tidyr/) by [Hadley Wickham](http://hadley.nz/)
* [tidyr cheatsheet](https://github.com/rstudio/cheatsheets/blob/main/tidyr.pdf)
