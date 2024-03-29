
# Joining Data

Often times, you may find yourself with two datasets that contain overlapping sets of information. In many cases, it may make the most sense to combine multiple datasets into one datasets for easier handling and reading.

In this chapter, we will discuss the different methods for combining multiple datasets.

## dplyr join family of functions

There are different kinds of joins - let's discuss what they do.

Let's say you have to data frames. One is called `df_a` and the other, `df_b`.
We can create these data frames using this code:


```r
df_a <- data.frame(sample = c("A", "B", "C", "D"),
                   number = c(2, 4, 4.4, 3.1))
df_b <- data.frame(sample = c("A", "B", "E", "F"),
                   color = c("blue", "blue", "red", "green"))
```

Let's print these toy tables out to see what they look like.
Here's `df_a`.

```r
df_a
```

```
##   sample number
## 1      A    2.0
## 2      B    4.0
## 3      C    4.4
## 4      D    3.1
```
And here's `df_b`

```r
df_b
```

```
##   sample color
## 1      A  blue
## 2      B  blue
## 3      E   red
## 4      F green
```

Notice that both table contain information about samples, `A` and `B` but each also contain information that the other table doesn't have.

Join functions can be great for situation like these to make one bigger table that contains the information you want to use.


`join` family of functions include these (which we will go over in this chapter):   

- `inner_join()`: includes only rows that have matches in `df_a` and `df_b`.
- `left_join()`: includes all rows in `df_a` but not any of `df_b` that doesn't have a match to `df_a`.
- `right_join()`: includes all rows in `df_b` but not any of `df_a` that doesn't have a match to `df_b`.
- `full_join()`: includes all rows in of `df_a` and `df_b`, regardless if they have matches in the other data frame or not.

#### inner_join()

First, let's try an `inner_join()`. This will **only** keep the `rows`s common to both datasets.

Note that we can try to have the function guess what column we would like to match the rows by, OR we should probably use the argument `by` to tell the function which column should be used as a `key`.

In our example above, we want to use the `sample` column to match rows by. Aka the sample column is what has the IDs that indicate what rows are related to which in the two data data frames.


```r
# Need to load in these functions first before we can use them
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
inner_join(df_a, df_b, by = "sample")
```

```
##   sample number color
## 1      A      2  blue
## 2      B      4  blue
```

Notice that now we only have the rows `A` and `B` because those were in both datasets. This is how inner_join() works. If we don't like dropping all that other data, we might want to use a different join function.

#### left_join()

Let's say we mostly care about the data in `df_a` and want to keep all that data, but want to join data from `df_b` only if there are matches. This is a great case for a `left_join`.

Let's try it:

```r
left_join(df_a, df_b, by = "sample")
```

```
##   sample number color
## 1      A    2.0  blue
## 2      B    4.0  blue
## 3      C    4.4  <NA>
## 4      D    3.1  <NA>
```

See that now we have all the rows of `df_a` but an added column, `color`,  from `df_b`. You'll see that the way the join deals with this is that it puts `NA`s for the rows it doesn't have information for `color` -- these will be the rows that are in `df_b` but not in `df_a`.

#### right_join()

What if instead we mostly care about `df_b`'s data but are wanting to add on `df_a`'s data ONLY if it matches to `df_b`? This is where we can do a `right_join()`


```r
right_join(df_a, df_b, by = "sample")
```

```
##   sample number color
## 1      A      2  blue
## 2      B      4  blue
## 3      E     NA   red
## 4      F     NA green
```

Note that the above is also equivalent to a `left_join()` if we switch the order that we are providing the data frames. Aka if we list `df_b` first and `df_a` second.


```r
all.equal(
right_join(df_a, df_b, by = "sample"),

# A left join, where we have df_b listed first
left_join(df_b, df_a, by = "sample")
)
```

```
## [1] "Names: 2 string mismatches"                          
## [2] "Component 2: Modes: numeric, character"              
## [3] "Component 2: target is numeric, current is character"
## [4] "Component 3: Modes: character, numeric"              
## [5] "Component 3: target is character, current is numeric"
```

In summary, the left or right in the function name just refers to which data frame is listed first (on the left) or second (on the right).

#### full_join()

In the situation where we want to keep all data from both datasets, we'll want to use a `full_join`.


```r
full_join(df_a, df_b, by = "sample")
```

```
##   sample number color
## 1      A    2.0  blue
## 2      B    4.0  blue
## 3      C    4.4  <NA>
## 4      D    3.1  <NA>
## 5      E     NA   red
## 6      F     NA green
```

