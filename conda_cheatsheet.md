# Create new environment

Notice that these exampples use `conda create`. `conda env create` takes different parameters.

```shell
conda create -n "myenv" python=3.3.0 ipython
```

```shell
conda create -n "myenv" --clone "base"
```

# Conda environment yaml

Notice that you cannot create a conda environment from a file using `conda create`, you must use `conda env create`

```yaml
# env.yml
name: py36
dependencies:
  # Python
  - python=3.6
  # Packages
  - pandas
  - pip:
    - django-environ==0.4

  # Packages used for development
  - pip=20.2.4
  - ipython
  - jedi=0.17.2 #downgrade jedi, to fix autocomplete in ipython
```

```shell
conda env create -f env.yml
```

Notice that here we need to use the `conda env` program
