# Welcome to Applied Linear Regression Models 

Here you will find the R Code and supplementary Excel files for the book titled "Applied Linear Regression Models" by Kutner, Nachtsheim and Neter. All page numbers for the examples are based on the *4th edition* of the Applied Linear Regression Models (ALRM) book.

Data sets for each chapter of ALRM 4th edition can be accessed at this link: www.cnachtsheim-text.csom.umn.edu. You may want to bookmark this link because we will reference it below. 

## Chapter 1

### Toluca Company Example on Page 19

The data set for this example can be found under Chapter 1 files and is titled "CH01TA01". And of course, since the first rule of Statistics is to always plot the data, that's where we will start. 

### Toluca Company Example Figure 1.10(a) on Page 20 
Here are two R-scripts that will allow you to create a scatter plot for the Toluca Example. 

This first script uses base R. 
```markdown

#This R script uses base R
#See the example about Toluca in the ALRM textbook

#first clean the global environment & the console 
rm(list=ls())
cat("\014")

#next import the data from the text file
TolucaDataALSM <- read.table("TolucaDataALSM.txt", sep="", header=FALSE)

#Alternatively, click "Import Dataset" under the Environment tab. 

Tolucadata <- TolucaDataALSM    #changes the name of the data frame
names(Tolucadata)[1] <- "LotSize"  #changes the column name for V1
names(Tolucadata)[2] <- "WorkHours"  #changes the column name for V2

#create a scatterplot to see if there is a linear relationship
plot(Tolucadata$LotSize, Tolucadata$WorkHours, ylab="Work Hours", xlab="LotSize",
     main="Toluca Company: Refrigeration Manufacturer") 

#plot(Tolucadata$LotSize, Tolucadata$WorkHours) also creates a scatterplot. 
#Note that the plot function assumes the first variable, i.e.,"LotSize", 
#to be the independent variable; consequently, the second variable is 
#assumed to be the dependent variable. 


``` 

The second script uses the Tidyverse pacakge in R. 



[editor on GitHub](https://github.com/leylaozsen/alrm.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.



Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/leylaozsen/alrm.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
