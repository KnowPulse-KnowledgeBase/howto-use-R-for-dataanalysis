---
title: "Export your data"
teaching: 20
exercises: 20
questions:

- "How to export my data after tidy?"


objectives:
- "Export a tidy file from R"
keypoints:
- "Make sure you have "
- "Exported file can be saved in different formats through the change of separator."
---
## `Work.table` Command to export your data from R

### We are aiming to output the `.csv` file we have tidied from last episode.

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

## Now your `DataToExport.csv` is saved in Downloads.
![Screenshot of main code listing](../fig/Export-data-2.png)

## To remove row name
```
write.table(yy,file="DataToExport.csv", row.names=F, sep=",")
```
![Screenshot of main code listing](../fig/Export-data-3.png)
* The old file is overwritten by the new one, so you only get one `DataToExport.csv`. 
