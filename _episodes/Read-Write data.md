
---
title: "Read/Write data"
teaching: 10
exercises: 10
questions:
- "How to bring my files in R?"

objectives:
- "Read already exist files with R "
keypoints:
- ""
- ""
- ""

---

## Csv File 
```
xx <- read.csv("Data.csv")
write.csv(xx, "Data.csv", row.names = F)
```

## Excel sheets 

The package `readxl` can be used to read in sheets of data.

```
library(readxl) # install.packages("readxl")
xx <- read_xlsx("Data.xlsx", sheet = "Data")
```
