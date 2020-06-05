
# Chapter 1

## Toluca Company Example on Page 19

The data set for this example is titled "CH01TA01". You will find "CH01TA01" at this link [DataSetsForAllChapters](http://www.cnachtsheim-text.csom.umn.edu). You may want to bookmark this link because we will reference this link for all  chapters. 

## Toluca Company Example Figure 1.10(a) on Page 20 
And of course, since the first rule of Statistics is to always plot the data, that's where we will start. Here are two R-scripts that will allow you to create a scatter plot for the Toluca Example. 

1. This first script uses base R. 

```markdown

#This R script uses base R

#first clean the global environment & the console 
rm(list=ls())
cat("\014")

#next import the data from the text file
TolucaDataALSM <- read.table("TolucaDataALSM.txt", sep="", header=FALSE)
#Alternatively, click "Import Dataset" under the Environment tab. 

Tolucadata <- TolucaDataALSM    #changes the name of the data frame

#take a look at the summary view of the data we imported
str(TolucaDataALSM)
#You will see that the columns don't have names so let's name the columns

names(Tolucadata)[1] <- "LotSize"  #changes the column name for V1
names(Tolucadata)[2] <- "WorkHours"  #changes the column name for V2

#create a scatterplot to see if there is a linear relationship
#the line below will create a scatter plot, generating Figure 1.10(a)
plot(Tolucadata$LotSize, Tolucadata$WorkHours, ylab="Work Hours", xlab="LotSize",
     main="Toluca Company: Refrigeration Manufacturer") 

#plot(Tolucadata$LotSize, Tolucadata$WorkHours) also creates a scatterplot. 
#Note that this plot function assumes the first variable, i.e.,"LotSize", 
#to be the independent variable; consequently, the second variable is 
#assumed to be the dependent variable. So pay attention to the order of 
#the arguments for the plot function; alternatively use the cleaner line 
#of code and explicity define x and y axis by entering the values for 
#ylab and xlab as shown above. 
``` 


2. The second script uses the Tidyverse package in R. 

```markdown

# Before you run the code, you will need to install and load tidyverse and ggplot2 packages 
install.packages("tidyverse")
install.packages("ggplot2")
library(tidyverse)
library(ggplot2)


#First clean the global environment & the console 
rm(list=ls())
cat("\014")

#next import the data from the text file
TolucaData <- read.table("CH01TA01.txt", sep="", header=FALSE)

#take a look at the summary view of the data we imported
glimpse(TolucaData)

#You will see that the columns don't have names so let's name the columns
names(TolucaData) <-  c("LotSize", "Hours")
glimpse(TolucaData) 

#create a scatterplot to see if there is a linear relationship between LotSize and Hours. 
#The line below will create a scatter plot, generating Figure 1.10.a.
plot <- ggplot(TolucaData, aes(LotSize,Hours)) 
plot + geom_point()

```

## Toluca Company Example Figure 1.10(b) on Page 20 

Now, we will add the fitted regression line to the scatter plot to generate Figure 1.10(b)

1. This first script uses base R. 

```markdown

#fit a linear model
lmfit <- lm(WorkHours~LotSize, data=Tolucadata) 
# for lmfit function, the first argument is the response variable 
# and the second argument is the independent variable
# the order is switched from the plotfunction 

#add the regression line to the plot
abline(lmfit)

```

2. The second script uses the Tidyverse package in R.

```markdown

#add the regression line to the plot generating Figure 1.10.b
ggplot(data = TolucaData) +
  geom_point(mapping = aes(x=LotSize, y=Hours)) +
  geom_smooth(mapping = aes(x=LotSize, y=Hours), method=lm)
  
  
```

## Toluca Company Example Figure 1.11 on Page 20 
 
```markdown

#finally, summarize the output of the regression, generating Figure 1.11
summary(lmfit) 

```

## Toluca Company Example Tables 1.1. and 1.2 on Pages 19 and 20

The Excel file illustrating the computations shown in Table 1.1. and 1.2. can be accessed [here](http://www.cnachtsheim-text.csom.umn.edu). The computation for the example on pages 21 and 22 are also included in this Excel file. 

