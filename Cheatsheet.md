####Compute Summary Statistics of Data Subsets

**aggregate**

```
# aggregate data frame mtcars by cyl and vs, returning means
# for numeric variables
attach(mtcars)
aggdata <-aggregate(mtcars, by=list(cyl,vs), 
  FUN=mean, na.rm=TRUE)
print(aggdata)
detach(mtcars)
```


#dplyr
======

Start by rewarpping the file in **table_df**,**table_dt**,**table_sql** for smaller print results.

####Select columns (variables) from the dataset

**select**

```
iris <- tbl_df(iris)
select(iris, Petal.Length, Petal.Width) ##select variables in this order, no iris$Petal.Length needed
select(iris, Petal.Length:Petal.Width) ##Select variables between these 2 columns
select(iris, -Petal.Length, -Petal.Width) ##Select variables excluding these 2 columns
select(iris, -(Petal.Length:Petal.Width)) ##Select variables excluding columns between these 2
select(iris, contains("etal"))
```

####kl

**filter**

```

```

####kl

**arrange**

```

```

####kl

**mutate**

```

```

####kl

**summarize**

```

```
