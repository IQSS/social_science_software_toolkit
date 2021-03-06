# IQSS Best Practices for Statistical Software Development in R

|              |                     |
| ------------ | ------------------- |
| Version      | 0.0.0.9000          |
| Last Updated | 2017-04-05          |
| Created      | 2017-03-29          |

The following tools are recommended for developing statistical software packages in R that comply with the [IQSS Best Practices for Statistical Software Development](https://github.com/IQSS/social_science_software_toolkit/blob/master/iqss_sss_best_practices.md).

The Best Practices are *in addition to* package requirements specified by the [Comprehensive R Archive Network (CRAN)](https://cran.r-project.org/doc/manuals/r-release/R-exts.html).

See the [Quickstart Guide](https://github.com/IQSS/social_science_software_toolkit/blob/master/best_practices_per_language/r_quickstart_guide.md) for a step-by-step introduction to implementing the best practices.

For details on how to use many of the tools listed below, please see Hadley Whickham's free online book [R Packages](http://r-pkgs.had.co.nz/).

## IQSSdevtools

The [**IQSSdevtools** package (UNDER DEVELOPMENT)](https://github.com/IQSS/IQSSdevtools) automates much of the process of initializing, building, checking, and publishing your package in compliance with the Best Practices. Use the following functions from the package in your software development workflow:

-   `init_iqss_package`: create a package skeleton that includes whole or skeleton documents for most of the following Best Practice compliant parts.

-   `build_iqss_package`: compile the package, documentation (including website), run tests, and commit changes to GitHub.

-   `publish_package`: push a package to GitHub, create a new git version tag, and submit the package to CRAN.

### Documentation

-   When possible, documentation should be written in [Markdown](https://en.wikipedia.org/wiki/Markdown) with dynamically generated examples created with [**rmarkdown**](http://rmarkdown.rstudio.com/).

-   Packages should include a dynamically generated (i.e. created using [**rmarkdown**](http://rmarkdown.rstudio.com/)) README.md file that gives a *brief* introduction to the package including (a) motivation for the package, (b) an explanation of the method the package implements, and (c) a "quickstart" example, i.e. a quick introduction to the package's syntax. The README.md file should be located in the package's root directory.

    +   The README.md file should also use [badges](https://shields.io/) to inform users about important package information such as the package version, test coverage, whether the package passes continuous integration tests, the package's development status, how to contact the package maintainers.

-   Function documentation should be written as closely to the function source code as possible and be dynamically generated. As such you should write function documentation with [**roxygen2**](https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html). It should be compiled into internal package documentation on build.

-   Package versions should be numbered using [semantic versioning](http://semver.org/.).

-   All changes to the package should documented in a NEWS.md file located in the package's root directory. GitHub Issues and Pull Request numbers should be referenced with each change when applicable.

-   The package DESCRIPTION file should include a `BugReports` field with a URL that users can visit to report issues with the package. [GitHub Issues](https://guides.github.com/features/issues/) is the recommended platform for handling bug reports.

    +   In addition to a place to make bug reports, an easy to use discussion platform should be available and maintained to disseminate announcements and build a community around the package. Examples include [Google Groups](https://groups.google.com), [Twitter](https://twitter.com/), and [Gitter](https://gitter.im).

-   In addition to the README.md and function specific documentation generated with **roxygen2**, longer explanations of methods and complex syntax examples should be documented with [vignettes](http://r-pkgs.had.co.nz/vignettes.html).

-   A guide for contributing to the package should be specified in a CONTRIBUTING.md file {WORDING NOT FINALIZED} in the package's root directory. It should include a link to the [IQSS Code of Conduct](https://github.com/IQSS/social_science_software_toolkit/blob/master/contributing/iqss_code_of_conduct.md).

-   Documentation should be available both as part of the package installation and on a version controlled public website. **roxygen** documentation and vignettes can be transformed into this website with the [**pkgdown**](https://github.com/hadley/pkgdown) package. IQSS packages should be hosted on OpenScholar {INTEGRATION BETWEEN pkgdown AND OpenScholar UNDER DEVELOPMENT}.

### License

-   Unless there are compelling reasons for a different license, IQSS Best Practice packages should use an open source license, namely [GPL 3](https://www.gnu.org/licenses/gpl-3.0.en.html).

### Testing

-   The package should be developed with a [test-driven workflow](https://github.com/IQSS/social_science_software_toolkit/blob/master/testing/recommended_testing_tools_R.md#development-process).


-   The package should have a [comprehensive test suite](https://github.com/IQSS/social_science_software_toolkit/blob/master/testing/recommended_testing_tools_R.md) that:

    +   is written using the [**testthat**](https://CRAN.R-project.org/package=testthat) R package,

    +   tests both package requirements and package error handling,

    +   has high [code coverage](https://en.wikipedia.org/wiki/Code_coverage),

    +   has [high quality expectations](https://github.com/IQSS/social_science_software_toolkit/blob/master/testing/recommended_testing_tools_R.md#what-is-a-high-quality-test),

    +   is tested locally using `check(args = c('--as-cran'))` from the [**devtools**](https://CRAN.R-project.org/package=devtools) package and remotely on [Travis CI](https://travis-ci.org/) (Linux and macOS) and [Appveyor](https://www.appveyor.com/) (Windows). These tools ensure that the package can build and all tests pass, including CRAN requirements.

    +   has code coverage reported on [codecov.io](https://codecov.io/).


### Version Control and Open Development

-   The full development of the package source code should be version controlled. The recommended version control tool is [git](https://git-scm.com/).

-   Unless privacy concerns necessitate otherwise, source code should be developed in the open, on a publicly accessible website that has version control facilities, bug reporting, project management tools, and enables community contributions. The recommended service is [GitHub](https://github.com/).

### Report Card

-   The package should include an [**IQSS Report Card**](https://github.com/IQSS/social_science_software_toolkit/blob/master/report_card/iqss_report_card_spec.md) describing the package's level of *minimal* compliance with the Best Practices.

-   The Report Card should be automatically generated with the `check_best_practices` function from the [**IQSSdevtools** package](https://github.com/IQSS/IQSSdevtools).


## Examples

The following are examples of current (as of 2017-03-29) *minimal* compliance with the R IQSS Best Practices. The Report Cards were generated with the `check_best_practices` function from the [**IQSSdevtools** package](https://github.com/IQSS/IQSSdevtools) package.

### Zelig

```yaml
# Created by IQSSdevtools (0.0.0.9000). Do not edit by hand.

Documentation:
  readme: yes
  roxygen: no
  news: yes
  bugreports: yes
  vignettes: yes
  website:
    openscholar: no
    pkgdown_website: no
License:
  gpl3_license: yes
Version_Control:
  git: yes
  github: yes
Testing:
  uses_testthat: yes
  uses_travis: yes
  uses_appveyor: yes
  build_check:
    build_check_completed: yes
    no_check_warnings: yes
    no_check_errors: yes
    no_check_notes: yes
  test_coverage: 86
Background:
  package_name: Zelig
  package_version: 5.0-18
  package_language: R
  package_commit_sha: e51feceaa484f8c9e9c6f206b38542fafd438e15
  iqss_bestpractices_version: 0.0.0.9000
  iqssdevtools_version: 0.0.0.9000
  check_time: 2017-03-29 12:03:23
```

### Amelia


```yaml
# Created by IQSSdevtools (0.0.0.9000). Do not edit by hand.

 Documentation:
  readme: no
  roxygen: no
  news: no
  bugreports: no
  vignettes: yes
  website:
    openscholar: yes
    pkgdown_website: no
License:
  gpl3_license: no
Version_Control:
  git: yes
  github: yes
Testing:
  uses_testthat: no
  uses_travis: no
  uses_appveyor: no
  build_check:
    completed: no
  test_coverage: 45
Background:
  package_name: Amelia
  package_version: 1.7.4
  package_language: R
  package_commit_sha: 2cd1efb6324e3761c10b5063c811cc6d6d72cdda
  iqss_bestpractices_version: 0.0.0.9000
  iqssdevtools_version: 0.0.0.9000
  check_time: 2017-03-29 15:51:57
```
