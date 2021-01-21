---
title: "Export your data"
teaching: 20
exercises: 20
questions:

- "How toexport my data after tidy?"


objectives:
- ""
keypoints:
- ""
- ""
---
## Work.table

```
#Save the exported file in Downloads
setwd("Downloads")
#Read your data from Downloads
xx <- read_csv("Downloads/DayToFlower.csv")
xx <- read_xlsx("Downloads/DayToFlower.xlsx", sheet = "DayToFlower")
xx<-na.omit(xx)
yy <- xx %>%
  group_by(Name, Location) %>%
  summarise(Mean_DTF = round(mean(DTF),1)) %>% 
  arrange(Location)
yy
#Your coad
yy <- yy %>% spread(key = Location, value = Mean_DTF)
yy
yy <- yy %>% gather(key = TraitName, value = Value, 2:4)
yy
yy <- yy %>% spread(key = Name, value = Value)
yy
write.table(yy,file="DataToExport.csv", sep=",")
```
![Screenshot of main code listing](../fig/Export-data-1.png)

Now your `DataToExport.csv` is saved in Downloads.
