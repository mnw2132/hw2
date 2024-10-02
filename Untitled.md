p8105_hw2_mnw2132
================
Mary Williams
2024-09-30

## Problem 1

*Bring data in and begin cleaning*

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   3.5.1     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.1
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
transit_data = read_csv(file = "/Users/nickywilliams/Desktop/hw2/NYC_Transit_Subway_Entrance_And_Exit_Data.csv")%>%
  janitor::clean_names()
```

    ## Rows: 1868 Columns: 32
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (22): Division, Line, Station Name, Route1, Route2, Route3, Route4, Rout...
    ## dbl  (8): Station Latitude, Station Longitude, Route8, Route9, Route10, Rout...
    ## lgl  (2): ADA, Free Crossover
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
  na=c(".","NA","")
```

*read data*

``` r
transit_data
```

    ## # A tibble: 1,868 × 32
    ##    division line   station_name station_latitude station_longitude route1 route2
    ##    <chr>    <chr>  <chr>                   <dbl>             <dbl> <chr>  <chr> 
    ##  1 BMT      4 Ave… 25th St                  40.7             -74.0 R      <NA>  
    ##  2 BMT      4 Ave… 25th St                  40.7             -74.0 R      <NA>  
    ##  3 BMT      4 Ave… 36th St                  40.7             -74.0 N      R     
    ##  4 BMT      4 Ave… 36th St                  40.7             -74.0 N      R     
    ##  5 BMT      4 Ave… 36th St                  40.7             -74.0 N      R     
    ##  6 BMT      4 Ave… 45th St                  40.6             -74.0 R      <NA>  
    ##  7 BMT      4 Ave… 45th St                  40.6             -74.0 R      <NA>  
    ##  8 BMT      4 Ave… 45th St                  40.6             -74.0 R      <NA>  
    ##  9 BMT      4 Ave… 45th St                  40.6             -74.0 R      <NA>  
    ## 10 BMT      4 Ave… 53rd St                  40.6             -74.0 R      <NA>  
    ## # ℹ 1,858 more rows
    ## # ℹ 25 more variables: route3 <chr>, route4 <chr>, route5 <chr>, route6 <chr>,
    ## #   route7 <chr>, route8 <dbl>, route9 <dbl>, route10 <dbl>, route11 <dbl>,
    ## #   entrance_type <chr>, entry <chr>, exit_only <chr>, vending <chr>,
    ## #   staffing <chr>, staff_hours <chr>, ada <lgl>, ada_notes <chr>,
    ## #   free_crossover <lgl>, north_south_street <chr>, east_west_street <chr>,
    ## #   corner <chr>, entrance_latitude <dbl>, entrance_longitude <dbl>, …

``` r
names(transit_data)
```

    ##  [1] "division"           "line"               "station_name"      
    ##  [4] "station_latitude"   "station_longitude"  "route1"            
    ##  [7] "route2"             "route3"             "route4"            
    ## [10] "route5"             "route6"             "route7"            
    ## [13] "route8"             "route9"             "route10"           
    ## [16] "route11"            "entrance_type"      "entry"             
    ## [19] "exit_only"          "vending"            "staffing"          
    ## [22] "staff_hours"        "ada"                "ada_notes"         
    ## [25] "free_crossover"     "north_south_street" "east_west_street"  
    ## [28] "corner"             "entrance_latitude"  "entrance_longitude"
    ## [31] "station_location"   "entrance_location"

*clean data*

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Problem 2

You can also embed plots, for example:

![](Untitled_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.

## Problem 3
