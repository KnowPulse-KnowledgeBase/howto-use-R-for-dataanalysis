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
- "Ensure your files contain all the required columns from template ."
- "Save your file in csv format"
- ""
---
## Import your .csv file to Rstudio
After growing season, you have your data files downloaded from KnowPulse, the next step, you want to inport your .csv files into Rstudio for further analysis. 


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

Now your file has been successfully imported to RStudio! 
![Screenshot of main code listing](../fig/Import-data-5.png)
## Import your data from excel to RStudio
