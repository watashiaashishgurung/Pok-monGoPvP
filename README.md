Long time ago I made a power point presentation to work on my presentational skills about our favorite childhood game. Pokémon Go.
Have a look at the slides and enjoy th eshow.  "imagination is more important than knowledge" - Einstein


---
title: "Master League Top 10 types"
author: "Aashish Gurung"
date: "2024-02-21"
output: html_document
---
## Hello, world! This is me, life should be, fun for every one!
### In this exercise we are going to make a predictive model for Master league pokemon encounters
### For this analysis install the tidyverse packages and the libraries listed below

```{r}
library(tidyverse)
library(ggplot2)
library(readr)
```
#### after installation and loading the libraries please upload the pvpdataset "cp10000_all_overall_rankings"
#### You can find the this file in at the location following desktop>CASE_STUDY>pvpdata>cp10000_all_overall_rankings.csv or inform presentation on how to download it immidiatly from pvpoke.com

#### Rename the dataset cp10000_all_overall_rankings.csv to mlpvp.csv
```{r}
mlpvp <- cp10000_all_overall_rankings
```

#### Clean the dataset
first we are going to change the column names with colnames() function

```{r}
            colnames(mlpvp) [2]<- "score"
            colnames(mlpvp) [4] <- "type_1"
            colnames(mlpvp) [5] <- "type_2"
            colnames(mlpvp) [12] <- "fastmove"
            colnames(mlpvp) [9] <- "statproduct"
            colnames(mlpvp) [13] <- "chargemove1"
            colnames(mlpvp) [14] <- "chargemove2"
            colnames(mlpvp) [15] <- "chargemove1count"
            colnames(mlpvp) [16] <- "chargemove2count"
            colnames(mlpvp) [17] <- "buddydistance"
            colnames(mlpvp) [18] <- "chargemovecost"
```
## making copy of mlpvp
```{r}
copymlpvp <- mlpvp
```
## filtering the top 100 

based on pvpoke.ranking on feb 18 these are pokemon with score >= 75.2
naming this new table "top100"

```{r}
top100 <- copymlpvp %>% filter(score >=75.2)
```

## make copy of top100 
```{r}
copytop100 <- top100
```
## count number per type_1 in top 100

```{r}
top_type_100 <- copytop100 %>% count(type_1)
```
## naming n as num_per_type with colnames() function

```{r}
colnames(top_type_100) [2] <- "number_of_type"
```
## arranging num_of_type column desc order and naming this new table top_type_100_arranged

```{r}
top_type_100_arranged <- top_type_100 %>%  arrange(-number_of_type)
```
##
selecting top 10 types with top_n() function, it automatically selects by number_of_type

################
```{r}
top_10_types <- top_type_100_arranged %>% top_n(10)
```
## now we have the top 10 types in the ML PvP
```{r}
View(top_10_types)
```
## data visualisation
```{r}
ggplot(top_10_types) + geom_point(mapping = aes(x=type_1, y=number_of_type, color=type_1))
```


