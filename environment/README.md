`pyhc-gallery.yml` is used to generate a specific environment defined by `pyhc-gallery-fixed-conda.txt` and `pyhc-gallery-fixed-pip.txt`. `pyhc-gallery.yml` is manually written, getting as many as possible packages from conda-forge, then adding the remaining pip-only packages.

To attempt to create an environment (cross platform):
```
mamba env create --name pyhc --file pyhc-gallery.yml
mamba activate pyhc
```

Then to generate the list of conda packages (the ones provided in `pyhc-gallery-fixed-conda.txt` are for linux)
```
mamba list --name pyhc --explicit > filename.txt
```

I created the `pyhc-gallery-fixed-pip.txt` manually from inspecting the output of:

```
mamba list --name pyhc | grep pypi
```

To create the exact environment (on linux) from the two .txt files:
```
mamba create --name pyhc --file pyhc-gallery-fixed-conda.txt
mamba activate pyhc
pip install pyhc-gallery-fixed-pip.txt
```
