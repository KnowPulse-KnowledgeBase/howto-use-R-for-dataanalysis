---
title: "Data-Wrangling"
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
## Data Wrangling
[R for Data Science](https://r4ds.had.co.nz/)

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



  




