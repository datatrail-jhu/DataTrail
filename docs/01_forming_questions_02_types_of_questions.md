


# Types of Data Science Questions

The way to start a data analysis project is to start with a question. Asking questions is central to data science. In this chapter we will start to get comfortable with the types of questions that data science can answer.

It's very likely that in a data science project you will start out with one question that will give rise to many more questions!

After you have asked your general question, the next step is to turn it into a data science question. This usually involves making the question more concrete, identifying what type of question you are asking, and identifying the parts of the data that you will use to answer the question.

We will look at a few different types of questions that you might want to answer from data.
There are four classes of data science questions we will talk about.

* **Descriptive** <img src="resources/icons/descriptive.png" width="12%">
The goal of descriptive data science questions is to understand the components of a data set, describe what they are, and explain that description to others who might want to understand the data. This is the simplest type of data analysis. Examples of descriptive data science calculations are the average (also called the mean), variance, maximum, and minimum of the data set.

* **Exploratory** <img src="resources/icons/exploratory.png" width="12%">
The goal of exploratory data science questions is to find unknown relationships between the different variables you have measured in your data set. Exploratory analysis is open ended and designed to find expected or unexpected relationships between different measurements. This step usually requires making a graph to visualize the relationships.

* **Inferential** <img src="resources/icons/inferential.png" width="12%">
The goal of inferential data science questions is to is to use a small sample of data to say something about what would happen if we collected more data. Inferential questions come up because we want to understand the relationships between different variables but it is too expensive or difficult to collect data on every person or object. In this case we can establish there is a relationship between two or more variables based on the small sample, but if we had more data we could be more confident about it.

* **Predictive** <img src="resources/icons/predictive.png" width="12%">
The goal of predictive data science question is to use data from a large collection to predict values for new individuals. This might be predicting what will happen in the future or predicting characteristics that are difficult to measure. Predictive data science is sometimes called machine learning.


![Types of Data Analysis](https://docs.google.com/presentation/d/1VIyLthjLSXikF1euqPNA71cnT_C1kSZhDbIPe8uzg9I/export/png?id=1VIyLthjLSXikF1euqPNA71cnT_C1kSZhDbIPe8uzg9I&pageid=g3ec461ec74_0_22)

The questions we will focus on are the types where we look for relationships between measurements or variables. But in these types of analyses we won't be able to tell anything about what happens if you _change_ one of the variables. To figure out what happens if you change a variable, you need a more advanced type of analysis. These analyses - causal and mechanistic - require data on specific types of problem and collected in special ways. For this class, the primary thing we need to be aware of is that **just because two variables are correlated with each other it doesn't mean that changing one causes a change in the other**.

[One way](http://www.tylervigen.com/spurious-correlations) that people illustrate this idea is to look at data where two variables show a relationship, but are clearly *not* related to each other. For example, in a specific time range, the number of people who drown while falling into a pool is related to the number of films that Nicholas Cage appears in. These two variables are clearly unrelated to each other, but the data seems to show a relationship. We'll discuss more later in this class


![Spurious Correlation](https://docs.google.com/presentation/d/1VIyLthjLSXikF1euqPNA71cnT_C1kSZhDbIPe8uzg9I/export/png?id=1VIyLthjLSXikF1euqPNA71cnT_C1kSZhDbIPe8uzg9I&pageid=g3ec461ec74_0_222)

### Examples of data science questions

Let's begin with some example data science projects, how they are asked, and how they are approached. In each example, we explain the problem as a data science question and guess what sort of analysis is fit for approaching the problem.


#### Example 1: Credit card fraud detection

If you have a credit card, every time you charge something, the bank keeps a record of that charge. This can be useful for you when you want to keep track of your finances. But banks use the information for other purposes as well. If you lose your credit card and someone starts using it to buy things for themselves this is called credit card fraud. By collecting data from everyone, credit card companies are able to predict potential fraudulent transactions before consumers notice anything. So the question is: "Can we predict which credit card charges are fraudulent?".  But this is not a data science question yet. To ask this like a data scientist we might ask, "Can we use the time of the charge, the location of the charge, and the price of the charge to predict whether that charge is fraudulent or not?". Since we are interested in predicting whether a charge is fraud or genuine, this will be a **predictive analysis**.

- **Problem:** Detecting whether credit card charges are fraudulent.
- **Data science question:** Can we use the time of the charge, the location of the charge, and the price of the charge to predict whether that charge is fraudulent or not?
- **Type of analysis:** Predictive analysis

#### Example 2: Analysis of YouTube comments

Any text you can find on the web can be considered to be data. You can use this data to understand how people behave on the web. For example, when companies like YouTube want to understand whether their users are behaving nicely or badly, they might look at the comments they leave. So the question might be, "Are the comments on our platform mostly nice or mostly mean?" To write this in terms of a data science question you might ask, "Are the words that people use in their comments more frequently positive words (great, awesome, nice, useful) or negative words (bad, stupid, lame, awful)?" This is a question you could answer by collecting information on words and labeling them with whether they are nice or mean. This is an example of **descriptive analysis** since once we have the data, the analysis boils down to comparing the number of positive comments to negative comments.

- **Problem:** Understanding whether users are nice or mean on YouTube
- **Data science question:** Are the words that people use in their comments more frequently positive words (great, awesome, nice, useful) or negative words (bad, stupid, lame, awful)?
- **Type of analysis:** Descriptive analysis


#### Example 3: Sesame Street and kids' brain development

Sesame Street is a children's entertainment and educational program. Scientists might be interested in whether watching Sesame Street helps brain development in kids. To turn this into a data science question we need to make it more specific and focused on data. So we might convert this to a data science question like, "Can we compare children who watch Sesame Street and those who don't to see whose test scores are higher?" A complication is that it might be difficult and expensive to get parents to have their children participate in the study. So we might take a small sample of students and measure their test scores and find out whether they watch TV. Since we want to say something about _all_ children, but have only measured data on a few, this would be an **inferential analysis**.  

- **Problem:** Does Sesame Street affect kids' brain development?
- **Data science question:** Is there a relationship between watching Sesame Street and test scores among children?
- **Type of analysis:** Inferential analysis
