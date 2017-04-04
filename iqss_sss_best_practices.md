# IQSS Best Practices for Software Development

|              |                     |
| ------------ | ------------------- |
| Version      | 0.0.0.9000          |
| Last Updated | 2017-04-04          |
| Created      | 2017-03-28          |

**UNDER DEVELOPMENT. The best practices are under review and subject to change.**

# Aims

The aims of the Institute for Quantitative Social Science (IQSS), Harvard University Best Practices for Software Development are to enable the creation and maintenance of software that is:

-   robust,

-   user-friendly,

-   persistant,

-   attributable,

-   enables reproducible research.

The best practices in this document are intended to be applicable to social science statistical software regardless of the programming language it is written in. Language specific guidelines based on these best practices are documented elsewhere in this repository.

## Best practices

Social science statistical software is more likely to achieve the aims listed above if they have the following characteristics:

1.  Are informatively **documented**

-   Documentation is written as close to the source code as possible, e.g. using [Doxygen](http://www.stack.nl/~dimitri/doxygen/) or a Doxygen-like markup.

-   Documentation is comprehensive and aproachably written.

-   Documentation is accessible both alongside the software and on a website.

-   Documentation is automatically generated for each version, in machine and human readable formats.

-   Versions are numbered using [semantic versioning](http://semver.org/.)

-   All changes made to the software are documented in a "changelog".

2.  Have an **open source license**

-   For example [GPL (>= 3)](https://www.gnu.org/licenses/gpl-3.0.en.html)

3.  Are comprehensively and automatically **tested**

4.  Are developed using **version control**

-   For example, but not limited to, [git](https://git-scm.com/)

5.  Are **developed in the open** using tools and standards that enable full source code discovery, exploration, and external contributions

-   For example, but not limited to, [GitHub](https://github.com/)

-   Service used should include facilities for making bug reports

6.  Are clearly **citeable**

-   {SOFTWARE CIATION}

7.  Uses an [**IQSS Report Card**](report_card/iqss_report_card_spec.md) to report their minimal compliance with these Best Practices

## Report card

Minimal compliance with the Best Practices can be recorded using the [IQSS Report Card Specification](report_card/iqss_report_card_spec.md).

For software packages written in R, you can automatically generate a report card using the `check_best_practices` function from the [IQSSdevtools](IQSSdevtools) package.

## Language-specific Best Practices

The tools for implementing the Best Practices are often different depending on the programming language used to create the statistical software.

For packages written in the R language please see: [R IQSS Best Practices](best_practices_per_language/r_best_practices.md).
