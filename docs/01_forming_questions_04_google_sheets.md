


# Google Documents

There are two types of Google Documents we will discuss:
- Google Sheets - for holding data
- Google Docs - for writing up non-code documents 

## Google Sheets

Google Sheets is a free, online spreadsheet program. If you're familiar with Excel, it is similar to Excel. If you are unfamiliar with Excel, that's ok! We'll go through everything you need to know to get started on the project here. And, later in the program, we will go into more details to get you fully comfortable working with Google Sheets. As for right now, just know that when you have data that you want to input into a spreadsheet, Google Sheets is an ok place to start. Google Sheets is also great because you never have to worry about saving your work. If you are online, Google Sheets automatically saves your work.

### What is a spreadsheet?

A spreadsheet is a type of document where data are stored in rows and columns of a grid. Each square is referred to as a 'cell' in the spreadsheet. In Google Sheets (and many other spreadsheet programs like Excel), the rows are numbered (like 1,2,3,...) and the columns are labeled with capital letters (like A, B, C,...).


![spreadsheet](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2bfdb07292_0_151)

If you want to talk about a specific spot on the grid you can use the number and letter corresponding to that point. For example, A2 specifies the data in cell in the first column (A) and second row (2) of the spreadsheet.


![spreadsheet position](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f5ce65ab5_0_7)

When you are working with data in a spreadsheet you can type directly into the spreadsheet. It is important to make sure you double check all the numbers you type since there isn't a good way to "spellcheck" your work when you are editing a spreadsheet.

