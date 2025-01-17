Package Development Lab Day 1
================
Joyce Robbins

# Create a package

1.  Create the package

``` r
library(devtools)
# adjust the path as you wish, just don't create a package
# inside another project, package, or repo
create_package("~/covidtime")  
```

2.  Create the following function and save it as `day.R` in the R
    folder:

``` r
whatdayisit <- function() {
  format(Sys.Date(), "%A, %B %d, %Y")
}
```

3.  Run:

``` r
library(devtools)
load_all()
```

4.  Test the function:

``` r
whatdayisit()
```

5.  Make some changes and repeat 3. and 4.

# Document and install

1.  Edit `DESCRIPTION`

It should look something like this, with *your* name and email address.
*Don’t remove what looks like an extra comma in* `Authors@R`.

    Package: covidtime
    Title: Helps reduce pandemic induced temporal disintegration
    Version: 0.0.0.9000
    Authors@R: 
        person("first", "last", , "first.last@example.com", role = c("aut", "cre"))
    Description: Tools for regaining temporal orientation.
    License: `use_mit_license()`, `use_gpl3_license()` or friends to pick a
        license
    Encoding: UTF-8
    Roxygen: list(markdown = TRUE)
    RoxygenNote: 7.1.2

2.  Open `day.R`. Put the cursor inside the function and click “Code…
    Insert Roxygen Skeleton”. Add to the documentation so it looks
    something like this:

<!-- -->

    #' Returns the current day and date nicely formatted
    #'
    #' @return character string with day and date
    #' 
    #' @export
    #'
    #' @examples
    #' whatdayisit()
    #' 

3.  Run:

``` r
document()
```

4.  Run:

``` r
install()
```

Check that it appears in your list of packages.

5.  Close the project and try using your package!

``` r
library(covidtime)
whatdayisit()
```
