# Quick introduction to RMarkdown for dynamic *README* files

R packages ideally have a file in their main folder called *README.md* providing a *brief* introduction to the package. It should explain the package's purpose, basic syntax, and provide a simple quickstart example to get users started. The *README* should be **dynamically generated** and written in **Markdown**.

*README* files written in Markdown (with the `.md` file extension) are automatically rendered by GitHub and CRAN so that they are easy for your users to read. For example, here is a selection from the [Zelig R package README](https://github.com/IQSS/Zelig) rendered on GitHub:

![zelig readme](img/zelig_readme.png)

## Markdown

(Almost) all of the source code files in your R package are plain text files. This includes the files you use to document why your package exists and how it works. As such, you need a [markup language](https://en.wikipedia.org/wiki/Markup_language) to give instructions for how to format the document when it is rendered on GitHub and CRAN. You are encouraged to use the [Markdown](https://en.wikipedia.org/wiki/Markdown) markup language for *README* files. Unlike more complex Markup languages like LaTeX and HTML, Markdown simple and easy to learn.

See [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for an introduction to Markdown.


## Dynamic *README* generation

*README* files ideally include examples that users can run on their computer to get a feel for how the package works. These examples should include output, so that users can compare the results they get on their own computer to the expected output. The examples should also run without error.

Use [R Markdown](http://rmarkdown.rstudio.com/lesson-2.html) to dynamically generate examples in your *README* file. R Markdown allows you to include executable "code chunks" in a Markdown document. These code chunks can be run by R and the output included in the final document.

To use R Markdown for your *README*, write your documentation and code chunks in a file called *README.Rmd*. `init_iqss_package` from the [**IQSSdevtools**](https://github.com/IQSS/IQSSdevtools) R package automatically creates this file. Only edit the *README.Rmd* file, not the *README.md* as the latter will be generated from *README.Rmd* automatically when you run in R either:

```r
IQSSdevtools::build_iqss_package()
```

or to render only the *README* and not the whole package:

```r
rmarkdown::render('README.Rmd')
```

### Code chunks in R Markdown

To add executable code in your *README.Rmd* include three backticks ``` followed by `{r}`. You can include [code chunk options](https://yihui.name/knitr/options/) inside of the curly brackets `{}` to specify how the chunk is run. Then on a new line include the code you want to execute. Close the chunk with another three backticks. For example:

```
## Example code chunk.

The following is an example R Markdown code chunk:

    ```{r}
    library(MyPackage)

    x <- 1:10
    a_function(x)
    ```
```

The three backticks followed by `{r}` tells `build_iqss_package` (or `render`) that the following code is R syntax, not Markdown, and that the code should be run with the output returned to the *README.md* file. The closing three backticks tells `build_iqss_package` that the code chunk has ended and to switch back to Markdown.

[This RStudio website](http://rmarkdown.rstudio.com/lesson-3.html) has more information on writing code chunks.
