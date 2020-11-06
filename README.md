# Overview

Welcome to this overview of R Markdown. This tutorial is intended to take 1 hour and was developed originally as part of the <a href="https://www.soils.org" target="_blank">2020 ASA-CSSA-SSSA International Annual Meeting</a> that was held virtually from November 9-13, 2020.

<i>Please note all session goal modules will be posted by November 8, 2020.</i>

# Session goals

This session has multiple goals. You can view these components in any order. 

* [Session at a glance](#session-at-a-glance)
* [Share resources](#share-resources)
* [Discuss the importance of code and documentation](#Discuss-the-importance-of-code-and-documentation)
* [Explain what R Markdown is](#Explain-what-R-Markdown-is)
* [Getting started in R Markdown](#getting-started-in-r-markdown)
* [Explain what a code chunk is](#explain-what-a-code-chunk-is)
* [Run code outside a code chunk](#run-code-outside-a-code-chunk)
* Demonstrate how multiple languages can be used in RMarkdown
* Create links within a markdown file
* Create tables in R Markdown
* Show how to format an word document 
* Show how to load in a file with a uniform naming structure
* Provide an example file for additional editing and revising

## Session at a glance

Here's a quick 5 W's overview of this session to help you determine if these materials will be useful for you.

<b>Who should take this session?</b>:

If you are interested in creating reproducible analytical routines that can be used to generate reports or other data summaries, this session might be of interest to you!

<b>What is this session?</b>

This sessions is a collection of overivews for different components of working with RMarkdown files.

<b>When should I complete this session?</b>

Please feel free to review these materials at any time. This tutorial will remain up online and will be modified in the future.

<b>Where should I complete this session?</b>

You can complete this session by reviewing the materials here. It could also be helpful to have a copy of RStudio installed on your computer and work through the examples. But, it's not required to have RStudio on your computer to view these materials. All materials are posted here.

<b>Why should I complete this session?</b>

This session should help you get an initial overview about using R Markdown. I don't mean to suggest everything about using R, Markdown, or R Markdown is covered in this tutorial. There's always more to learn!

If any of the above questions and answers sounded good to you, please read on!

<hr>

* [Back to Session goals](#session-goals)

<hr>



## Share resources

There are multiple overviews of RMarkdown available online. You might find the following resources of interest. Please feel free to suggest other resources to include on this list too!

* <a href="https://bookdown.org/yihui/rmarkdown/" target="_blank">R Markdown: The Definitive Guide</a> by Yihui Xie, J. J. Allaire, Garrett Grolemund
* <a href="https://rmarkdown.rstudio.com/" target="_blank">General overview from RStudio</a>
* <a href="https://rmarkdown.rstudio.com/articles.html" target="_blank">Series of RMarkdown related articles from RStudio</a>
* <a href="https://rmarkdown.rstudio.com/lesson-1.html" target="_blank">Lession 1 from RStudio about RMarkdown</a>
* <a href="https://guides.github.com/features/mastering-markdown/" target="_blank">An Overview of Markdown from GitHub</a>
* <a href="https://www.markdownguide.org/basic-syntax/" target="_blank">The Basic Syntax page from the Markdown guide</a>

<hr>

* [Back to Session goals](#session-goals)

<hr>


## Discuss the importance of code and documentation

Well-documented code provides one piece of achieving the goal of reproducible science. Given your dataset and code, someone else should be able to evaluate the dataset using your code and find the same results. Your study is <i>reproducible</i> if others can take these steps. Another aspect of scientific research is <i>replicability</i>, which relates to more running a study under different conditions, such as using a different dataset or in a laboratory different from the laboratory that you used, and be able to find similar results. 

One way to think about these two topics is as follows:

* reproducibility = use same dataset and code, receive the same results

* replicability = use the same research question, different dataset, receive similar results to support the overall finding

For example, let's say you write a paper about how soil characteristics respond to a series of crop and soil management decisions, including tillage type and crops planted. You help <i>scientific reproducibility</i> by including your dataset and code so that others can use your dataset and code to match the results you present in the paper.

In this same paper, you fully describe your research study methods so that someone else could try and run the whole study again, perhaps on a different soil type or in a different climate. With these thorough descriptions you help <i>scientific replicability</i> because someone else could run a new study and see if their findings are similar to your current study.

I don't intend to exclude modelling or other computer-based study types from this description. In the above example I hope to differentiate between reproducibility and replicability. 

An R Markdown file provides one method (and certainly not the only method) for creating reproducible science. You can write annotations to your code and run the code in the same document. Readers will see the code you used and the output side-by-side. If an interested reader would like to run the analysis, they can take the code you used and compare line-by-line output with the results you presented in your study.

With an overall goal of reproducible science, many methods can be used to achieve this goal. Detailed descriptions can be written alongside any code results. You can run an analysis and print all the console results. You can use other code documentation methods, such as <a href="https://jupyter.org/" target="_blank">Jupyter Notebook</a>. 

For more information about how code is a component of reproducible and replicable science, please see the National Academies of Sciences, Engineering, and Medicine consensus report titled: 
<a href="https://www.nap.edu/read/25303/chapter/2" target="_blank">Reproducibility and Replicability in Science</a>.



<hr>

* [Back to Session goals](#session-goals)

<hr>

## Explain what R Markdown is

<a href="https://bookdown.org/yihui/rmarkdown/basics.html" target="_blank">Chapter 2 of R Markdown: The Definitive Guide</a> provides an excellent summary of what R Markdown is:  

```
"an authoring framework for data science"
```

In summarizing the two key points raised at the beginning of chapter 2, R Markdown allows you to (1) write and run code, and (2) create data reports that can be shared with others.

R Markdown can take R code (and several other code types too), run the code, and show you the code and the associated output in a report. This report can be created as an html file, a PDF, or a word document. The example used in the [Getting started in R Markdown](#getting-started-in-r-markdown) section shows how to write output to an html file. You could subsequently print this file and save as a pdf, though this is a little different than writing to a pdf directly.

R Markdown provides a method for combining your code with additional descriptive text to create a report. If you find yourself running similar code over and over again, copying and pasting into a new document, formatting, and so forth, creating a data analysis routine in R Markdown could be an option to consider.

For example, you might be interested in evaluating a dataset that is updated every week or maybe once every month (or possibly every day). The file format remains the same, but you are creating new data summaries from each file. You could create an R Markdown file that processes and analyzes the file in a consistent way and provides an output report. This standardized method could help you review the data more quickly, share these results with others, and then identify parts of the dataset that may require new analysis and code to be written.

<hr>

* [Back to Session goals](#session-goals)

<hr>

## Getting started in R Markdown

You might be interested in starting with a test file. The following steps will generate an example test file using RStudio.

1. Please make sure you have <a href="https://rstudio.com/" target="_blank">R Studio</a> installed on your computer.

2. Go to the top of the browser and create a new markdown file. 

![Image showing selecting File > New File > R Markdown](images/CreateNewFile.png)

3. Create a name for the new R Markdown file

![Typing in a new name for the markdown file](images/NameTheMarkdownFile.png)

4. Your initial R Markdown file is created! There's several pieces of helpful code that are automatically created within the document.

![Initial file created](images/InitialFileCreated.png)

5. Look to the top menu and select Knit > To HTML

![Knitting the document](images/HowToKnit.png)

6. Type in a name for the new html output file.

![Naming the knit document](images/NameTheKnitFile.png)

7. The code should be procesed and knit. The new html file will appear!

![New HTML file](images/ExampleHTML.png)

8. Check the R Markdown window that is located next to the tabs Console, Terminal, and Jobs.

![Checking R Markdown processing](images/CheckRMarkdownOutput.png)

You will see how RStudio processed each of the code chunks and provides information about how the processing occurred. If you are trying to knit a file, this output can helpful to identify where the code might be breaking and need modification.

9. You'll have two files, one with an .Rmd file type and one with an .html file type.

![File types](images/TwoFileTypes.png)

If you wanted to make edits to the html file, the best way is to edit the .Rmd file, knit a new file, and then you'll have a new html file!

<hr>

* [Back to Session goals](#session-goals)

<hr>

## Explain what a code chunk is

In R Markdown, a code chunk is any set of code that starts with three single quotes in a row and ends with three single quotes in a row.

In the example image below, the code chunk is written in R. Everything outside the code chunk, but still in the same R Markdown document, is written in Markdown. 

![Code chunk in R Markdown](images/CodeChunkInRStudio.png)

After the page is knit, the same results appear as follows:

![Code chunk after knit](images/CodeChunkAfterKnit.png)

There are many options available when setting up a code chunk. These can affect how the code is printed, if the code is run, how plots appear, and other factors. R Studio has a <a href="https://rmarkdown.rstudio.com/lesson-3.html" target="_blank">short list of options here</a> and a <a href="https://rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf" target="_blank">longer list of all options in this pdf</a>.

As a brief example, here is an example of how the include and echo options appear in R Markdown and after being knit.

![Options in R Markdown](images/OptionsInRMarkdown.png)

Once this code is knit, the options appear as shown below. Please note that the TRUE setting is the default in R Markdown for these two examples.

![Options in R Markdown](images/OptionsAfterKnit.png)

<hr>

* [Back to Session goals](#session-goals)

<hr>

## Run code outside a code chunk

You may be interested in running code outside of a code chunk. This is also possible in RMarkdown. For running code in line, you use a single quote around the statement you are interested in processing.

In R Markdown, a line of code like this

![In line within R Markdown](images/InLineInRMarkdown.png)

will appear like this after knitting

![In line after knit](images/InLineAfterKnit.png)

This technique is helpful if you want to write sentences or paragraphs that have combinations of written text and results. For example, the text that you write can be responsive to results that you generated in a previous section.

![If Else in R Markdown](images/IfElseInRMarkdown.png)

After knitting the code above, the text can then react to those new values.

![If Else after knit](images/IfElseAfterKnit.png)

<hr>

* [Back to Session goals](#session-goals)

<hr>