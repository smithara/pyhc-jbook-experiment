# PyHC jbook experiment

This is a demo of using [Jupyter Book](https://jupyterbook.org/) for the [PyHC gallery](https://github.com/heliophysicsPy/gallery).

Content is copied from: https://github.com/heliophysicsPy/gallery/tree/main/gallery

## Development

Binder link: https://mybinder.org/v2/gh/smithara/pyhc-jbook-experiment/main

Local setup with conda/mamba:
```
mamba env create --file environment.yml
conda activate pyhc
jupyter lab
```

Environment includes [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git) extension for nice git usage with notebooks

Three environments for different use cases (same packages configured, but different versions):

- `environment.yml`: loose definition (major+minor versions) for some wiggle room to include bugfixes
- `environment-strict.yml`: specific versions used for better reproducability
  (`conda env export --name pyhc --file environment-strict.yml`)
- `environment-latest.yml` builds environment with latest versions to test against before manually updating `environment.yml`
