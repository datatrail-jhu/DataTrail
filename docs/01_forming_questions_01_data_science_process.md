

# The Data Science Process

As a data scientist, what steps are involved in answering a question with data? In this course, we aim to frame everything in the context of the data science process.

In the following chapters and courses we will cover each part of this process more in-depth.

### The Parts of a Data Science Project

Data science process generally follow these steps:

The first part of the a data science process is **forming a question**. Sometimes you'll have a dataset in mind that you will explore to form this question, and other times, you will have a question that you will find some data to help you answer.

- **Form a question** - What is the question you hope to answer with data?
- **Get the data** - To answer this question you'll need data!
- **Clean the data** - Datasets are almost never ready to analyze from the get go. As a data scientist, we'll need to do some cleaning and set up steps to get the data where we need it before we can really dig into it.
- **Explore and plot the data** - After your data is clean, you'll want to do some initial exploration. What do these data look like? Plots are a great way to visual your data and start to get an idea of how the data might relate to your initial question.
- **Get stats** - You can use statistics and models to try to use your data to get to the bottom of your question.
- **Share results** - Given everything you are seeing with your data, how do we interpret this? What's our conclusion when it comes to our initial question?

<img src="resources/images/01_forming_questions_01_data_science_process_files/figure-html//114QYFmKuJ2M5E3tlBw8Gwu2xI09tb8gnrKrNkMY9CG4_p.png" title="Data Science process involves" alt="Data Science process involves" width="100%" />

In the upcoming chapters and courses we will further dive into each of these steps!

### A Data Science Project Example

