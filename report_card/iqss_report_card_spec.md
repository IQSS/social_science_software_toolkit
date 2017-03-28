[<img src="img/iqss_report_card_logo_v1.png" align="right" height="75" width ="75"/>](https://github.com/IQSS/social_science_software_toolkit/blob/master/report_card/iqss_report_card_spec.md)

# IQSS Report Card Specification

|              |                     |
| ------------ | ------------------- |
| Authors      | Christopher Gandrud |
| Version      | 0.0.0.9000          |
| Last Updated | 2017-03-28          |
| Created      | 2017-03-28          |

## Goals

An IQSS Report Card reports the extent to which a piece of statistical software is *minimally* compliant with the [IQSS Best Practices for Social Science Statistical Software Development](https://github.com/IQSS/social_science_software_toolkit/blob/master/iqss_sss_best_practices.md).

## Changelog

All changes to the spec after version 0.0.0.9000 are reported in the [Changelog](changelog.md).

## File name and format

An IQSS Report Card is a [YAML formatted file](http://yaml.org/) with the name *.iqss_reportcard.yml*. Note that YAML files can be parsed as JSON or XML.

## Parent Nodes

All IQSS Report Cards **must** have the following parent nodes:

```yaml
Documentation
License
Version_Control
Testing
Background
```

## Child Nodes

An IQSS Report Card **may** have the following child nodes. Typically different child nodes will be applicable to software written in particular languages.


### Documentation

The `Documentation` parent node **may** contain the following fields:

| Name              | Description | Type     | Language |
| ----------------- | ----------- | -------- | -------- |
| `readme`          | A README file explaining the software's aims and with a quickstart example | boolean | all |
| `changelog`       | Document detailing all changes per release | boolean | non-R |
| `NEWS`            | Document detailing all changes per release | boolean | R |
| `bugreports`      | URL for public location to make bug reports | boolean | all |
| `vignettes`       | Longform documentation with detailed descriptions | boolean | R |
| `website`         | A website dynamically generated documentation website | boolean | non-R |
| `pkgdown_website` | A website dynamically generated with the [pkgdown](https://github.com/hadley/pkgdown) package | boolean | R |

### License

The `License` parent node **may** contain the following fields:

| Name              | Description              | Type     | Language |
| ----------------- | ------------------------ | -------- | -------- |
| gpl3_license      | Contains a GPL-3 License | boolean  | all      |

### Version_Control

The `Version_Control` parent node **may** contain the following fields:

| Name              | Description                 | Type     | Language |
| ----------------- | --------------------------- | -------- | -------- |
| git               | Version controlled with git | boolean  | all      |
| github            | Source developed on GitHub  | boolean  | all      |
| gitlab            | Source developed on GitLab  | boolean  | all      |

### Testing

The `Testing` parent node **may** contain the following fields:

| Name              | Description                              | Type     | Language |
| ----------------- | ---------------------------------------- | -------- | -------- |
| uses_travis       | Uses Travis CI                           | boolean  | all      |
| uses_appveyor     | Uses Appveyor CI                         | boolean  | all      |
| uses_testthat     | Uses testthat package                    | boolean  | R        |
| test_coverage     | Percent of source covered by tests       | integer  | all      |
| build_check       | Reports software build and check results | node     | all      |

The `build_check` node **may** contain the following fields:

| Name                 | Description                      | Type     | Language |
| -------------------- | -------------------------------- | -------- | -------- |
| build_check_complete | Able to complete build and check | boolean  | all      |
| no_check_warings     | Check without warnings           | boolean  | all (?)  |
| no_check_errors      | Check without errors             | boolean  | all (?)  |
| no_check_notes       | Check without notes              | boolean  | all (?)  |


### Background

The `Background` parent node **may** contain the following fields:

| Name                       | Description                                                | Type     | Language |
| -------------------------- | ---------------------------------------------------------- | -------- | -------- |
| package_name               | Name of the software package for the Report Card           | string   | all      |
| package_version            | Version number of the software package for the Report Card | string   | all      |
| package_language           | Primary programming language used to write the package     | string   | all      |
| package_commit_sha         | Most recent package git commit SHA                         | numeric  | all      |
| iqss_bestpractices_version | IQSS Best Practices version references                     | string   | all      |
| iqssdevtools_version       | IQSS Best Practices version references                     | string   | R        |
| check_time                 | Time of IQSS Best Practices check                          | string   | all      |
