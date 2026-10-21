---
tags: [machine-learning, programming, r]
---

Tags: [[R]] [[Programming]] [[Data 104]] [[Tidyverse]] 

## Common Commands of Tidyverse

 ### **Select**: is used to select particular columns in a data set/csv or excel file. It has many variations such as ==(Note: In place of dataset the name of the dataset should be used and in place of column numbers the name of the column)==.
     `select(dataset)` - selects the whole data set.
     `select(dataset, column3)` - selects the 3rd column only.
     `select(dataset, -column2)` - selects the whole dataset except the column 2.
     `select(dataset, starts_with("H"))` - selects the columns that start with the letter H.

Filter: is used to filter the contents of the dataset. It can be used to filter the data with different conditions ==(Note: We use df_f this time in place of dataset to show how it can have any name really)==.
     `df_f <- filter(df,Age>25)` - filters the dataset 'df' and selects only the entries who have the age value set at more than 25.
     `df_f <- filter(df, Gender == 'F' & Height > 160)` - filters the dataset and selects the entry which has both gender as 'F' and Height more than 160.
     `df_f <- filter(df, City == 'New York' || Age > 30)` - filters the dataset with or operator that means it choose the values for which the city is new york or the values which have age > 30.
     `df_filtered <- filter(df, City %in% c('Chicago', 'Houston'))` - filters the dataset and will return rows where the `City` is either "Chicago" or "Houston".

Mutate: 

 