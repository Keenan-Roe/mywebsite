---
title: Test
categories:
- Test
- Regression
author: Keenan Roe
date: '2021-10-03'
description: This is meta description.
draft: false
image: images/portfolio/item-1.png
tags: []
---


Now is the time to do this 

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

```{r eval=FALSE, echo=FALSE}
library(corrplot)
library(aod)
library(ggplot2)
```

```{r eval=TRUE, echo=FALSE}

mydata<- read.csv("diabetes2.csv")
attach(mydata)
summary(mydata)

dataIQR<-sapply(mydata, IQR)

boxplot(mydata)

boxplot(BloodPressure, Glucose, names = c("Blood Pressure", "Glucose"), col=c("Red", "Gold"))

boxplot(SkinThickness, BMI, Age, Pregnancies, names=c("Skin Thiccness", "BMI", "Age", "Pregnancies"), col=c("Magenta", "darkslategray1", "lightsalmon", "blue"))

boxplot(Insulin, col=c("Red"))

length(Insulin)
boxplot(Insulin[!Insulin %in% boxplot.stats(Insulin)$out])

newVect<-Insulin[!Insulin %in% boxplot.stats(Insulin)$out & Insulin!=0]
newVect1<-Outcome[!Insulin %in% boxplot.stats(Insulin)$out & Insulin!=0]

boxplot(newVect~newVect1, col=c("blue"), border=c("red") , frame=F)

```
