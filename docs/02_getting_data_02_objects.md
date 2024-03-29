


# Objects in R

### What is an object?

An object in R is something that contains information. In R there are a number of basic **classes** and **types** of objects.

- Classes - tell us what kind of data is being stored? Is it a number? A category? A word?

- Types - tell us what shape the data are being stored as. Is it a table? A series of items together (called a vector)? Or something with a different structure all together.

### Storing objects

In R, as with all programming languages, it is important to be able to store objects that we create so that we can use them in later code. The process of storing an object is called **assignment**, and it entails giving an object a name. For example, the following code creates an object called `min_age` and stores inside that object the value 21. It is equivalent to saying that `min_age` *is equal to* 21.

```r
min_age <- 21
```

The `<-` operator is called the assignment operator. After you run this code in R, you will see the object `min_age` show up in your **Environment** panel.

![Assignment](https://docs.google.com/presentation/d/1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc/export/png?id=1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc&pageid=g313d649efe_0_22)

Now if we tell R `min_age` it will print back to us the number `21`.

Having this minimum age variable stored in an object can be useful later if we have data where we only want to keep individuals who exceed this minimum age.

### Printing objects

Often we will want to print the contents of an object to see the information it contains. We can do this by clicking in the Console in Posit Cloud (bottom left corner). The **R prompt** is indicated by the `>` in the Console. This indicates that R is ready to accept a command from you. If we simply enter the number 21 at the R prompt, the 21 object will be printed, but you will not see an object come up under the **Environment** pane (top right corner).

```text
> 21
[1] 21

> min_age <- 21
> min_age
[1] 21
```

The 1 in square brackets that gets displayed in the printed output is simply an index that is provided for convenience of reading in case the object contains several values. It indicates that the number 21 is the first number in this object. It also happens to be the only number in this object.

Throughout this curriculum, when we display code without the `>` indicating that we are not at the R prompt in the Console, we are emphasizing only the R command. When we display code with the `>` indicating that we are at the R prompt in the Console, we want to emphasize the commands and how the output is displayed on the screen.

#### Classes of objects

Five classes that you'll be working with commonly are:

- Character - e.g. `"sharon"` `"marcus"`
- Integer - e.g. `1`, `4` (whole numbers)
- Numeric - e.g. `1.2`, `3.4`, `4`
- Logical - only two options: `TRUE` or `FALSE`.
- Factor - `red`, `red`, `blue`, `yellow` (categories that could be repeated).

We will describe each of these classes in more detail but first, why are these important anyway?

#### Why are classes important?

Let's discuss an example.

If we asked: "What is `Blue` divided by `2` equal?" You would rightly tell us that question doesn't even make sense and you can't answer it.

But if we asked: "What is `4` divided by `2` equal?", then you could easily tell us  `4/2 = 2`.
In the same way, R will throw errors at us if we ask it nonsensical questions or things that its not built to do.

Because of this, we need to keep an eye on what kind of data classes we have, and what kinds of things we are asking R to do to make sure that those things make sense together.

### Character

Character objects in R can be created by surrounding a string in either double quotes or single quotes as in the following two examples.

"This is a character object."

'This is also a character object.'

The example below shows how to store the above sentence character object in an object named `my_char`. `my_char` is a character vector of length 1.

```r
my_char <- "This is a character object."
```

We can create a character vector named `my_char_vec` with multiple character objects using the **concatenate** function, `c()`. While we'll discuss functions more in later lessons, the word concatenate means to link things together in a series, so this function links pieces of information together:

```r
my_char_vec <- c("char object 1", "char object 2")
```

This character vector contains two different pieces of information. In R, the number of pieces of information in a vector is referred to as that vectors length. Thus, this vector is of length 2.

### Integer

Integers are whole numbers, such as 1, 23, or 1000.  1.2 is not an integer, as it contains a fraction of a number. Integer objects in R can be created by specifying an integer number followed by the letter "L". The following creates an integer object called `num` and stores the value 1.

```r
num <- 1L
```

Without the letter "L", the number will be recognized as a more general, numeric object (discussed below). We can create an integer vector with multiple items using the `c` function, the concatenation function. The following creates an integer vector of length 3 with the numbers 1, 10, and 3.

```r
num_vec <- c(1L, 10L, 3L)
```

We can also create an integer vector with the colon operator. The colon operator specifies to include all numbers between the value before the colon and the value after the colon. The following command creates an integer vector with the numbers 2, 3, 4, and 5.

```r
num_vec2 <- 2:5
```

If we create longer vectors and print the output, we can see the use of having the square bracket indices at the beginning of the lines of the printed output. In this last example, we see that 4 is the first number in the vector, and 12 is the ninth number in the vector, as specified by the 9 in brackets to start the second line of output.

```text
> 4:16
 [1]  4  5  6  7  8  9 10 11
 [9] 12 13 14 15 16
```

### Numeric

Numeric objects in R represent real numbers and are created by simply entering a number. Thus, while 1.2 is not an integer, it is a real number. Thus 1.2 could be stored as a numeric but not an integer.

```r
num1 <- 1
num2 <- 1.2
```

We can create a numeric vector with multiple items using the c function.

```r
num_vec <- c(1.2, 9.8)
```

As discussed previously, we can also use R as calculator. At the prompt, we can enter mathematical expressions without assignment to display the results as a calculator would. The **operators** for addition, subtraction, multiplication, division, and exponentiation in R are `+`, `-`, `*`, `/`, and `^` respectively.

```text
> 1+5
[1] 6
> 2-3
[1] -1
> 4*2
[1] 8
> 4/5
[1] 0.8
> 3^2
[1] 9
```

### Logical

Logical objects in R represent true or false conditions and can be created by typing "TRUE" or "FALSE".

```r
check_condition <- TRUE
check_condition <- FALSE
```

We can create a logical vector with multiple items using the c function.

```r
check_condition <- c(TRUE, TRUE, FALSE)
```

### Factor

Factor objects contain information for categorical variables (e.g. color, shape), where there are a number of possible values the object can take, but these values are limited. For example, a categorical variable could include the colors of the rainbow. Here, values could be red, orange, yellow, green, blue, indigo, or violet. Thus, values could be one of seven different colors, but the categorical variable is limited to one of these seven values.

To simplify this example and make factors explicitly clear, the following `colors` object is a character vector containing five pieces of color information. There are only two unique colors present: red and blue. These unique colors are called the **levels** of a factor.

```r
colors <- c("red", "red", "blue", "red", "blue")
```

To create a factor object out of this character vector we can use the `factor` function or the `as.factor` function. Let's try both and look at the objects created.

```text
> colors_factor1 <- factor(colors, levels = c("red", "blue"))
> colors_factor1
[1] red  red  blue red  blue
Levels: red blue
> colors_factor2 <- as.factor(colors)
> colors_factor2
[1] red  red  blue red  blue
Levels: blue red
```

When we used the `factor` function we also specified the levels to be red and blue. The order of the levels we specified is important: first red, then blue. We can see that when we print this object the levels are listed in the order we specified. A quick way to create a factor object is with the coercion function `as.factor`. When we print this object, the levels are opposite to what we specified when we used the `factor` function because by default, the levels are specified in alphabetical order. Here the first level is blue and the second is red. The ordering of levels will be important in future courses when we cover data tidying, plotting, and statistical modeling.

One last topic to cover with factors is labeling. We can control the displayed labels of a factor with another option with the `factor` function. This need often arises if we want to create a factor object from an integer object or from a character object with labels that we don't like. In the example below, we see that we originally had ozone information encoded with integers. When we use the `factor` function to make a corresponding factor object, we specify both the unique levels present in the integer object and the desired labels with a character vector. The order of the specified levels should correspond to the order of the specified labels. The two examples, `ozone_factor` and `ozone_factor2`, create the same labeling of the original integer vector, but the order of the levels is different between the two approaches. In the first approach, the first level is low, the second is medium, and the third is high, which is the most natural ordering. In the second approach, the first level is medium, the second is low, and the third is high.

```
> ozone_levels <- c(1,2,1,3,1,1)
> ozone_factor <- factor(ozone_levels, levels = 1:3, labels = c("low", "medium", "high"))
> ozone_factor
[1] low    medium low    high   low    low   
Levels: low medium high
> ozone_factor2 <- factor(ozone_levels, levels = c(2,1,3), labels = c("medium", "low", "high"))
> ozone_factor2
[1] low    medium low    high   low    low   
Levels: medium low high
```

### Data frames

Now that we've covered common basic data classes, we will now discuss data frames. Data frames are a more complex data type than the simple vectors than we've seen so far. Data frames organize data into a rectangular format where each column corresponds to a single variable and each row corresponds to an observation. So a row of a data frame contains an observation's values for all variables. An example of a data frame is shown below:


![Data frame example](https://docs.google.com/presentation/d/1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc/export/png?id=1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc&pageid=g313d649efe_0_38)

We see along the columns different variables related to car properties, and each row gives information on those properties for a particular car model. Every column in a data frame is a simple vector of values all from the same class. Most often, the data that we work with can be represented with data frames.

You will learn more about working with data frames in subsequent chapters.

### Missing values

The last topic that we should discuss in our introduction to R objects is missing values. During nearly any type of data collection, there is information missing for one or more variables. Thus, it is important to understand how R handles missing values. Most missing values that you will deal with are encoded with `NA` in R. Below are some examples of creating objects of the various basic types we discussed above that contain missing values.

```text
> char_vec <- c(NA, "two", "four")
> char_vec
[1] NA     "two"  "four"
> num_vec <- c(1L, 10L, NA, 3L)
> num_vec
[1]  1 10 NA  3
> num_vec <- c(1.2, 9.8, NA)
> num_vec
[1] 1.2 9.8  NA
> logi_vec <- c(TRUE, NA, FALSE, FALSE)
> logi_vec
[1]  TRUE    NA FALSE FALSE
> factor_vec <- as.factor(c(NA, "apple", "banana"))
> factor_vec
[1] <NA>   apple  banana
Levels: apple banana
```

Another missing value that can arise in R is `NaN` which stands for "not a number." This can arise in mathematical calculations, such as 0 divided by 0.

```text
> 0/0
[1] NaN
```

### Determining the class and shape of an object

In this lesson so far we have discussed how to create the five main classes of objects in R; however, we haven't yet described how to determine the class of an object once its been stored. To do so, there are three different strategies we'll show you.

1) You can use the function `class()` and specify the class of the object within the parentheses:

```
> min_age <- 21
> class(min_age)
[1] "numeric"

> min_age <- 21L
> class(min_age)
[1] "integer"

> colors <- c("red", "red", "blue", "red", "blue")
> class(colors)
[1] "character"

> colors_factor1 <- factor(colors, levels = c("red", "blue"))
> class(colors_factor1)
[1] "factor"
```

As you can see, the class of the object specified within the parentheses is the class of that object.

2) You can use a function `str()` which will tell you its structure. This will tell you more about the shape of an object, how long or wide it is, etc.

