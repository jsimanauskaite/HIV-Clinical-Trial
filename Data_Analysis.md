Data Analysis
================
<<<<<<< HEAD
=======
Juste Simanauskaite & Patricia Rivera
>>>>>>> 7cef86ad2399b55ae3e3ade50cdbbd37e007e49f

``` r
knitr::opts_chunk$set(message=FALSE, warning=FALSE, fig.height=3, fig.width=5, fig.align="center")
library(tidyverse)
library(broom)
library(plyr)
<<<<<<< HEAD
=======
library(survival)
library(survminer)
>>>>>>> 7cef86ad2399b55ae3e3ade50cdbbd37e007e49f
aids <- read.csv( "http://pages.pomona.edu/~jsh04747/courses/math150/AIDSdata.csv")

summary(aids)
```

    ##        id              time           censor            time_d     
    ##  Min.   :   1.0   Min.   :  1.0   Min.   :0.00000   Min.   :  1.0  
    ##  1st Qu.: 287.5   1st Qu.:179.5   1st Qu.:0.00000   1st Qu.:199.5  
    ##  Median : 581.0   Median :257.0   Median :0.00000   Median :266.0  
    ##  Mean   : 579.5   Mean   :231.8   Mean   :0.08108   Mean   :243.4  
    ##  3rd Qu.: 873.0   3rd Qu.:300.0   3rd Qu.:0.00000   3rd Qu.:306.0  
    ##  Max.   :1156.0   Max.   :362.0   Max.   :1.00000   Max.   :362.0  
    ##     censor_d            tx             txgrp           strat2      
    ##  Min.   :0.0000   Min.   :0.0000   Min.   :1.000   Min.   :0.0000  
    ##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:1.000   1st Qu.:0.0000  
    ##  Median :0.0000   Median :1.0000   Median :2.000   Median :1.0000  
    ##  Mean   :0.0235   Mean   :0.5041   Mean   :1.504   Mean   :0.6157  
    ##  3rd Qu.:0.0000   3rd Qu.:1.0000   3rd Qu.:2.000   3rd Qu.:1.0000  
    ##  Max.   :1.0000   Max.   :1.0000   Max.   :2.000   Max.   :1.0000  
    ##       sex            raceth          ivdrug         hemophil      
    ##  Min.   :1.000   Min.   :1.000   Min.   :1.000   Min.   :0.00000  
    ##  1st Qu.:1.000   1st Qu.:1.000   1st Qu.:1.000   1st Qu.:0.00000  
    ##  Median :1.000   Median :1.000   Median :1.000   Median :0.00000  
    ##  Mean   :1.157   Mean   :1.706   Mean   :1.317   Mean   :0.03408  
    ##  3rd Qu.:1.000   3rd Qu.:2.000   3rd Qu.:1.000   3rd Qu.:0.00000  
    ##  Max.   :2.000   Max.   :5.000   Max.   :3.000   Max.   :1.00000  
    ##      karnof            cd4            priorzdv           age       
    ##  Min.   : 70.00   Min.   :  0.00   Min.   :  3.00   Min.   :15.00  
    ##  1st Qu.: 90.00   1st Qu.: 22.25   1st Qu.: 11.00   1st Qu.:33.00  
    ##  Median : 90.00   Median : 75.00   Median : 21.00   Median :38.00  
    ##  Mean   : 91.34   Mean   : 86.45   Mean   : 30.63   Mean   :38.81  
    ##  3rd Qu.:100.00   3rd Qu.:135.75   3rd Qu.: 44.00   3rd Qu.:44.00  
    ##  Max.   :100.00   Max.   :348.00   Max.   :288.00   Max.   :73.00

``` r
hist(aids$time)
<<<<<<< HEAD
```

![](Data_Analysis_files/figure-markdown_github/global_options-1.png)
=======

aids_fit_time <- survfit(Surv(time, censor) ~ sex, data=aids)
ggsurvplot(aids_fit_time, data=aids,  conf.int = TRUE)
```

![](Data_Analysis_files/figure-markdown_github/global_options-1.png)![](Data_Analysis_files/figure-markdown_github/global_options-2.png)

``` r
aids_fit_time.d <- survfit(Surv(time_d, censor_d) ~ sex, data=aids)
ggsurvplot(aids_fit_time.d, data=aids,  conf.int = TRUE)
```

![](Data_Analysis_files/figure-markdown_github/global_options-3.png)
>>>>>>> 7cef86ad2399b55ae3e3ade50cdbbd37e007e49f
