<style>
body {
 background-image: url("presentation-figure/background 1680x1050 E.png");
   /* Full height */
  height: 100%; 

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>

Introduction to R and RStudio
========================================================
author: Marko Draisma (Vijfhart IT-opleidingen & AT computing)
date: 17-03-2019
autosize: true

R en RStudio
========================================================
* **R** is the language, the workhorse
* **RStudio** is your gate to productivity
  - Console is a way to communicate with R directly
  - Terminal is a Linux terminal
  - To try out and remember your steps: use **R scripts**
  - To document and remember your steps: use **R notebooks**

Starting a project
=======================================================
<small>
File > New Project >  New Directory / Existing Directory

Within project folder: Files > New Folder
* data (for raw, read only datasets)
* scripts (for .R scripts)
* notebooks (for .Rmd notebooks)
* doc (for text documents related to the project)
* results (for files generated during cleanup and analysis)

Tip: (can also be used outside project folders): use More > Set As Working Directory  
`setwd("~/Rdata/gastcollege")`  

or More > Goto Working Directory  
to jump to the working directory
</small>

Creating and Running a script
=======================================================
<small>
File > New File > R Script (Ctrl-Shift-Alt-N)

Enter script, use Ctrl-Enter to run each line

```
print(fivenum(cars$speed))
print(mean(cars$speed))
```

File > Save as > scripts > cars example  


```r
source("scripts/cars example.R")
```

```
[1]  4 12 15 19 25
[1] 15.4
```
</small>


Creating a Notebook
=======================================================
File > New > R Notebook

R Notebooks can contain markdown, R snippets and LaTeX formula's  

You work in a .Rmd file  

After each save a HTML file containing the current state is saved too.


Getting the data
========================================================
Using the menu: 
* Environment tab (Right) > Import Dataset > From Text (base)...
![import from text (baxe)](presentation-figure/import_base.png)

Getting the data
========================================================
Using the menu: 
* Environment tab (Right) > Import Dataset > From Text (readr)...
![import from text (baxe)](presentation-figure/import_readr.png)

Getting the data
========================================================
* Using commands:

`library(readr)`  
`Titanic <- read_csv("data/Titanic.csv")`  

`Titanic <- read_csv("data/Titanic.csv", col_types = cols(`  
    `Age = col_factor(levels = c("Child", 
    "Adult")),`  
    `Class = col_factor(levels = c("1st",
    "2nd", "3rd", "Crew"), ordered=TRUE),`  
    `Sex = col_factor(levels = c("Female", 
    "Male")),`  
    `Survived = col_factor(levels = c("No", 
    "Yes"))))`
    
`View(Titanic)`

Getting the data
========================================================
class: small-code
| Function	| What It Does	| Example |
|---------|-------|-------|
|read.table()|	Reads any tabular data where the columns are separated (for example by commas or tabs). You can specify the separator (for example, commas or tabs), as well as other arguments to precisely describe your data. |	read.table(file=”myfile”, sep=”t”, header=TRUE) |
| read.csv() |	A simplified version of read.table() with all the arguments preset to read CSV files, like Microsoft Excel spreadsheets.	| read.csv(file=”myfile”) |
| read.csv2() |	A version of read.csv() configured for data with a comma as the decimal point and a semicolon as the field separator.	| read.csv2(file=”myfile”, header=TRUE) |
| read.delim() |	Useful for reading delimited files, with tabs as the default separator. |	read.delim(file=”myfile”, header=TRUE) |
| scan() |	Allows you finer control over the read process when your data isn’t tabular.	| scan(“myfile”, skip = 1, nmax=100) |
readLines() |	Reads text from a text file one line at a time. |	readLines(“myfile”) |
| read.fwf |	Read a file with dates in fixed-width format. In other words, each column in the data has a fixed number of characters. |	read.fwf(“myfile”, widths=c(1,2,3) |

What's next?
========================================================
1. quick demo of R notebooks
2. import data from github: https://github.com/markodraisma/Rintroduction
3. create a new project based on this folder
4. take good notice of the resources in notebook 0 (make your own changes)
5. try out notebook 1 to 8 (add your own code and comments)
6. create a new project, and a new notebook
7. in it, assemble information to check out later, needed for you thesis
8. try out 01,04,05,06,08 from [https://swcarpentry.github.io/r-novice-gapminder/](https://swcarpentry.github.io/r-novice-gapminder/) 
and/or try out more advanced regression models: [http://r-statistics.co/adv-regression-models.html](http://r-statistics.co/adv-regression-models.html)



