---
layout: post
title: Pandas Basic Commands
---

Read csv file:
```
all = pd.read_csv(
    "export-2020-02-13-T-13-58-18.csv",
    skiprows=8, # skip the first 8 rows
    nrows=16, # read the next 16 rows
)
```

Merge two dataframes by a certain column:
```
pd.merge(df1, df2, on='company')
```

Display a slice of the data
```
all.head()
```

Rename column from "Unnamed: 0" to "State" for the data set called "all":
```
all = all.rename(columns={"Unnamed: 0": "State"})
```

Remove columns:
```
data = data.drop(["Y2001", "Y2002", "Y2003"], axis=1)
```

Reshape data from wide to long:
```
all = pd.wide_to_long(all, stubnames="", i="State", j="Year")
```

Change multilevel index to single level:
```
all = all.reset_index()
```

Check data type:
```
all.dtypes
```

Change data type. Note that NaN can only be changed into float but not into integer.
```
all['ER Visits'] = all['ER Visits'].astype(float)
```

Sort values:
```
avg.sort_values("perc_gun", inplace = True, ascending=False) 
```

Replace values:
```
all.replace(0, 5)
```