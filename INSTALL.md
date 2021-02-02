# Installation

In the main repo folder, add this template as a submodule:

```bash
git submodule add https://github.com/mikel-egana-aranguren/ShowerTemplate.git shower

git push
```

Then optionally create a symbolic to the index.html file:

```bash
ln -s  shower/index.html index.html
```

To print as PDF, install (`sudo npm install -g @shower/cli`)and then in the shower folder:

```bash
shower pdf
```
