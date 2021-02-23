# Shower presentations

## Installation

In the main repo folder, add this template as a submodule:

```bash
git submodule add https://github.com/mikel-egana-aranguren/ShowerTemplate.git ShowerTemplate
git commit -m "Add subdmodule"
git push
```

Copy `index.html` to appropiate folder, change `shower` paths accordingly, and start editing.

## Create PDF version of presentation

To print as PDF, install `shower` if necessary and then (`sudo npm install -g @shower/cli`) and then in the folder containing `index.html`:

```bash
shower pdf
```

## Release presentation

* Merge `develop` into `releases`.
* (Optionally) Login to [Zenodo](https://zenodo.org/).
* (Optionally) Under user name, click on option GitHub.
* (Optionally) Activate GitHub repo.
* Create a release in GitHub from branch `releases`.
* Add DOI badge to `index.html` and `README.md`.
* Merge `releases` into `main`.
* Merge `main` into `develop`.
