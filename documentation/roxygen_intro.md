# Quick introduction to Roxygen for R Package documentation

Clear and complete documentation is vitally important for users to be able to actually use your R package accurately.

All of the user-facing objects in your R package--e.g. functions and data sets--should have object documentation. This documentation is included with your package's installation and, when using [**IQSSdevtools**](https://github.com/IQSS/IQSSdevtools), your package's website. Users can access object documentation in directly in R using `?` or `help()`, e.g. for the `mean` function:

```r
?mean
```

Object documentation in an R package is stored in `.Rd` files in the *man/* directory. It is written in a [LaTeX](https://en.wikipedia.org/wiki/LaTeX)-based [markup language](https://en.wikipedia.org/wiki/Markup_language). This is inconvenient for at least two reasons:

-   requires knowledge of a complex idiosyncratic markup language,

-   separates the writing of your function code and documentation.

One solution to these issues is to use [Roxygen2](https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html) documentation syntax and **IQSSdevtools** (you can also of course compile the documentation using the roxygen2 R package).

Roxygen allows you to intermingle your R code and documentation, so you can easily update your documentation when you change your R code. From this code it generates the `.Rd` files dynamically and writes boilerplate documentation so you don't need to.

## Roxygen quickstart

This is a quickstart guide to get you writting R documentaiton in Roxygen. For more detailed introduction to object documentation see [HW: Object documentation](http://r-pkgs.had.co.nz/man.html) (upon which this introduction is based).

Add roxygen documentation directly in the `.R` source code files that you use to create your package's functions. In fact for each function you create and want to document, place the roxygen code *directly above it*

Then, whey you use the `build_iqss_package()` function from the **IQSSdevtools** package it will automatically convert this to R object documentation in both the package and on your website.

Here is an example from [HW: Object documentation](http://r-pkgs.had.co.nz/man.html) of how to document a function called `add`:

```r
#' Add together two numbers
#'
#' @param x A number.
#' @param y A number.
#'
#' @return The sum of \code{x} and \code{y}.
#'
#' @examples
#' add(1, 1)
#' add(10, 1)

add <- function(x, y) {
  x + y
}
```

Notice that all of the roxygen comments are started with `#'`. This informs R to ignore them and roxygen to pay attention to them.

The first line of roxygen comment--`#' Add together two numbers`--contains the function's title. The third line contains the `@param` tag. This tag documents function arguments. `#' @param x A number.` assigns `A number` as the description of the `x` argument in the `add` function. We use a similar syntax to document the `y` argument.

The `@return` tag allows you to provide a description of what the `add` function returns. Notice that `\code` allows you to format text as using code highlighting.

Finally, the `@examples` tag allows you to include executable examples in your documentation. When you run `build_iqss_package` this code will be run and return an error if it fails. This is a basic form of software testing, though the [expectation you are testing is relatively poor](https://github.com/IQSS/social_science_software_toolkit/blob/master/testing/recommended_testing_tools_R.md#what-is-a-high-quality-test), i.e. does a given call to the function not return an error.  