This is the biggest data frame of the joins, and will always be that way, because we have not dropped any data. Instead we've just fill in `NA`s where we don't have information after we've combined `df_a` and `df_b`.

Having a bunch of `NA`s may be okay depending on what you are hoping to do with these data. But it goes back to the idea that a lot of data science decisions, including those about tidying data, will be largely dependent on the context and goals of what you are working on.

But, to make these decisions, you will need to be aware of what your data look like so: Always be looking at your data!

### Row binding

In some cases it may be more appropriate to merely stack rows on top of each other instead of doing a join. Let's say our datasets have most of the same columns but different rows.

![](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g1483518923e_0_0)

To do this, we could use a row bind. Look up `?dplyr::bind_rows` to see this function's help page. Let's use this function.


```r
bind_rows(df_a, df_b)
```

```
##   sample number color
## 1      A    2.0  <NA>
## 2      B    4.0  <NA>
## 3      C    4.4  <NA>
## 4      D    3.1  <NA>
## 5      A     NA  blue
## 6      B     NA  blue
## 7      E     NA   red
## 8      F     NA green
```

If we want to keep track of which row of data came from where, we should use the `.id` argument to specify a column name where this info will be kept.


```r
bind_rows(df_a, df_b, .id = "dataset")
```

```
##   dataset sample number color
## 1       1      A    2.0  <NA>
## 2       1      B    4.0  <NA>
## 3       1      C    4.4  <NA>
## 4       1      D    3.1  <NA>
## 5       2      A     NA  blue
## 6       2      B     NA  blue
## 7       2      E     NA   red
## 8       2      F     NA green
```

Note that the `dataset` column is not super easy to understand in that it has `"1"` and `"2"` when it really means `df_a` and `df_b`. So to fix this, we can specify these names of these dataframes. Look at the examples in the documentation and try to do this so that the `id` column says `ffood` and `ffood_may` instead of `"1"` and `"2"`.


```r
bind_rows("df_a" = df_a, "df_b" = df_b, .id = "dataset")
```

```
##   dataset sample number color
## 1    df_a      A    2.0  <NA>
## 2    df_a      B    4.0  <NA>
## 3    df_a      C    4.4  <NA>
## 4    df_a      D    3.1  <NA>
## 5    df_b      A     NA  blue
## 6    df_b      B     NA  blue
## 7    df_b      E     NA   red
## 8    df_b      F     NA green
```

### Column binding

Let's say we have information about the same rows, but different variables. This would be a good use of the `dplyr::bind_cols()`

![](https://docs.google.com/presentation/d/14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI/export/png?id=14msuN3MbQE6BSIaNu2ipv1-5ypgvWlxsGwn3jmpFyAI&pageid=g1483518923e_0_6)

For this example, we will need a different dataset. We need two datasets that represent the same cases (or samples). Note that when we make `df_c` below, we know that the samples are the same in both datasets and that they are in the same order.


```r
df_a <- data.frame(sample = c("A", "B", "C", "D"),
                   number = c(2, 4, 4.4, 3.1))
df_c <- data.frame(sample = c("A", "B", "C", "D"),
                   animal = c("dog", "cat", "bird", "snake"))
```

Before we merge these two datasets, we would want to make absolutely sure that our samples are in the same order in each. Otherwise we will be combining data in a way that doesn't make sense and could throw off the rest of our analysis! (Eeek!)

We can use our friend, the function `all.equal()` to check that we are working with the same samples and in the same order.


```r
all.equal(df_a$sample, df_c$sample)
```

```
## [1] TRUE
```

Now we know we can bind_cols() of `df_a` and `df_c` safely.


```r
bind_cols(df_a, df_c)
```

```
## New names:
```

```
##   sample...1 number sample...3 animal
## 1          A    2.0          A    dog
## 2          B    4.0          B    cat
## 3          C    4.4          C   bird
## 4          D    3.1          D  snake
```

Note that because our `sample` columns are named the same thing in both datasets, they've now been renamed to `sample...1` and `sample...3`. But this isn't super helpful or descriptive. We will probably want to use `dplyr::rename()` to make these names more informative OR since we've confirmed that they contain identical information, its probably best we drop one of them using `dplyr::select()`.


```r
bind_cols(df_a, df_c) %>%
  rename(sample = sample...1) %>%
  select(-sample...3)
```

```
## New names:
```

```
##   sample number animal
## 1      A    2.0    dog
## 2      B    4.0    cat
## 3      C    4.4   bird
## 4      D    3.1  snake
```

Now we have all these data in one dataset! Now you have all of these different tools in your tool belt to combine data frames that contain related information!