We will talk a lot more in future courses about how to organize data that you have collected. Mostly we will want to collect ["tidy data"](https://en.wikipedia.org/wiki/Tidy_data) which is data that has

1. Each type of data in one column.
2. Each data point in one row.
3. One spreadsheet for each "kind" of data.
4. If you have more than one spreadsheet, they should include a column in the table that allows them to be linked.

Here we are only collecting one "kind" of data - just data on books. The columns will be different types of information about the books. We will collect information on the name of the book, the number of sales of that book, the minimum price of the book, and the suggested price of the book. Each of those will be in a separate column. Then, for each book, we will make a new row with the data for that book.

Remember we are collecting information on the bestselling books from the last week on Leanpub. You can find the list of bestsellers here: https://leanpub.com/bookstore. Remember that if you click on the image of one book you will get something that looks like this.


![Powershell 101 landing page](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2ded52d8f0_0_4)


### Setting up your spreadsheet

When we collect the information we will use the Google Sheets software to store it for us. You will need to open up another web browser. You can do this by holding down the key _ctrl_ and pressing _t_. This will open up a new tab. Leave this page open and type go to Google Sheets by navigating to the website https://docs.google.com/spreadsheets/ in the new tab. You will see something like this.


![Google sheets home](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_0)

Now click on the big plus sign and you will get a new spreadsheet that will look like this.


![Untitled sheet](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_6)

If you click on the words _"Untitled Spreadsheet"_ you can rename the spreadsheet. Type in the words _"leanpub\_data"_ to change the name of your spreadsheet. You should now have a spreadsheet that looks like this.


![leanpub_data sheet](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_10)

We are almost done setting up the spreadsheet, now we just need to label the different kinds of data we are going to collect. Start by clicking on the upper left hand cell (A1) and type "title". This will be the column where we are going to store information on the title of the book.


![leanpub_data sheet with title](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_15)

Then move one cell to the right, click and type "readers". This will be where we will store how many readers a book has. Move one more cell to the right type "suggested" and then one more cell and type "minimum". Make sure your column names are not capitalized.

![leanpub_data sheet with headers](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_27)

### Collecting data

Now you are all set to start collecting data! To do this open another new tab by holding _ctrl_ and pressing _t_, then go to the webpage: https://leanpub.com/bookstore. Click on the book and write the title, number of readers, suggested, and minimum prices on a row in the spreadsheet tab. When you are doing this make sure that:

* There are no commas in numbers. Just leave them out. So don't write "1,036" write "1036" instead.
* You don't put dollar signs for the price, just include the number like "7.99."
* If a book's minimum price is free, enter "0" in the cell.
* If the book has no readers, put "0" in the cell.
* If the book's author opted not to include how many readers their book has, put "NA" in the "readers" column for that book.

So for me, since the first book is "PowerShell 101" after getting the data for the first book my spreadsheet will look like this.


![First row of data for project](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f6cf370b2_0_33)

Continue this process, entering each book into a new row. Collect information on ten or twenty books. One book for every row. At the end you should have a data set that looks something like this. But yours will have different numbers and names in it.


![First complete data set](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2ded52d8f0_0_82)

### Checking your data

Now that you've entered your data into the Google Sheet, we want to check for a few possible issues before moving on to make sure the data are formatted correctly. Double to make sure the following are true for the data in your spreadsheet:

1. You have at least 11 rows with reader and minimum price information (one header row and at least 10 books included - if you have NAs anywhere, you'll want more than 11 books)
2. Your dollar amounts do NOT have dollar signs next to them.
3. Your number of readers does not include any commas.
4. If a book's minimum price is FREE, you have put the number 0 in the cell, rather than "FREE"


![Checking your data](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g324d81a498_0_28)

This is great! You now have a question you want to answer and you have collected some data to answer that question. You are on your way to becoming a data scientist!

### Publishing to the web

Our plan is to use the data in this spreadsheet to answer our question about how the price of a bestselling book relates to how much the author is charging for that book. To do so in the next lesson, you will first have to publish the data to the web. This gives the software we'll use in the next lesson permission to access your data. to make your sheet public, you'll want to click on File at the top of the Google Sheet. From the drop-down menu that appears, you'll want to click on "Publish to the web."


![Publish to the web...](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g37a0676f96_0_0)

In the window that pops up, you'll want to click on "Publish"

![Publish](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g37a0676f96_0_8)

A box will appear to confirm that you would like to publish this Google Sheet. Click "OK."


![OK](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g37a0676f96_0_17)

### Making the sheet public

After publishing your data to the web, the last step is to make these data accessible to others who have the link.This can be done easily on a Google Sheet by clicking on "Share" in the top right-hand corner of the Google Sheet.


![Share](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f8abafabb_0_75)

A "Share with others" box will pop up. Click on "Get shareable link."


![Share with others](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f8abafabb_0_82)

Your screen will update so that this document can now be viewed by anyone, as long as they have the link to the spreadsheet.


![Shareable](https://docs.google.com/presentation/d/1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM/export/png?id=1EPt7DuMZOqJMElDNMi3PWO66OytMlWPoc-RsopdVxNM&pageid=g2f8abafabb_0_89)

Congrats!! You have successfully made this spreadsheet shareable and the link has been copied. You'll be asked to paste this link in the quiz for this lesson, and we'll use this spreadsheet link in the next lesson when you get started using RStudio Cloud, so don't close your Google Sheets tab quite yet.

## Google Docs

One of the benefits to using Google on the cloud is its suite of document editors, which are completely free to use and accessible anywhere online. One of these editors is Google Docs, which is a web-based word document and text editor.  If you've ever used Microsoft Word to create and edit documents, then you can think of Google Docs as an online version of Word, since it has many of the same capabilities.  In fact, it is compatible with Microsoft Word files (.docx and older) as well as plain text files (.txt).  A major benefit of Google Docs over Microsoft Word, however, is the cloud capability.  Because documents are edited online, multiple users can format and edit a word document at the same time.

Google Docs can be accessed from within Google Drive.  To create a new document through Drive, simply click the "New" button in the top left corner of the Google Drive home page and then select "Google Docs."  


![Docs on Google Drive](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g37cad8f87a_0_80)

Alternatively, you can go directly to the Google Docs URL https://docs.google.com to create a new document.  What's the difference? Google Drive contains all of the files you have stored on the cloud, including images, spreadsheets, and presentations.   Google Docs will contain only your word and text documents, so it can be useful when you only want to work with those types of files.  Here's an example of Jane's Google Docs page.  You can see her recent documents in the bottom part of the screen.  The top part, below "Start a new document" is called the TEMPLATE GALLERY, which allows you to quickly create a new document. To create a new document you can choose the blank option or any of the templates available.


![Google Docs Page](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g350069922f_0_0)

Clicking on the "TEMPLATE GALLERY" link will expand the template options to include "Resumes," "Letters," "Personal," "Work," and "Education" templates.


![Google Docs Templates Gallery](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g350069922f_0_5)

Assuming that you are logged into your Google account, underneath the templates you will see the past documents that are saved on your Google Drive under the "Recent documents".  In Jane's account, we see only one. Each of them can be opened and edited by clicking on them, which will redirect the current window to the old word document. You can sort by date modified or by title by clicking on the "A-Z" button.


![A-Z List](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g37cad8f87a_0_172)

### Auto-save feature and working offline

One of the most convenient aspects of Google Docs (and all document editors on Google Drive) is its auto-save feature. As soon as the application detects a change in the file, it will automatically save without any prompt from the user. This means you don't need to remember to save your progress as you work.  You do not need to worry about losing progress when the power goes out, the internet disconnects, or even when a computer breaks down.

If a stable internet connection is an issue or if you plan to work offline, Google Docs offers an offline mode that saves the word documents to the local computer. Even in offline mode, Google Docs will automatically save changes.

To turn on offline mode, click on the menu button in Google Docs and then click on "Settings."   


![Offline mode on](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g37cad8f87a_0_185)

Toggle the "Offline" switch to on.


![Offline mode on](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g350069922f_0_28)

Offline mode for Google Docs will also be applied to Google Sheets and Google Slides.

### Working in Google Docs

Now that we've covered how to access Google Docs and where to find Google Docs you've previously created, we'll discuss a few features that you can use within Google Docs. Additionally, many of these features can be used across Google products, so once you master them in Google Docs, you can also apply them in Google Sheets and Google Slides.

If you've worked in Google Docs or Microsoft Word previously, this will likely be a review. However, we want to make sure that all the features within Google Docs that you'll use regularly are covered in this lesson. To get started, again, you'll want to go to [Google Docs](https://docs.google.com) and click on Blank to open up a blank document.


![Opening a blank Doc](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_5)

You will then see a blank document, as shown here.  In addition to the document itself, there are many formatting options available through menus in the document editor.


![Blank Google Doc](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_0)

#### Formatting Font

Within Google Docs, once you start typing information into your document, you may want to change the way that your text looks. This is called "formatting" your text. You can format the text by:

* changing the font
* changing the size of the font
* making the font bold, italicized, or underlined
* changing the color of the font

All of these changes to text can be accomplished using the options on the toolbar within Google Docs.


![Formatting from the toolbar in Google Docs](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_15)

To use these options from the toolbar, you'll begin typing within Google Docs. Then, for any text you want to format, you will simply highlight the text, and click on the appropriate option from the toolbar. In this example, we would type "Document Title" into the Google Doc.

To make the title bold, underlined, and larger, we would just highlight the text, click on the bold symbol and the underline symbol.  While the text is still highlighted you would click on the drop down "Font size" menu, and click on a larger number (here, we've selected '24'). Now your text will be just as you want it. The same process can be used to change the font and to change the color of the font.


![Formatted title within Google Docs](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_32)

#### Aligning Text

What if, in addition to formatting the text itself you wanted to alter where the text was on the page? To change this, you can use other options from the toolbar. These buttons can be used to alter the alignment in four different ways:

* left-aligned - aligned on the left side of the page
* center-aligned - aligned in the center of the page
* right-aligned - aligned on the right side of the page
* justified - aligned so that the text is flush with both the left- and right-sides of the page


To use these options, again, you'll highlight the text you would like to align and then click on the appropriate alignment option:


![different alignment options within Google Doc](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_90)

#### Inserting a List

In addition to changing how some text is formatted or where it is on the page, you'll often find the need to include lists in your Google Docs. There are two primary types of lists in documents:

* bulleted lists - lists where each item starts with a bullet
* numbered lists - lists where each item starts with a number

To create either type of list, you can type the list out, with each item on a separate line. You'll then highlight the text you want to be a list, and click on either the numbered list icon in the toolbar or the bulleted list icon in the toolbar to create the type of list you want to create.


![options to create a numbered or bulleted list](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_127)

#### Inserting an Image

We previously covered this briefly; however, we'll cover how to insert an image into your Google Doc in more detail now.

To insert an image, you'll make sure the cursor is in your document where you would like to insert the image, and then you'll click on the insert an image icon in the toolbar to display a drop-down menu with options:


![Insert an image icon](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_61)

There are a number of ways in which you can insert an image that will appear on this menu. Most frequently, you'll likely be including images that are either on your computer or from a URL. We'll discuss those in detail now, but feel free to play around with the other options to understand them as well.

##### From a URL

If there's an image on the Internet that you would like to insert into your Google Doc, Google makes this simple for you. For example if you were on Google and searched for "R language image", you'd likely get results looking something similar to this:


![R language image search](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_148)

If you were to click on 'Images for R language', you'd see lots of images from which to choose. If you were to scroll through these, you could select your favorite image, and right-click on it.


![Google Image search](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_173)

From the drop-down menu, click on "Copy Image Address." This copies the image address (the URL) for this image. This enables you to paste it in your Google Doc.


!["Copy Image Address" menu](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_189)

You would then return to your Google Doc, ensure that your cursor is where you would like to insert the image and click on the image icon in the toolbar, and select "By URL" from the drop-down menu


![Insert Image icon and select "By URL"](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_162)

In the box that pops up, you'll then paste the URL that you just copied by using the keyboard shortcut `ctrl + v`.


![Insert image by pasting URL](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_152)

The image you selected will automatically appear in that box. Now, you just have to click "INSERT."


![Click INSERT to insert image](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_179)

The image will now appear in your Google Doc!


![image inserted in Google Doc from URL](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_184)

Whenever you're using an image that is not your own, whether in a Google Doc, a Google Sheet presentation, or anywhere else, it's important to include the source information, to give credit to the people whose image it is and to allow others to find the image if they want to.


![image inserted in Google Doc from URL with source](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c04c6fe7_2_194)

Note: If an image you select does not work with these instructions, there is a chance that you do not have permission to use that image. In that case, it's likely best to search for an alternate image.


##### From your computer

In addition to inserting images from URL, you may need to insert images that are on your computer locally. We previously discussed that there is not much local storage on your Chromebook; however, if you have saved an image to that space, you can insert it in your Google Doc using the following procedure.


First, you'll click on Insert Image Icon and click on the "Upload from computer" from the drop-down menu. On your Chromebook, this will give you access to your Downloads folder.


![Select "Upload from computer"](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_0_0)

If the file you want to insert has been recently downloaded, it will appear first in the list that appears. Click on the image you want to insert and then click "OPEN" at the bottom right-hand of the screen.


![Select image from Downloads in Documents that appear](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_0_5)

Your image will now be inserted in your Google Doc! As mentioned in the previous section, don't forget to include your source!


![Image inserted from computer](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_0_10)

#### Inserting a Table

In addition to inserting lists and images, you may find the need to insert tables into your Google Docs. To do so, you'll make sure your cursor is in your Google Doc where you'd like to insert the table and then click on "Insert" from the menu along the top of your Google Doc. From the drop-down menu, you'll click on Table.


![Insert table](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_29)

This will expose an additional menu from which you'll select how many columns and rows you want the table to have. For example, if you want a table with 4 columns and two rows, you'll highlight that in the squares that pop up and click once.


![Insert table using highlighted cells](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_34)

In this case, a 4x2 (meaning 4 columns and 2 rows) has been inserted in your document.


![table inserted within a Google Doc](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_39)

You can then click in the squares of the table to add text to your table. Note that all of the formatting discussed earlier in this lesson still applies within a table. You can change the font, font size, and color of text within a table.

Finally, to change additional things within your table, you can always put your cursor in the table and right-click to expose a drop-down menu, and make a selection from that list. If you need additional columns or rows or to delete columns or rows, that can be accomplished in this manner.


![Additional table options can be accessed by double clicking within a table](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_44)

### Renaming Your Document

"Untitled document" is not a great name for your Google Doc. To change the name of your document, simply click in the "Untitled document" box at the top of the Google Doc and type in what you would like your filename to be. In this case, we chose "google_doc_intro." We'll cover how to best name files in a later course; however, for now, make sure you change the name of your Google Docs to something more informative than "Untitled document", and very briefly, it's best not to use spaces in your filenames but rather to use an underscore anywhere you would otherwise put a space.


![renamed Google Doc](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g39c29fd30c_2_51)

### Download documents in different formats

You can also download Google Docs documents in most common formats. You should click on "File" in the top menu and then select "Download as." You can then choose the format you want among the options including .pdf, .docx, .rtf, etc.


![Downloading documents](https://docs.google.com/presentation/d/1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM/export/png?id=1Z8iXcc046CvMC7dbCItTSBT2-yBVuuNSEDGKAe3FYhM&pageid=g350069922f_0_33)

For sharing documents you can follow the procedure we learned in the lesson on Google Drive.

### More specifics on using Google Docs

This lesson has covered a number of helpful features within Google Docs. There are many more capabilities within this application, so feel free to play around and check out additional resources here and on the web.  For example, there are many tutorials for using Drive on YouTube.com.

Google also has extensive information on getting started with Drive on their G Suite Learning Center, which can be found at the following web address: https://gsuite.google.com/learning-center/products/docs/get-started/#!/

If you're already familiar with Microsoft Word, Google Docs also operates very similarly without a couple of Word's more advanced features. However, most tasks can be done with Google Docs, from simple text editing to importing images and graphs to exporting documents as PDFs. There are more in-depth guides on [creating documents](https://www.gcflearnfree.org/googlespreadsheets/creating-google-docs/1/) and [downloading and printing](https://www.gcflearnfree.org/googlespreadsheets/converting-and-printing-docs/1/).


### Additional Resources

* [Google's Google Doc Tutorial](https://gsuite.google.com/learning-center/products/docs/get-started/#!/)
* [GCF Learn Tutorial](https://www.gcflearnfree.org/googledocuments/creating-google-docs/1/)
