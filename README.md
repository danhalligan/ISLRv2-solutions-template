# ISLRv2 solutions template

This repository provides a [bookdown] [GitHub template] for completing the end
of chapter "Conceptual" and "Applied" exercises from the the book [An
Introduction to Statistical Learning] by Gareth James, Daniela Witten, Trevor
Hastie and Robert Tibshirani.

![ISLR cover](images/isl_small.jpg)

## tl;dr

* [Generate a new repository from this template].
* Fill in your answers in [R Markdown] between the commented questions.
* Push your edits to build your [bookdown book of solutions].

[Generate a new repository from this template]: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template
[bookdown book of solutions]: https://danhalligan.github.io/ISLRv2-solutions-template/

## Usage

To complete your solutions, please [generate a new repository] from this
 template this repository first. You can then add solutions between the relevant
commented questions using [R markdown].

All questions from the original book have been translated to markdown and are
quoted. You should provide your answers between the commented sections. 
For example:


```markdown
> For each of parts (a) through (d), indicate whether we would generally expect
> the performance of a flexible statistical learning method to be better or
> worse than an inflexible method. Justify your answer.
>
> a. The sample size n is extremely large, and the number of predictors p is
>    small.

In this case, a flexible method would be better because we have a large number
of observations so can more reliably detect subtle patterns in the data and are
likely to avoid overfitting due to the low number of predictors.

> b. The number of predictors p is extremely large, and the number of
>    observations n is small.

Erm, perhaps the opposite?
```

You may want to edit this `README.md` (to reflect that your version is not a
template!), and edit the `edit` tag in `_output.yml` to point to your
repository.

## Data sets

For some questions, you are required to read in data. These data are provided
in subdirectory `data`, downloaded from the [resources] section of 
<https://www.statlearning.com>.


## Implementation details

This repository is setup using bookdown and can build a [gitbook] style bookdown
book. Options are controlled in `_bookdown.yml` and `_output.yml`. Notably, I've
set `new_session: yes` to start a new R session for each chapter of the book,
so R packages required for answers should be reloaded for each chapter
that requires them.

To build the book locally you can run:

```{r}
bookdown::render_book('index.Rmd', 'bookdown::gitbook')
```

Or hit the "build" button in your RStudio session.

### GitHub workflow

I have specified a `.github/workflows` directory to implement a [GitHub
workflow] to build the book on updates to the repository and then host the 
built book from GitHub pages. For example, to see the built version of this 
template, see the [GitHub pages deployment]. When generating a new repository
from this template you may need to enable workflows to get this to run. The 
workflow will create a new branch `gh-pages` containing the built book and will
deploy this book for you.

### Dependencies

R package dependencies should be specified in the (fake) package `DESCRIPTION`
file. These dependencies will then be installed by the workflow so that your 
book build works as expected.

### Styling

I've added some (minimal) styling for the book inside `islrv2.css`, notably,
using [Computer Modern] in homage to the the book (and the rest of this font's
history!). To achieve this, I've made use of a [web version] of computer modern.

## Final words

Many thanks for the original authors for a great book on statistical learning.

If you notice any errors, feel free to make a pull request.

[bookdown]: https://bookdown.org/
[R Markdown]: https://rmarkdown.rstudio.com/
[GitHub template]: https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/
[An Introduction to Statistical Learning]: https://www.statlearning.com/
[generate a new repository]: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template
[resources]: https://www.statlearning.com/resources-second-edition
[gitbook]: https://www.gitbook.com/
[GitHub workflow]: https://docs.github.com/en/actions/using-workflows
[GitHub pages deployment]: https://danhalligan.github.io/ISLRv2-solutions-template/
[Computer Modern]: https://en.wikipedia.org/wiki/Computer_Modern
[web version]: https://github.com/aaaakshat/cm-web-fonts
