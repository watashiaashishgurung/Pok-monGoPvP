# Master League Top 10 Types

Author: Aashish Gurung  
Date: 2024-02-21  

---

## Introduction

Welcome to my presentation on Master League Pokémon encounters in Pokémon Go. This exercise involves creating a predictive model for these encounters.

"Imagination is more important than knowledge." - Albert Einstein

## Setup

To begin, install the `tidyverse` package and load the necessary libraries.

```{r}
library(tidyverse)
library(ggplot2)
library(readr)
```
# Data Preparation
First, upload the PvP dataset "cp10000_all_overall_rankings.csv". You can find this file at the following location: desktop>CASE_STUDY>pvpdata>cp10000_all_overall_rankings.csv. Alternatively, you can download it directly from pvpoke.com.

## Rename the dataset to mlpvp.csv.
```{r}
mlpvp <- read_csv("cp10000_all_overall_rankings.csv")
```
## Clean the Dataset
Change the column names using the colnames() function.
```{r}
colnames(mlpvp)[2] <- "score"
colnames(mlpvp)[4] <- "type_1"
colnames(mlpvp)[5] <- "type_2"
colnames(mlpvp)[12] <- "fastmove"
colnames(mlpvp)[9] <- "statproduct"
colnames(mlpvp)[13] <- "chargemove1"
colnames(mlpvp)[14] <- "chargemove2"
colnames(mlpvp)[15] <- "chargemove1count"
colnames(mlpvp)[16] <- "chargemove2count"
colnames(mlpvp)[17] <- "buddydistance"
colnames(mlpvp)[18] <- "chargemovecost"
```
## Create a Copy of the Dataset

```{r}
copymlpvp <- mlpvp
```
## Filter the Top 100 Pokémon
Based on the PvPoke ranking from February 18, filter for Pokémon with a score greater than or equal to 75.2. Name this new table top100.

```{r}
top100 <- copymlpvp %>% filter(score >= 75.2)
```

## Create a Copy of the Top 100 Dataset

```{r}
copytop100 <- top100
``
## Count the Number of Pokémon per Type

```{r}
top_type_100 <- copytop100 %>% count(type_1)
```
## Rename the Count Column
Rename the count column to number_of_type using the colnames() function.

```{r}
colnames(top_type_100)[2] <- "number_of_type"
```

## Arrange the Types in Descending Order
Arrange the number_of_type column in descending order and name this new table top_type_100_arranged.

```{r}
top_type_100_arranged <- top_type_100 %>% arrange(desc(number_of_type))
```

## Select the Top 10 Types
Select the top 10 types using the top_n() function. It automatically selects by number_of_type.

```{r}
top_10_types <- top_type_100_arranged %>% top_n(10)
```

## View the Top 10 Types
```{r}
View(top_10_types)
```

# Data Visualization
Visualize the top 10 types using ggplot2.

```{r}
ggplot(top_10_types) +
  geom_point(mapping = aes(x = type_1, y = number_of_type, color = type_1))
```
