# IQSS Best Practices for Social Science Software Development

|              |                     |
| ------------ | ------------------- |
| Version      | 0.0.0.9000          |
| Last Updated | 2017-03-28          |
| Created      | 2017-03-28          |

**UNDER DEVELOPMENT. The best practices are under review and subject to change.**

# Aims

The amis of the Institute for Quantitative Social Science (IQSS), Harvard University Best Practices for Social Science Software Development are to enable the creation and maintenance of software that is:

-   robust,

-   user-friendly,

-   persistant,

-   attributable,

-   enables reproducible research.

The best practices in this document are intended to be applicable to social science statistical software regardless of the programming language it is written in. Language specific guidelines based on these best practices are documented elsewhere in this repository.

## Best practices

Social science statistical software is more likely to acheive the aims listed above if they have the following characteristics:

1.  Are informatively documented

-   Documentation is written as close to the source code as possible, e.g. using [Doxygen](http://www.stack.nl/~dimitri/doxygen/) or a Doxygen-like markup.

-   Documentation is comprehensive and aproachably written.

-   Documentation is accessible both alongside the software and on a website.

-   Documentation is automatically generated for each version, in machine and human readable formats.

-   Versions are numbered using [semantic versioning](http://semver.org/.)

-   All changes made to the software are documented in a "changelog".

2.  Have an open source license

-   For example [GPL (>= 3)](https://www.gnu.org/licenses/gpl-3.0.en.html)

3.  Are comprehensively and automatically tested

4.  Are developed using version control

-   For example, but not limited to, [git](https://git-scm.com/)

5.  Are developed in the open using tools and standards that enable full source code discovery, exploration, and external contributions

-   For example, but not limited to, [GitHub](https://github.com/)

-   Service used should include facilities for making bug reports

6.  Are clearly citeable

-   {SOFTWARE CIATION}

7.  Uses an [IQSS Report Card](report_card/iqss_report_card_spec.md) to report their minimal compliance with these Best Practices
