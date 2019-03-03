Random Draw
================

This is a simple script that randomly selects column values and creates
a new row from a given data frame.

### Script

`df` refers to the given data frame, `n` refers to the number of columns
in your data frame.

``` r
result <- function(df,n) {
  set.seed(700)
  df[] <- lapply(df, as.character)
  some_vector<-rep(NA,n)
  for (i in 1:n) {
    some_vector[i]<-sample(df[[i]],1)
  }
  imputed_row<-rbind(some_vector)
  return(imputed_row)
}
```

### Example

``` r
am<-matrix(1:9, nrow = 3, ncol = 3)
am.df<-as.data.frame(am)
am.df
```

    ##   V1 V2 V3
    ## 1  1  4  7
    ## 2  2  5  8
    ## 3  3  6  9

Now the `result` function will create a new row by randomly selecting
values from the data frame `am.df`.

``` r
result(am.df,3)
```

    ##             [,1] [,2] [,3]
    ## some_vector "2"  "4"  "8"
