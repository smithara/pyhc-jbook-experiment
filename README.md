# PyHC jbook experiment

This is a demo of using [Jupyter Book](https://jupyterbook.org/) for the [PyHC gallery](https://github.com/heliophysicsPy/gallery).

Content is copied from:
- https://github.com/heliophysicsPy/gallery/tree/main/gallery
- and the [PyHC executable paper presented at AGU](https://agu.confex.com/agu/fm21/meetingapp.cgi/Paper/911907)

## Development

Binder link: https://mybinder.org/v2/gh/smithara/pyhc-jbook-experiment/main

Local setup with conda/mamba in Linux:  
```
conda env create --file environment.yml --name pyhc
conda activate pyhc
pre-commit install
jupyter lab
```

Compile the book with: `jupyter-book build .`

The environment includes the [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git) extension for nice git usage with notebooks. It also includes [pre-commit](https://pre-commit.com/) to use [nbstripout](https://github.com/kynan/nbstripout) to help prevent committing notebook output cells to the repository. pre-commit will run automatically when you `git commit`, scrubbing the notebooks (the first commit will fail, having just modified the notebooks - just `git add` and `git commit` a second time for it to succeed).

There are three environments for different use cases (same packages configured, but different versions):

- `environment-near.yml`: loose definition (major+minor versions) with only direct dependencies - used as a starting point to generate `environment.yml`
- `environment.yml`: full specification for better reproducability  
  (`conda env export --name pyhc --file environment.yml`)
- `environment-latest.yml` builds environment with latest versions to test against before manually updating `environment.yml`
