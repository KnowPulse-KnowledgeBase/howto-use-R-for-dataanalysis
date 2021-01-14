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

Data wrangling with `tidyverse` and `pipes (%>%)`

  




```
library(tidyverse) # install.packages("tidyverse")
xx <- data.frame(Group = c("X","X","Y","Y","Y","Y","Y","X","X","X")) %>%
  mutate(Data1 = 1:10, 
         Data2 = seq(10, 100, by = 10),
         NewData1 = Data1 + Data2,
         NewData2 = Data1 * 1000)
xx

```
```
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
xx %>% filter(Data1 < 5)
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