```
str(colors)
> chr [1:5] "red" "red" "blue" "red" ...
```

3) Lastly, you can always look at your `Environment` panel and sometimes click on an object to see more about it. This strategy doesn't require you to run any command, but sometimes it won't have information that using `str()` or `class()` would tell you.


#### Types of objects

We store these different classes of objects in different ways. The ways this information is stored is referred to as the **type** of object.

When talking about objects in R, it may be helpful to think of *actual* objects in every day life for comparison. For example, think of three objects: a bucket, a pot you would cook with, and a backpack. These three objects are clearly designed for and carry out different purposes. The bucket may be used to carry water to clean your floor, the pot to cook pasta, and the backpack to carry notebooks, but, we can agree that they are all objects, just different *types* of objects. The water, pasta, and notebooks would be the information contained in the object. In this real-life example, the "class" of the information may be "liquid", "food", and "paper".

![Objects in real-life analogy](https://docs.google.com/presentation/d/1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc/export/png?id=1Q47qnIkVzE-JzCEE5Lm54P6yqReg09QJdr7kiFyCbGc&pageid=g3b0072ef38_0_0)

The simplest *type* of object in R is called a **vector**, which is an object that can contain multiple items. Generally, each individual vector can only contain objects of the same class, but a certain type of vector, called a **list**, can contain objects of different classes. You will learn about lists in a later lesson.

For now, it's not important to understand the details of that last paragraph, but it *is* important to know that there are **different types** of objects and that these objects each hold information of a specific **class**.

### Summary

In this lesson, we've discussed that within R information can be assigned to objects. We've covered the five main classes of objects in R and have started to touch on the different types of objects in R, but will discuss this in greater detail in later lessons in this course. We've discussed how to create each class of object in R as well as each class' unique properties. Finally, we discussed how to  determine the class of an object in R using the function `class()`.
