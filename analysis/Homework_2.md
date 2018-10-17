Homework 2
================

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
data <- read_tsv("../data/example_dataset_2.tsv") %>% 
  print()
```

    ## Parsed with column specification:
    ## cols(
    ##   strain = col_character(),
    ##   mean_yfp = col_integer(),
    ##   mean_rfp = col_integer()
    ## )

    ## # A tibble: 16 x 3
    ##    strain  mean_yfp mean_rfp
    ##    <chr>      <int>    <int>
    ##  1 schp688     1748    20754
    ##  2 schp684     3294    20585
    ##  3 schp690     3535    20593
    ##  4 schp687     4658    20860
    ##  5 schp686     5000    21171
    ##  6 schp685     7379    22956
    ##  7 schp683     9365    23866
    ##  8 schp689     8693    22649
    ##  9 schp679     2528    19906
    ## 10 schp675     3687    20438
    ## 11 schp681     3705    20227
    ## 12 schp678     4378    20630
    ## 13 schp677     3967    20604
    ## 14 schp676     2657    20223
    ## 15 schp674     1270    20316
    ## 16 schp680     1117    19377

``` r
data <- data %>%
  mutate(mean_ratio = mean_yfp / mean_rfp) %>%
  print()
```

    ## # A tibble: 16 x 4
    ##    strain  mean_yfp mean_rfp mean_ratio
    ##    <chr>      <int>    <int>      <dbl>
    ##  1 schp688     1748    20754     0.0842
    ##  2 schp684     3294    20585     0.160 
    ##  3 schp690     3535    20593     0.172 
    ##  4 schp687     4658    20860     0.223 
    ##  5 schp686     5000    21171     0.236 
    ##  6 schp685     7379    22956     0.321 
    ##  7 schp683     9365    23866     0.392 
    ##  8 schp689     8693    22649     0.384 
    ##  9 schp679     2528    19906     0.127 
    ## 10 schp675     3687    20438     0.180 
    ## 11 schp681     3705    20227     0.183 
    ## 12 schp678     4378    20630     0.212 
    ## 13 schp677     3967    20604     0.193 
    ## 14 schp676     2657    20223     0.131 
    ## 15 schp674     1270    20316     0.0625
    ## 16 schp680     1117    19377     0.0576
