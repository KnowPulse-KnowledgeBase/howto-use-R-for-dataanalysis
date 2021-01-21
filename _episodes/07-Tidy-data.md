---
title: "Tidy data"
teaching: 20
exercises: 20
questions:

- "How to tidy my data after import?"


objectives:
- "Install Tidyverse package to help tidy up data"
keypoints:
- "Ensure your files contain all the required columns from template."
- "Use the correct verbs from dplyr to rearrange you untidy data."
---
## Tidy your data
In the previous episode, you have learned how to import your tidy data. But most likely, you will have to tidy up your data after import. In this episode, we are going to learn how to tidy data. 

>“Tidy datasets are all alike, but every messy dataset is messy in its own way.” –– Hadley Wickham

## Introduce to Tidyr Package

*  [Tidy data---R for Data Science ](https://r4ds.had.co.nz/tidy-data.html)
*  [Tidy data---CRAN ](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html)
*  [Data Wrangling Cheat sheet ](https://rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)

## Installation
* install.packages("tidyverse")
* library(dplyr)

### tidyverse core principles:
* Each variable forms a column.
* Each observation forms a row.
* Each type of observational unit forms a table.

### 6 main verbs in dplyr
* mutate()
* select()
* filter()
* summarise()
* arrange()
* group by()

## Example dataset: DayToFlower.csv

Data file for the lesson can be downloaded [Here](https://figshare.com/articles/dataset/DayToFlower_csv/13622831/1) manually


```
xx <- read_csv("Downloads/DayToFlower.csv")
xx<-na.omit(xx)
yy <- xx %>%
  group_by(Name, Location) %>%
  summarise(Mean_DTF = round(mean(DTF),1)) %>% 
  arrange(Location)
yy


```
```
## # A tibble: 9 x 3
## # Groups:   Name [3]
##   Name          Location            Mean_DTF
##   <chr>         <chr>                  <dbl>
## 1 CDC Maxim AGL Jessore, Bangladesh     86.7
## 2 ILL 618 AGL   Jessore, Bangladesh     79.3
## 3 Laird AGL     Jessore, Bangladesh     76.8
## 4 CDC Maxim AGL Metaponto, Italy       134. 
## 5 ILL 618 AGL   Metaponto, Italy       138. 
## 6 Laird AGL     Metaponto, Italy       137. 
## 7 CDC Maxim AGL Saskatoon, Canada       52.5
## 8 ILL 618 AGL   Saskatoon, Canada       47  
## 9 Laird AGL     Saskatoon, Canada       56.8
```

```
yy <- yy %>% spread(key = Location, value = Mean_DTF)
yy
```

```
## # A tibble: 3 x 4
## # Groups:   Name [3]
##   Name          `Jessore, Bangladesh` `Metaponto, Italy` `Saskatoon, Canada`
##   <chr>                         <dbl>              <dbl>               <dbl>
## 1 CDC Maxim AGL                  86.7               134.                52.5
## 2 ILL 618 AGL                    79.3               138.                47  
## 3 Laird AGL                      76.8               137.                56.8
```
```
yy <- yy %>% gather(key = TraitName, value = Value, 2:4)
yy
```
```
## # A tibble: 9 x 3
## # Groups:   Name [3]
##   Name          TraitName           Value
##   <chr>         <chr>               <dbl>
## 1 CDC Maxim AGL Jessore, Bangladesh  86.7
## 2 ILL 618 AGL   Jessore, Bangladesh  79.3
## 3 Laird AGL     Jessore, Bangladesh  76.8
## 4 CDC Maxim AGL Metaponto, Italy    134. 
## 5 ILL 618 AGL   Metaponto, Italy    138. 
## 6 Laird AGL     Metaponto, Italy    137. 
## 7 CDC Maxim AGL Saskatoon, Canada    52.5
## 8 ILL 618 AGL   Saskatoon, Canada    47  
## 9 Laird AGL     Saskatoon, Canada    56.8
```
```
yy <- yy %>% spread(key = Name, value = Value)
yy

```
```
## # A tibble: 3 x 4
##   TraitName           `CDC Maxim AGL` `ILL 618 AGL` `Laird AGL`
##   <chr>                         <dbl>         <dbl>       <dbl>
## 1 Jessore, Bangladesh            86.7          79.3        76.8
## 2 Metaponto, Italy              134.          138.        137. 
## 3 Saskatoon, Canada              52.5          47          56.8
```
