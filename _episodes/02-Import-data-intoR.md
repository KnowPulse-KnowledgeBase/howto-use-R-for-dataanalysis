---
title: "Import data into R"
teaching: 20
exercises: 20
questions:
- "How to prepare a csv file for my raw phenotypic data?"
- "How to read a csv file with RStudio?"

objectives:
- "Make your raw phenotypic data in a R friendly way"
keypoints:
- "Ensure your files is saved as .csv before you import it into RStudio ."
- "Save your file in csv format"
- ""
---
## Download your .csv from KnowPulse then import it into Rstudio
After growing season, you have your data files downloaded from KnowPulse as comma separated value `.csv`. The next step, you want to import your `.csv `files into Rstudio for further analysis. 


### Step 1
Import your downloaded `.csv file` on bottom right panel to Rstudio, you will be able to see the URL of the file. 
![Screenshot of main code listing](../fig/Import-data-1.png)

### Step 2
Then you can preview your data, meanwhile, more **Import Options** are available for you to rename your file, or choose which sheet you would like RStudio to view.
![Screenshot of main code listing](../fig/Import-data-2.png)


### Step 3
It is intuitive to hit **Import** on bottom right, which is an option to import your file; as an alternate, you can also copy paste the code into the editor. 
![Screenshot of main code listing](../fig/Import-data-3.png)

### Step 4
Inside the bracket besdie the `library`, **readr** is the package that is used to read your file. So you want to run both lines of code.
![Screenshot of main code listing](../fig/Import-data-4.png)

Right now your file has been successfully imported to RStudio, you can continue on your data analysis. 
![Screenshot of main code listing](../fig/Import-data-5.png)



## Import data with `read.csv`

The following command can also be used to import your file. Let us call your file `mydata` in this case. 

### Step 1
```
mydata <- read.csv(file.choose(), header=T)
```
* `file.choose()` command allows a menu poping for you to choose your file instead of typing its full path to find it.
* `header=T`euqals to `header=TRUE` means you want to keep the first row of your dataset as variable names or headers. Otherwise, you can set `header=FALSE`

### Step 2
![Screenshot of main code listing](../fig/Import-data-6.png)
![Screenshot of main code listing](../fig/Import-data-7.png)
For excel sheets, the package **readxl** can be used to read in sheets of data.


## Excel sheets 



```
library(readxl) # install.packages("readxl")
xx <- read_xlsx("Data.xlsx", sheet = "Data")
```
