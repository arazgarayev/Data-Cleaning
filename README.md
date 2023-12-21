# Data-Cleaning
Diabet Data cleaning example
attach(D)
> table(CLASS)
CLASS
  N   P   Y 
103  53 844 
> library(DataExplorer)
> plot_missing(D)
> library(plyr)
> D$CLASS <- as.factor(mapvalues(D$CLASS,from = c("P"),to=c("N")))
> table(CLASS)
CLASS
  N   P   Y 
103  53 844 
> D$CLASS=gsub("P","N",D$CLASS)
> table(CLASS)
CLASS
  N   P   Y 
103  53 844   table(CLASS)
CLASS
  N   Y 
156 844 
