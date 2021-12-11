---
title: "Visualizing Text and Distributions"
author: "Orel Yoshia `oyoshia3972@floridapoly.edu`"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
---

# Data Visualization Project 03


In this exercise you will explore methods to visualize text data and practice how to recreate charts that show the distributions of a continuous variable. 


```r
library(tidyverse)
library(lubridate)
library(dplyr)
library(ggridges)
```



## Part 1: Density Plots

Using the dataset obtained from FSU's [Florida Climate Center](https://climatecenter.fsu.edu/climate-data-access-tools/downloadable-data), for a station at Tampa International Airport (TPA) from 2016 to 2017, attempt to recreate the charts shown below


```r
weather_tpa <- read_csv("https://github.com/reisanar/datasets/raw/master/tpa_weather_16_17.csv")
# random sample 
sample_n(weather_tpa, 4)
```

```
## # A tibble: 4 x 6
##    year month   day precipitation max_temp min_temp
##   <dbl> <dbl> <dbl>         <dbl>    <dbl>    <dbl>
## 1  2016     1    15          0.54       73       62
## 2  2016     1    11          0          60       44
## 3  2016     9     4          0          91       77
## 4  2016     2     3          0          84       69
```


See https://www.reisanar.com/slides/relationships-models#10 for a reminder on how to use this dataset with the `lubridate` package for dates and times.

(a) Recreate the plot below:

<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_facet.png" width="80%" style="display: block; margin: auto;" />
Hint: the option `binwidth = 3` was used with the `geom_histogram()` function.


<img src="Yoshia_Orel_project_03_files/figure-html/solution_A-1.png" width="80%" style="display: block; margin: auto;" />

(b) Recreate the plot below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_density.png" width="80%" style="display: block; margin: auto;" />
Hint: check the `kernel` parameter of the `geom_density()` function, and use `bw = 0.5`.

<img src="Yoshia_Orel_project_03_files/figure-html/solution_B-1.png" width="80%" style="display: block; margin: auto;" />


(c) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_density_facet.png" width="80%" style="display: block; margin: auto;" />
Hint: default options for `geom_density()` were used. 

<img src="Yoshia_Orel_project_03_files/figure-html/solution_C-1.png" width="80%" style="display: block; margin: auto;" />



(d) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges.png" width="80%" style="display: block; margin: auto;" />
Hint: default options for `geom_density()` were used. 


```
## Picking joint bandwidth of 1.49
```

<img src="Yoshia_Orel_project_03_files/figure-html/solution_D-1.png" width="80%" style="display: block; margin: auto;" />


(e) Recreate the plot below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges.png" width="80%" style="display: block; margin: auto;" />
Hint: use the`ggridges` package, and the `geom_density_ridges()` function paying close attention to the `quantile_lines` and `quantiles` parameters.


```
## Picking joint bandwidth of 1.49
```

<img src="Yoshia_Orel_project_03_files/figure-html/solution_E-1.png" width="80%" style="display: block; margin: auto;" />


(f) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges_plasma.png" width="80%" style="display: block; margin: auto;" />
Hint: this uses the `plasma` option (color scale) for the _viridis_ palette.


```
## Picking joint bandwidth of 1.49
```

<img src="Yoshia_Orel_project_03_files/figure-html/solution_F-1.png" width="80%" style="display: block; margin: auto;" />



## Part 2: Visualizing Text Data

I have done visualizing text data in Mini Project 01 and Mini Project 02 if you would like to see some examples :)