For this example, we're going to use an example analysis from a data scientist named [Hilary Parker](https://hilaryparker.com/about-hilary-parker/). Her work can be found [on her blog](https://hilaryparker.com), and the specific project we'll be working through here is from 2013 and titled ["Hilary: the most poisoned baby name in US history"](https://hilaryparker.com/2013/01/30/hilary-the-most-poisoned-baby-name-in-us-history/). To get the most out of this lesson, click on that link and read through Hilary's post. Once you're done, come on back to this lesson and read through the breakdown of this post.


![Hilary's blog post](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_0)

#### Form a question

When setting out on a data science project, it's always great to have your question well-defined. Additional questions may pop up as you do the analysis, but knowing what you want to answer with your analysis is a really important first step. Hilary Parker's question is included in bold in her post. Highlighting this makes it clear that she's interested in answer the following question:

> Is Hilary/Hillary really the most rapidly poisoned name in recorded American history?

#### Get the data

To answer this question, Hilary collected data from the [Social Security website](https://www.ssa.gov/OACT/babynames/). This dataset included the 1000 most popular baby names from 1880 until 2011.

#### Data Analysis

As explained in the blog post, Hilary was interested in calculating the relative risk for each of the 4,110 different names in her dataset from one year to the next from 1880 to 2011. By hand, this would be a nightmare. Thankfully, by writing code in R, all of which is [publicly available on a site called GitHub](https://github.com/hilaryparker/names), Hilary was able to generate these values for all these names across all these years. It's not important at this point in time to fully understand what a relative risk calculation is (although Hilary does a *great* job breaking it down in her post!), but it is important to know that after getting the data together, the next step is figuring out what you need to do with that data in order to answer your question. For Hilary's question, calculating the relative risk for each name from one year to the next from 1880 to 2011 and looking at the percentage of babies named each name in a particular year would be what she needed to do to answer her question.


![Hilary's GitHub repo for this project](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_32)

#### Clean the data

What you don't see in the blog post is all of the code Hilary wrote to get the data from the [Social Security website](https://www.ssa.gov/OACT/babynames/), to get it in the format she needed to do the analysis, and to generate the figures. As mentioned above, she made all this code [available on GitHub](https://github.com/hilaryparker/names) so that others could see what she did and repeat her steps if they wanted.

#### Explore and plot the data

In addition to this code, data science projects often involve writing a lot of code and generating a lot of figures that aren't included in your final results. This is part of the data science process too. Figuring out *how* to do what you want to do to answer your question of interest is part of the process, doesn't always show up in your final project, and can be very time-consuming.

#### Get stats

That said, given that Hilary now had the necessary values calculated, she began to further analyze the data. The first thing she did was look at the names with the biggest drop in percentage from one year to the next. By this preliminary analysis, Hilary was sixth on the list, meaning there were five other names that had had a single year drop in popularity larger than the one the name "Hilary" experienced from 1992 to 1993.


![Biggest Drop Table](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_36)

In looking at the results of this analysis, the first five years appeared peculiar to Hilary Parker. (It's always good to consider whether or not the results were what you were expecting, from any analysis!) None of them seemed to be names that were popular for long periods of time. To see if this hunch was true, Hilary plotted the percent of babies born each year with each of the names from this table. What she found was that, among these "poisoned" names (names that experienced a big drop from one year to the next in popularity), all of the names other than Hilary became popular all of a sudden and then dropped off in popularity. Hilary Parker was able to figure out why most of these other names became popular, so definitely read that section of her post! The name, Hilary, however, was different. It was popular for a while and then completely dropped off in popularity.


![14 most poisoned names over time](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_47)

To figure out what was specifically going on with the name Hilary, she removed names that became popular for short periods of time before dropping off, and only looked at names that were in the top 1000 for more than 20 years. The results from this analysis definitively show that Hilary had the quickest fall from popularity in 1992 of any female baby name between 1880 and 2011. ("Marian"'s decline was gradual over many years.)


![39 most poisoned names over time, controlling for fads](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_53)

#### Interpret and communicate results

The final step in this data analysis process was, once Hilary Parker had answered her question on her computer, it was time to share it with the world. An important part of any data science project is effectively communicating the results of the project. Hilary did so by writing a wonderful blog post that communicated the results of her analysis, answered the question she set out to answer, and did so in an entertaining way.

Additionally, it's important to note that most projects build off someone else's work. It's *really* important to give those people credit. Hilary accomplishes this by:

* linking to a [blog post](http://stuartbuck.blogspot.com/2003/09/hillary-is-most-poisoned-baby-name-in.html) where someone had asked a similar question previously
* linking to the [Social Security website](https://www.ssa.gov/OACT/babynames/) where she got the data
* linking to a link about where she [learned about web scraping](http://syntaxi.net/2013/01/20/storyboard/)

### What you can build using R

Hilary's work was carried out using the R programming language. Throughout the courses in this series, you'll learn the basics of programming in R, exploring and analyzing data, and how to build reports and web applications that allow you to effectively communicate your results. To give you an example of the types of things that can be built using the R programming and suite of available tools that use R, below are a few examples of the types of things that have been built using the data science process and the R programming language - the types of things that you'll be able to generate by the end of this series of courses.

#### Prediction Risk of Opioid Overdoses in Providence, RI

Masters students at the University of Pennsylvania set out to predict the risk of opioid overdoses in Providence, Rhode Island. They include [details on the data they used, the steps they took to clean their data, their visualization process, and their final results](https://pennmusa.github.io/MUSA_801.io/project_5/index.html). While the details aren't important now, seeing the process and what types of reports can be generated is important. Additionally, they've created a [Shiny App](https://jordanbutz.shinyapps.io/directory/), which is an interactive web application. This means that you can choose what neighborhood in Providence you want to focus on. All of this was built using R programming.


![Prediction of Opioid Overdoses in Providence, RI](https://docs.google.com/presentation/d/1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8/export/png?id=1SNT3SYuWJhjRYx7VmyFKWkuxESEx5THt-mWJ7Mx5Cr8&pageid=g39818b4900_0_93)

### Other Cool Data Science Projects

The following are smaller projects than the example above, but data science projects nonetheless! In each project, the author had a question they wanted to answer and used data to answer that question. They explored, visualized, and analyzed the data. Then, they wrote blog posts to communicate their findings. Take a look to learn more about the topics listed and to see how others work through the data science project process and communicate their results.

* [Predicting movie ratings with IMDb data and R](http://re-design.dimiter.eu/?p=767), by [Dimiter Toshkov](http://re-design.dimiter.eu/)
* [Where to Live in the US](http://www.masalmon.eu/2017/11/16/wheretoliveus/), by [Maelle Salmon](https://masalmon.eu/)
* [Sexual Health Clinics in Toronto](https://sharlagelfand.netlify.com/posts/tidying-toronto-open-data/), by [Sharla Gelfand](https://sharlagelfand.netlify.com/about/)
