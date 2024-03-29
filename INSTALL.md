# Shower presentations

Shower is a JS library for presentations, so these instructions assume that you already have a Git repo where your slides will live (A repo for a whole course, divided into chapters).

Examples on how to use Shower:

* https://shwr.me/
* https://github.com/shower/shower/blob/main/docs/features.md#code

## Installation of Shower

In the main repo folder, add this Shower template as a submodule:

```bash
git submodule add https://github.com/mikel-egana-aranguren/ShowerTemplate.git ShowerTemplate
git commit -m "Add Shower JS library for presentations as submodule"
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

## Pictures

Use SVG format.

## Releases

Assuming a [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) based repo:

* Work happens in `feature_*` branches, when finished merge into develop (`git merge --no-ff myfeature`) and delete the feature branch (`git branch -d myfeature`). It is important to add the No Fast Forward option to keep the history separated if the develop lacks intermediate commits (My case since single developer).
* Create a `release_*` branch from `develop`: `git checkout -b release-1.2 develop`. Edit `RELEASES.md` and push.
* Merge `release_*` branch into `develop` and `main`: `git merge --no-ff release-1.2`.
* (Optionally) Login to [Zenodo](https://zenodo.org/).
* (Optionally) Under user name, click on option GitHub.
* (Optionally) Activate GitHub repo.
* (Optionally) Tag release in main: `git tag -a 1.2`.
* (Optionally) Create a release in GitHub from `main`.
* (Optionally) Add DOI badge to `index.html` and `README.md`.

## PDF version

To print as PDF, install `shower` if necessary (`sudo npm install -g @shower/cli`) and then in the folder containing `index.html`:

```bash
shower pdf
```

You can use `generate_pdf.sh` to generate multiple PDFs in multiple chapter-folders: `ln -s ShowerTemplate/generate_pdf.sh generate_pdf.sh`.

**IMPORTANT NOTE**: MathJax equations are not properly printed in PDF.

## MathJax

The template includes the [MathJax library](https://www.mathjax.org/) for rendering equations.

For more information on how to use [MathJax](http://docs.mathjax.org/en/latest/) look at [this thread](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).

