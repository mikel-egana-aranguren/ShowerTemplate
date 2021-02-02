# Installation

In the main repo folder, add this template as a submodule:

```bash
git submodule add https://github.com/mikel-egana-aranguren/ShowerTemplate.git ShowerTemplate
git commit -m "Add subdmodule"
git push
```

Copy `index.html` to appropiate folder, change `shower` paths accordingly, and start editing.

To print as PDF, install `shower` if necessary and then (`sudo npm install -g @shower/cli`) and then in the folder containing `index.html`:

```bash
shower pdf
```
