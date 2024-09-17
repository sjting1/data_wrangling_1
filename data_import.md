Data Import
================

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

To insert a code chunk, can press “option command i”. The code chunk
above is called “r setup”

## Read in some data

*A relative vs. absolute path*: A relative path example: tell it to go
to the data file then find the FAS_litters.csv. An absolute path
example: tell it to go to hard drive, then to users folder, then etc…
Recommend use relative; they’re stable

Read in the litters dataset.

``` r
litters_df = read_csv("./data/FAS_litters.csv")
```

    ## Rows: 49 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (2): Group, Litter Number
    ## dbl (6): GD0 weight, GD18 weight, GD of Birth, Pups born alive, Pups dead @ ...
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
litters_df = janitor::clean_names(litters_df)
#overwrite the original "litters_df" in line 18. load the clean_name function which is in the janitor package. Can load janitor package with tidyverse above but we only want the clean_name function so we write it with the ::.
```

“read_csv()” function exist in the reader package. Insert the relative
path in the bracket. “.” means from the starting point, go to data
folder, and look at the FAS_litters csv file.

## Take a look at the data
