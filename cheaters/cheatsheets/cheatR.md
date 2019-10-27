{
    "layout": "multicolumn"
}
%%%END

### R

#### general

task            | example           | notes
----------------|-------------------|---------------------
help            | `?sd`             |
show variables  | `ls()`            | list objects in env
var assignment  | `a = 4` `b <- 17` | 
change dir      |                   | select in UI
work dir        | `getwd()`         |
delete variable | `rm(WHO)`         | saves memory   

#### basics

task            | example                       | notes
----------------|-------------------------------|----------------------
vector or list  | `c(2,3,5)`  `c("one","two")`  | combine, single type
sequence        | `seq(0, 100, 2)`              | 0, 2, 4, 6, ..., 100
data frame      | `data.frame(colA, colB)`      | 
append row      | `rbind(frameOld, frameNew)`   | vector, matrix, frame
append column   | `cbind(frameOld, frameNew)`   | vector, matrix, frame

```R
Country = c("Brazil", "China", "India", "Switzerland", "USA")
LifeExpectancy = c(74, 76, 65, 83, 79)
CountryData = data.frame(Country, LifeExpectancy)
CountryData$Population = c(199000, 1390000, 1240000, 7997, 318000)
NewCountryData = data.frame(Country, LifeExpectancy, Population)
AllCountryData = rbind(CountryData, NewCountryData)
```

#### data

task            | example                         | notes
----------------|---------------------------------|----------------------
read csv        | `WHO = read.csv("WHO.csv")`     | change to dir first
show structure  | `str(WHO)`                      | 
show summary    | `summary(WHO)`                  |
show variables  | `names(UDSA)`                   |
find value      | `match("value", USDA$Desc`      |
subset          | `subset(WHO, Region == Europe)` |
write csv       | `write.csv(frameA, "out.csv")`  |

```R
WHO = read.csv("WHO.csv")
str(WHO)
summary(WHO)
WHO_Europe = subset(WHO, Region == "Europe")
str(WHO_Europe)
write.csv(WHO_Europe, "WHO_Europe.csv")
rm(WHO_Europe)
USDA$Description[match("CAVIAR", USDA$Sodium)]
```

#### analyisis

task               | example                    | notes
-------------------|----------------------------|----------------------------
data frame column  | `WHO$Under15`              | 
mean               | `mean(WHO$Under15)`        |
standard deviation | `sd(WHO$Under15)`          |
summary            | `summary(WHO$Under15)`     | min, quantile, median, max 
which              | `which.min(WHO$Under15)`   | returns index (1 first)
show index         | `WHO$Country[86]`          | 
plot               | `plot(frame$X, frame$Y)`   | scatterplot
subset multi cond. | `subset(frame, a>2 & b>6)` |
number of rows     | `nrow(frame)`              |
frame subset       | `frame[c(colA, colB)]`     |

```R
mean(WHO$Under15)
sd(WHO$Under15)
summary(WHO$Under15)
which.min(WHO$Under15)
WHO$Country[86]
which.max(WHO$Under15)
WHO$Country[124]
plot(WHO$GNI, WHO$FertilityRate)
Outliers = subset(WHO, GNI > 10000 & FertilityRate > 2.5) 
nrow(Outliers)
Outliers[c("Country","GNI","FertilityRate")]
sd(USDA$Sodium, na.rm=TRUE)
```

#### plots

task        | example                                | notes
------------|----------------------------------------|---------------------
histogram   | `hist(WHO$CellSubs)`                   | distribution 
boxplot     | `boxplot(WHO$LifeExpect ~ WHO$Region)` | statistical range
table       | `table(WHO$Region)`                    | few values
table apply | `tapply(WHO$Over60, WHO$Region, mean)` |

```R
hist(WHO$CellularSubscribers)
boxplot(WHO$LifeExpectancy ~ WHO$Region)
boxplot(WHO$LifeExpectancy ~ WHO$Region, 
    xlab = "", ylab = "Life Expectancy", 
    main = "Life Expectancy of Countries by Region")
table(WHO$Region)
tapply(WHO$Over60, WHO$Region, mean)
tapply(WHO$LiteracyRate, WHO$Region, min)
tapply(WHO$LiteracyRate, WHO$Region, min, na.rm=TRUE)
```

$$a^2 + b^2 = c^2$$