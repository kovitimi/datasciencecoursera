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

####Subset rows/ Return rows with matching conditions

**filter**

```
mtcars<-tbl_df(mtcars)
filter(mtcars, cyl == 8) ##No need to specify mtcars$cyl
filter(mtcars, cyl < 6)
filter(mtcars, cyl < 6, hp < 4) ##Can specifiy as many conditions as I want
filter(mtcars, cyl < 6 | hp < 4) ##Can use logical operators like OR | 
filter(mtcars, !is.na(gear)) ##Filter NA-s no need for ...$...
```

####Arrange rows by values of variables

**arrange**

```
arrange(mtcars, cyl, disp) ##Ascending order first according to cyl then according ot disp
arrange(mtcars, desc(disp)) ##Arranging in descending order
```

####Creates new variables and transforms variables in the dataset

**mutate**

```
mutate(mtcars, displ_l = disp / 61.0237) 
mutate(mtcars, displ_l = disp / 61.0237, disp_m = disp_l / 5.12) ##Can create multiple new variables in a row

```

####Summarise multiple values to a single value (collapse a dataset into a row)

**summarize**

```
summarize(mtcars, mean(disp))
summarize(group_by(mtcars, cyl), mean(disp)) ##
summarize(group_by(mtcars, cyl), m = mean(disp), sd = sd(disp))
```

####Group a tbl by one or more variables

**group_by**

```

```

#Relation operators
======
|Relation operators|
|----------|
|x < y|
|x > y|
|x <= y|
|x >= y|
|x == y|
|x != y|

#Functions

##Numeric Functions


| Functions       | Description           | 
| ------------- |:-------------:| 
abs(x)|	absolute value
sqrt(x)|	square root
ceiling(x)|	ceiling(3.475) is 4
floor(x)|	floor(3.475) is 3
trunc(x)|	trunc(5.99) is 5
round(x, digits=n)|	round(3.475, digits=2) is 3.48
signif(x, digits=n)|	signif(3.475, digits=2) is 3.5
cos(x), sin(x), tan(x)|	also acos(x), cosh(x), acosh(x), etc.
log(x)|	natural logarithm
log10(x)|	common logarithm
exp(x)|	e^x

