# Shower presentations

Shower is a JS library for presentations, so these instructions assume that you already have a Git repo where your slides will live (A repo for a whole course, divided into chapters).

## Installation of Shower

In the main repo folder, add this Shower template as a submodule:

```bash
git submodule add https://github.com/mikel-egana-aranguren/ShowerTemplate.git ShowerTemplate
git commit -m "Add subdmodule for Shower"
git push
```

Create a folder for each chapter at the root level of the repo e.g.:

```bash
Introduction/
Security/
ShowerTemplate/
LICENSE
README.md
```

Copy `index.html` from `ShowerTemplate` to each chapter folder. Change paths that refer to shower elements by adding `../ShowerTemplate/` at the beggining. At least, as a suggestion:

* `<link rel="stylesheet" href="../ShowerTemplate/shower/themes`
* `<img src="../ShowerTemplate/pictures/ehu.png"`
* `<img src="../ShowerTemplate/pictures/by.png" alt="Creative Commons BY" height="10%">`
* `<script src="../ShowerTemplate/shower/shower.js"></script>`

Start editing `index.html`.

(If, instead of a course with different chapters, you have only a file for e.g. a talk, you can copy `index.html` to the root level and use directly the `ShowerTemplate/shower` path)

## Release of the presentation

Assuming a [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) based repo:

* Merge `develop` into `releases`.
* (Optionally) Login to [Zenodo](https://zenodo.org/).
* (Optionally) Under user name, click on option GitHub.
* (Optionally) Activate GitHub repo.
* Create a release in GitHub from branch `releases`.
* Add DOI badge to `index.html` and `README.md`.
* Merge `releases` into `main`.
* Merge `main` into `develop`.

## Extras

### PDF version

To print as PDF, install `shower` if necessary (`sudo npm install -g @shower/cli`) and then in the folder containing `index.html`:

```bash
shower pdf
```

**IMPORTANT NOTE**: MathJax equations are not properly printed.

### MathJax

The template includes the [MathJax library](https://www.mathjax.org/) for rendering equations.

For more information on how to use [MathJax](http://docs.mathjax.org/en/latest/) look at [this thread](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).
