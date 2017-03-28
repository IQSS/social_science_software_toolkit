# Recommended testing tools for R packages

## Tools

Setting up an effective testing suite for R can involve the following tools:

-   [devtools](https://CRAN.R-project.org/package=devtools) r package

-   [testthat](https://CRAN.R-project.org/package=testthat) r package

-   [covr](https://CRAN.R-project.org/package=covr) r package

-   one or more continuous integration service such as [Travis CI](https://travis-ci.org/) and [Appveyor](https://www.appveyor.com/)

## Setup steps

You can set up a testing suite at any time in an R package development process using the following steps:

1.

# Development process

Once you have the testing suite set up, you should follow a "test-first" development process characterised in the following figure:
![R Package Development Flow Diagram](img/r-dev-flow.png)

## Further reading

-   [Failing Faster](http://slides.com/christophergandrud/failing-faster#/): presenation by Christopher Gandrud from 22 March 2017 on testing with R packages

-   Hadley Wickham's [chapter](http://r-pkgs.had.co.nz/tests.html) on testing R packages
