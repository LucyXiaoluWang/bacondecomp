# bacon

## Overview

`bacon` is a package with tools to perform the Goodman-Bacon decomposition for differences-in-differences with variation in treatment timing.

## Functions
* `bacon()`: calculates all 2x2 differences-in-differences estimates and weights for the Bacon-Goodman decomposition.

## Data
* `math_refom`: A data set containing state/year level data on an educational reform and future income.
* `castle`: A data set containing state/year level data on a crime reform.

## Installation
``` r
library(devtools)
install_github("evanjflack/bacon")
```

## Usage
```r
df_bacon <- bacon(incearnl_ln ~ reform_math,
                  data = bacon::math_reform,
                  id_var = "state",
                  time_var = "class")

ggplot(df_bacon) +
  aes(x = weight, y = estimate, shape = factor(type)) +
  labs(x = "Weight", y = "Estimate", shape = "Type") +
  geom_point()

```
