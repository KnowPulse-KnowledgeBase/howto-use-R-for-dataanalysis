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

-c():a string of value'

xc <- 1:10
xc
##  [1]  1  2  3  4  5  6  7  8  9 10

xc <- c(1,2,3,4,5,6,7,8,9,10)
xc
##  [1]  1  2  3  4  5  6  7  8  9 10

```diff

-c(): a matrix'

xm <- matrix(1:100, nrow = 10, ncol = 10, byrow = T)
xm

##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1    2    3    4    5    6    7    8    9    10
##  [2,]   11   12   13   14   15   16   17   18   19    20
##  [3,]   21   22   23   24   25   26   27   28   29    30
##  [4,]   31   32   33   34   35   36   37   38   39    40
##  [5,]   41   42   43   44   45   46   47   48   49    50
##  [6,]   51   52   53   54   55   56   57   58   59    60
##  [7,]   61   62   63   64   65   66   67   68   69    70
##  [8,]   71   72   73   74   75   76   77   78   79    80
##  [9,]   81   82   83   84   85   86   87   88   89    90
## [10,]   91   92   93   94   95   96   97   98   99   100

xm <- matrix(1:100, nrow = 10, ncol = 10, byrow = F)
xm

##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1   11   21   31   41   51   61   71   81    91
##  [2,]    2   12   22   32   42   52   62   72   82    92
##  [3,]    3   13   23   33   43   53   63   73   83    93
##  [4,]    4   14   24   34   44   54   64   74   84    94
##  [5,]    5   15   25   35   45   55   65   75   85    95
##  [6,]    6   16   26   36   46   56   66   76   86    96
##  [7,]    7   17   27   37   47   57   67   77   87    97
##  [8,]    8   18   28   38   48   58   68   78   88    98
##  [9,]    9   19   29   39   49   59   69   79   89    99
## [10,]   10   20   30   40   50   60   70   80   90   100

-c(): A data frame'

xd <- data.frame(
  x1 = c("aa","bb","cc","dd","ee",
         "ff","gg","hh","ii","jj"),
  x2 = 1:10,
  x3 = c(1,1,1,1,1,2,2,2,3,3),
  x4 = rep(c(1,2), times = 5),
  x5 = rep(1:5, times = 2),
  x6 = rep(1:5, each = 2),
  x7 = seq(5, 50, by = 5),
  x8 = log10(1:10),
  x9 = (1:10)^3,
  x10 = c(T,T,T,F,F,T,T,F,F,F)
)
xd

##    x1 x2 x3 x4 x5 x6 x7        x8   x9   x10
## 1  aa  1  1  1  1  1  5 0.0000000    1  TRUE
## 2  bb  2  1  2  2  1 10 0.3010300    8  TRUE
## 3  cc  3  1  1  3  2 15 0.4771213   27  TRUE
## 4  dd  4  1  2  4  2 20 0.6020600   64 FALSE
## 5  ee  5  1  1  5  3 25 0.6989700  125 FALSE
## 6  ff  6  2  2  1  3 30 0.7781513  216  TRUE
## 7  gg  7  2  1  2  4 35 0.8450980  343  TRUE
## 8  hh  8  2  2  3  4 40 0.9030900  512 FALSE
## 9  ii  9  3  1  4  5 45 0.9542425  729 FALSE
## 10 jj 10  3  2  5  5 50 1.0000000 1000 FALSE

-c(): A list'

xl <- list(xc, xm, xd)
xl[[1]]

##  [1]  1  2  3  4  5  6  7  8  9 10

xl[[2]]
##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1   11   21   31   41   51   61   71   81    91
##  [2,]    2   12   22   32   42   52   62   72   82    92
##  [3,]    3   13   23   33   43   53   63   73   83    93
##  [4,]    4   14   24   34   44   54   64   74   84    94
##  [5,]    5   15   25   35   45   55   65   75   85    95
##  [6,]    6   16   26   36   46   56   66   76   86    96
##  [7,]    7   17   27   37   47   57   67   77   87    97
##  [8,]    8   18   28   38   48   58   68   78   88    98
##  [9,]    9   19   29   39   49   59   69   79   89    99
## [10,]   10   20   30   40   50   60   70   80   90   100

xl[[3]]
##    x1 x2 x3 x4 x5 x6 x7        x8   x9   x10
## 1  aa  1  1  1  1  1  5 0.0000000    1  TRUE
## 2  bb  2  1  2  2  1 10 0.3010300    8  TRUE
## 3  cc  3  1  1  3  2 15 0.4771213   27  TRUE
## 4  dd  4  1  2  4  2 20 0.6020600   64 FALSE
## 5  ee  5  1  1  5  3 25 0.6989700  125 FALSE
## 6  ff  6  2  2  1  3 30 0.7781513  216  TRUE
## 7  gg  7  2  1  2  4 35 0.8450980  343  TRUE
## 8  hh  8  2  2  3  4 40 0.9030900  512 FALSE
## 9  ii  9  3  1  4  5 45 0.9542425  729 FALSE
## 10 jj 10  3  2  5  5 50 1.0000000 1000 FALSE
```

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
