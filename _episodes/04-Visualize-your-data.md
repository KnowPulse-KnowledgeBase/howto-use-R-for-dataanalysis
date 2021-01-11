---
title: "Visualize your data"
teaching: 20
exercises: 20
questions:
- "How to visualise my data?"

objectives:
- "Visualise your data using xxx"
keypoints:
- ""
- ""
- ""

---

## Objects 

Information can be stored in user defined objects, in multiple forms:

* c(): a string of value 
* matrix(): a two dimensional matrix in one format 
* data.frame(): a two dimensional matrix where each column can be a different format
* list():

```diff
-c(): a string of value'
```
```
xc <- 1:10
xc
```
##  [1]  1  2  3  4  5  6  7  8  9 10
 xc <- c(1,2,3,4,5,6,7,8,9,10)
xc
Two ways to run your data: 
1. Select the line, then click run on top right in `Editor` 
2. Select the line, then press control+command+enter

https://r4ds.had.co.nz/data-visualisation.html

## 1. Base plotting
http://www.sthda.com/english/wiki/r-base-graphs
https://bookdown.org/rdpeng/exdata/the-base-plotting-system-1.html

## 1.1 Basic scatter plot
Code:

Ex: Temperature& Day lengths (insert picture)

Bar Chats
Ex: total precipitation
Histogram: quantative/scaled/measured/interval/ratio level
Allow to see: shape/gap/outliers/symmetry


Scatter Plot
visualizing the association between two quantative variables
Ex: Precipitation (insert picture)

OverlayingPlots

## ggplot2 package (additional packages ggbeeswarm & ggrepel)

-better, more visually appealing plots 

https://derekmichaelwright.github.io/htmls/academic/envdata.html#
## Environmental Data Vignette
Examples of how to manipulate and plot the environmenal data for AGILE project 

## Step 1 Prpare the data 
## Step 2 Summarize data
## Step 3 Plot data
