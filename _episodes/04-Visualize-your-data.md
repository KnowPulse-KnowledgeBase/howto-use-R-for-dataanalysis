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

Selecting data


xc[5] # 5th element in xc

## [1] 5

xd$x3[5] # 5th element in col "x3"

## [1] 1

xd[5,"x3"] # row 5, col "x3"

## [1] 1

xd$x3 # all of col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3

xd[,"x3"] # all rows, col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3

xd[3,] # row 3, all cols
##   x1 x2 x3 x4 x5 x6 x7        x8 x9  x10
## 3 cc  3  1  1  3  2 15 0.4771213 27 TRUE

xd[c(2,4),c("x4","x5")] # rows 2 & 4, cols "x4" & "x5"
##   x4 x5
## 2  2  2
## 4  2  4

xl[[3]]$x1 # 3rd object in the list, col "x1
##  [1] "aa" "bb" "cc" "dd" "ee" "ff" "gg" "hh" "ii" "jj"
```
## Data Formats

Data can also be saved in many formats:
* numeric
* integer
* character
* factor
* logical

```
xd$x3 <- as.character(xd$x3)
xd$x3
##  [1] "1" "1" "1" "1" "1" "2" "2" "2" "3" "3"

xd$x3 <- as.numeric(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3

xd$x3 <- as.factor(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 1 2 3

xd$x3 <- factor(xd$x3, levels = c("3","2","1"))
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 3 2 1

xd$x10
##  [1]  TRUE  TRUE  TRUE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE

as.numeric(xd$x10) # TRUE = 1, FALSE = 0
##  [1] 1 1 1 0 0 1 1 0 0 0

sum(xd$x10)
## [1] 5
```

Internal structure of an object can be checked with `str()`

```
str(xc) # c()
##  num [1:10] 1 2 3 4 5 6 7 8 9 10

str(xm) # matrix()
##  int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...

str(xd) # data.frame()
## 'data.frame':    10 obs. of  10 variables:
##  $ x1 : chr  "aa" "bb" "cc" "dd" ...
##  $ x2 : int  1 2 3 4 5 6 7 8 9 10
##  $ x3 : Factor w/ 3 levels "3","2","1": 3 3 3 3 3 2 2 2 1 1
##  $ x4 : num  1 2 1 2 1 2 1 2 1 2
##  $ x5 : int  1 2 3 4 5 1 2 3 4 5
##  $ x6 : int  1 1 2 2 3 3 4 4 5 5
##  $ x7 : num  5 10 15 20 25 30 35 40 45 50
##  $ x8 : num  0 0.301 0.477 0.602 0.699 ...
##  $ x9 : num  1 8 27 64 125 216 343 512 729 1000
##  $ x10: logi  TRUE TRUE TRUE FALSE FALSE TRUE ...

str(xl) # list()
## List of 3
##  $ : num [1:10] 1 2 3 4 5 6 7 8 9 10
##  $ : int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...
##  $ :'data.frame':    10 obs. of  10 variables:
##   ..$ x1 : chr [1:10] "aa" "bb" "cc" "dd" ...
##   ..$ x2 : int [1:10] 1 2 3 4 5 6 7 8 9 10
##   ..$ x3 : num [1:10] 1 1 1 1 1 2 2 2 3 3
##   ..$ x4 : num [1:10] 1 2 1 2 1 2 1 2 1 2
##   ..$ x5 : int [1:10] 1 2 3 4 5 1 2 3 4 5
##   ..$ x6 : int [1:10] 1 1 2 2 3 3 4 4 5 5
##   ..$ x7 : num [1:10] 5 10 15 20 25 30 35 40 45 50
##   ..$ x8 : num [1:10] 0 0.301 0.477 0.602 0.699 ...
##   ..$ x9 : num [1:10] 1 8 27 64 125 216 343 512 729 1000
##   ..$ x10: logi [1:10] TRUE TRUE TRUE FALSE FALSE TRUE ...
```
## Packages
Additional libraries can be installed and loaded for use.

```
install.packages("scales")
```
```
library(scales)
xx <- data.frame(Values = 1:10)
xx$Rescaled <- rescale(x = xx$Values, to = c(1,30))
xx
```

```
##    Values  Rescaled
## 1       1  1.000000
## 2       2  4.222222
## 3       3  7.444444
## 4       4 10.666667
## 5       5 13.888889
## 6       6 17.111111
## 7       7 20.333333
## 8       8 23.555556
## 9       9 26.777778
## 10     10 30.000000
```

## Data Wrangling
[R for Data Science] (https://r4ds.had.co.nz/)

```
xx <- data.frame(Group = c("X","X","Y","Y","Y","X","X","X","Y","Y"),
                 Data1 = 1:10, 
                 Data2 = seq(10, 100, by = 10))
xx$NewData1 <- xx$Data1 + xx$Data2
xx$NewData2 <- xx$Data1 * 1000
xx
```

```
##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      X     6    60       66     6000
## 7      X     7    70       77     7000
## 8      X     8    80       88     8000
## 9      Y     9    90       99     9000
## 10     Y    10   100      110    10000
```
```
xx$Data1 < 5 # which are less than 5
##  [1]  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE
```
```
xx[xx$Data1 < 5,]

##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
```
```
xx[xx$Group == "X", c("Group","Data2","NewData1")]

##   Group Data2 NewData1
## 1     X    10       11
## 2     X    20       22
## 6     X    60       66
## 7     X    70       77
## 8     X    80       88
```

Data wrangling with tidyverse and pipes (%>%)

```
library(tidyverse) # install.packages("tidyverse")
xx <- data.frame(Group = c("X","X","Y","Y","Y","Y","Y","X","X","X")) %>%
  mutate(Data1 = 1:10, 
         Data2 = seq(10, 100, by = 10),
         NewData1 = Data1 + Data2,
         NewData2 = Data1 * 1000)
xx

##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      Y     6    60       66     6000
## 7      Y     7    70       77     7000
## 8      X     8    80       88     8000
## 9      X     9    90       99     9000
## 10     X    10   100      110    10000
```

```
pch Plot
R Markdown
 Derek Michael Wright
derek.wright@usask.ca
www.dblogr.com/

 2020-10-12

Introduction
This vignette will introduce the reader to R, a free, open-source statistical computing environment and RStudio, a integrated development environment for R.



Download R
Download R

Download RStudio



http://r-statistics.co/R-Tutorial.html

https://bookdown.org/rdpeng/exdata/getting-started-with-r.html#installation

Calculator
R can be used as a super awesome calculator

# 5 + 3 = 8
5 + 3 
## [1] 8
# 24 / (1 + 2) = 8
24 / (1 + 2) 
## [1] 8
# 2 * 2 * 2 = 8
2^3 
## [1] 8
# 8 * 8 = 64
sqrt(64) 
## [1] 8
# -log10(0.05 / 5000000) = 8
-log10(0.05 / 5000000) 
## [1] 8
Functions
R has many useful built in functions

1:10
##  [1]  1  2  3  4  5  6  7  8  9 10
as.character(1:10)
##  [1] "1"  "2"  "3"  "4"  "5"  "6"  "7"  "8"  "9"  "10"
rep(1:2, times = 5)
##  [1] 1 2 1 2 1 2 1 2 1 2
rep(1:5, times = 2)
##  [1] 1 2 3 4 5 1 2 3 4 5
rep(1:5, each = 2)
##  [1] 1 1 2 2 3 3 4 4 5 5
rep(1:5, length.out = 7)
## [1] 1 2 3 4 5 1 2
help(rep)
seq(5, 50, by = 5)
##  [1]  5 10 15 20 25 30 35 40 45 50
seq(5, 50, length.out = 5)
## [1]  5.00 16.25 27.50 38.75 50.00
paste(1:10, 20:30, sep = "-")
##  [1] "1-20"  "2-21"  "3-22"  "4-23"  "5-24"  "6-25"  "7-26"  "8-27"  "9-28"  "10-29" "1-30"
paste(1:10, collapse = "-")
## [1] "1-2-3-4-5-6-7-8-9-10"
paste0("x", 1:10)
##  [1] "x1"  "x2"  "x3"  "x4"  "x5"  "x6"  "x7"  "x8"  "x9"  "x10"
min(1:10)
## [1] 1
max(1:10)
## [1] 10
range(1:10)
## [1]  1 10
mean(1:10)
## [1] 5.5
sd(1:10)
## [1] 3.02765
Users can also create their own functions

customFunction1 <- function(x, y) {
  z <- 100 * x / (x + y)
  paste(z, "%")
}
customFunction1(x = 10, y = 90)
## [1] "10 %"
customFunction2 <- function(x) {
  mymin <- mean(x - sd(x))
  mymax <- mean(x) + sd(x)
  print(paste("Min =", mymin))
  print(paste("Max =", mymax))
}
customFunction2(x = 1:10)
## [1] "Min = 2.47234964590251"
## [1] "Max = 8.52765035409749"
for loops and if else statements

xx <- NULL #creates and empty object
for(i in 1:10) {
  xx[i] <- i*3
}
xx
##  [1]  3  6  9 12 15 18 21 24 27 30
xx %% 2 #gives the remainder when divided by 2
##  [1] 1 0 1 0 1 0 1 0 1 0
for(i in 1:length(xx)) {
  if((xx[i] %% 2) == 0) {
    print(paste(xx[i],"is Even"))
  } else { 
      print(paste(xx[i],"is Odd")) 
    }
}
## [1] "3 is Odd"
## [1] "6 is Even"
## [1] "9 is Odd"
## [1] "12 is Even"
## [1] "15 is Odd"
## [1] "18 is Even"
## [1] "21 is Odd"
## [1] "24 is Even"
## [1] "27 is Odd"
## [1] "30 is Even"
# or
ifelse(xx %% 2 == 0, "Even", "Odd")
##  [1] "Odd"  "Even" "Odd"  "Even" "Odd"  "Even" "Odd"  "Even" "Odd"  "Even"
paste(xx, ifelse(xx %% 2 == 0, "is Even", "is Odd"))
##  [1] "3 is Odd"   "6 is Even"  "9 is Odd"   "12 is Even" "15 is Odd"  "18 is Even" "21 is Odd"  "24 is Even" "27 is Odd"  "30 is Even"
Objects
Information can be stored in user defined objects, in multiple forms:

c(): a string of values
matrix(): a two dimensional matrix in one format
data.frame(): a two dimensional matrix where each column can be a different format
list():
A string…

xc <- 1:10
xc
##  [1]  1  2  3  4  5  6  7  8  9 10
xc <- c(1,2,3,4,5,6,7,8,9,10)
xc
##  [1]  1  2  3  4  5  6  7  8  9 10
A matrix…

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
A data frame…

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
A list…

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
Selecting data…

xc[5] # 5th element in xc
## [1] 5
xd$x3[5] # 5th element in col "x3"
## [1] 1
xd[5,"x3"] # row 5, col "x3"
## [1] 1
xd$x3 # all of col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3
xd[,"x3"] # all rows, col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3
xd[3,] # row 3, all cols
##   x1 x2 x3 x4 x5 x6 x7        x8 x9  x10
## 3 cc  3  1  1  3  2 15 0.4771213 27 TRUE
xd[c(2,4),c("x4","x5")] # rows 2 & 4, cols "x4" & "x5"
##   x4 x5
## 2  2  2
## 4  2  4
xl[[3]]$x1 # 3rd object in the list, col "x1
##  [1] "aa" "bb" "cc" "dd" "ee" "ff" "gg" "hh" "ii" "jj"
Data Formats
Data can also be saved in many formats:

numeric
integer
character
factor
logical
xd$x3 <- as.character(xd$x3)
xd$x3
##  [1] "1" "1" "1" "1" "1" "2" "2" "2" "3" "3"
xd$x3 <- as.numeric(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
xd$x3 <- as.factor(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 1 2 3
xd$x3 <- factor(xd$x3, levels = c("3","2","1"))
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 3 2 1
xd$x10
##  [1]  TRUE  TRUE  TRUE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE
as.numeric(xd$x10) # TRUE = 1, FALSE = 0
##  [1] 1 1 1 0 0 1 1 0 0 0
sum(xd$x10)
## [1] 5
Internal structure of an object can be checked with str()

str(xc) # c()
##  num [1:10] 1 2 3 4 5 6 7 8 9 10
str(xm) # matrix()
##  int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...
str(xd) # data.frame()
## 'data.frame':    10 obs. of  10 variables:
##  $ x1 : chr  "aa" "bb" "cc" "dd" ...
##  $ x2 : int  1 2 3 4 5 6 7 8 9 10
##  $ x3 : Factor w/ 3 levels "3","2","1": 3 3 3 3 3 2 2 2 1 1
##  $ x4 : num  1 2 1 2 1 2 1 2 1 2
##  $ x5 : int  1 2 3 4 5 1 2 3 4 5
##  $ x6 : int  1 1 2 2 3 3 4 4 5 5
##  $ x7 : num  5 10 15 20 25 30 35 40 45 50
##  $ x8 : num  0 0.301 0.477 0.602 0.699 ...
##  $ x9 : num  1 8 27 64 125 216 343 512 729 1000
##  $ x10: logi  TRUE TRUE TRUE FALSE FALSE TRUE ...
str(xl) # list()
## List of 3
##  $ : num [1:10] 1 2 3 4 5 6 7 8 9 10
##  $ : int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...
##  $ :'data.frame':    10 obs. of  10 variables:
##   ..$ x1 : chr [1:10] "aa" "bb" "cc" "dd" ...
##   ..$ x2 : int [1:10] 1 2 3 4 5 6 7 8 9 10
##   ..$ x3 : num [1:10] 1 1 1 1 1 2 2 2 3 3
##   ..$ x4 : num [1:10] 1 2 1 2 1 2 1 2 1 2
##   ..$ x5 : int [1:10] 1 2 3 4 5 1 2 3 4 5
##   ..$ x6 : int [1:10] 1 1 2 2 3 3 4 4 5 5
##   ..$ x7 : num [1:10] 5 10 15 20 25 30 35 40 45 50
##   ..$ x8 : num [1:10] 0 0.301 0.477 0.602 0.699 ...
##   ..$ x9 : num [1:10] 1 8 27 64 125 216 343 512 729 1000
##   ..$ x10: logi [1:10] TRUE TRUE TRUE FALSE FALSE TRUE ...
Packages
Additional libraries can be installed and loaded for use.

install.packages("scales")
library(scales)
xx <- data.frame(Values = 1:10)
xx$Rescaled <- rescale(x = xx$Values, to = c(1,30))
xx
##    Values  Rescaled
## 1       1  1.000000
## 2       2  4.222222
## 3       3  7.444444
## 4       4 10.666667
## 5       5 13.888889
## 6       6 17.111111
## 7       7 20.333333
## 8       8 23.555556
## 9       9 26.777778
## 10     10 30.000000
Data Wrangling
R for Data Science

xx <- data.frame(Group = c("X","X","Y","Y","Y","X","X","X","Y","Y"),
                 Data1 = 1:10, 
                 Data2 = seq(10, 100, by = 10))
xx$NewData1 <- xx$Data1 + xx$Data2
xx$NewData2 <- xx$Data1 * 1000
xx
##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      X     6    60       66     6000
## 7      X     7    70       77     7000
## 8      X     8    80       88     8000
## 9      Y     9    90       99     9000
## 10     Y    10   100      110    10000
xx$Data1 < 5 # which are less than 5
##  [1]  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE
xx[xx$Data1 < 5,]
##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
xx[xx$Group == "X", c("Group","Data2","NewData1")]
##   Group Data2 NewData1
## 1     X    10       11
## 2     X    20       22
## 6     X    60       66
## 7     X    70       77
## 8     X    80       88
Data wrangling with tidyverse and pipes (%>%)

library(tidyverse) # install.packages("tidyverse")
xx <- data.frame(Group = c("X","X","Y","Y","Y","Y","Y","X","X","X")) %>%
  mutate(Data1 = 1:10, 
         Data2 = seq(10, 100, by = 10),
         NewData1 = Data1 + Data2,
         NewData2 = Data1 * 1000)
xx
##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      Y     6    60       66     6000
## 7      Y     7    70       77     7000
## 8      X     8    80       88     8000
## 9      X     9    90       99     9000
## 10     X    10   100      110    10000
```
```
filter(xx, Data1 < 5)
##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
```

```
xx %>% filter(Group == "X") %>% 
  select(Group, NewColName=Data2, NewData1)

##   Group NewColName NewData1
## 1     X         10       11
## 2     X         20       22
## 3     X         80       88
## 4     X         90       99
## 5     X        100      110
```
```
xs <- xx %>% 
  group_by(Group) %>% 
  summarise(Data2_mean = mean(Data2),
            Data2_sd = sd(Data2),
            NewData2_mean = mean(NewData2),
            NewData2_sd = sd(NewData2))
xs
## # A tibble: 2 x 5
##   Group Data2_mean Data2_sd NewData2_mean NewData2_sd
##   <chr>      <dbl>    <dbl>         <dbl>       <dbl>
## 1 X             60     41.8          6000       4183.
## 2 Y             50     15.8          5000       1581.


## # A tibble: 2 x 5
##   Group Data2_mean Data2_sd NewData2_mean NewData2_sd
##   <chr>      <dbl>    <dbl>         <dbl>       <dbl>
## 1 X             60     41.8          6000       4183.
## 2 Y             50     15.8          5000       1581.
```
```
xx %>% left_join(xs, by = "Group")
##    Group Data1 Data2 NewData1 NewData2 Data2_mean Data2_sd NewData2_mean NewData2_sd
## 1      X     1    10       11     1000         60 41.83300          6000    4183.300
## 2      X     2    20       22     2000         60 41.83300          6000    4183.300
## 3      Y     3    30       33     3000         50 15.81139          5000    1581.139
## 4      Y     4    40       44     4000         50 15.81139          5000    1581.139
## 5      Y     5    50       55     5000         50 15.81139          5000    1581.139
## 6      Y     6    60       66     6000         50 15.81139          5000    1581.139
## 7      Y     7    70       77     7000         50 15.81139          5000    1581.139
## 8      X     8    80       88     8000         60 41.83300          6000    4183.300
## 9      X     9    90       99     9000         60 41.83300          6000    4183.300
## 10     X    10   100      110    10000         60 41.83300          6000    4183.300
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
