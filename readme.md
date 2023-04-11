# SNAPSI conda environment

## Getting started

This repository contains a conda environment for use within the SNAPSI project,
to ensure that our results are reproducible.

The recommended way to implement the environment on JASMIN is to use Mamba
(though the below is also possible with Conda). This can be installed as
follows:

``` 
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
bash Mambaforge-$(uname)-$(uname -m).sh
```

After this you'll need to close and then restart your shell session. Then the
environment can be created with:

```
mamba env create -f environment.yml
```

This may take 5-10 minutes. The environment can then be activated with 

```
mamba activate snapsi
```

## Adding packages

If you would like to add or remove some packages to this environment please edit
the `environment.yml` file. You can then commit the changes and update your
environment with

```
mamba env update --name snapsi --file environment.yml --prune
```

## Using the evironment file from the JASMIN notebook service

To use this environment within a Jupyter notebook run on the JASMIN notebook
service, you'll need to create a kernel. First we'll make a directory to hold
this:

```
mkdir ~/nb_envs
cd ~/nb_envs
```

Then we make the kernel



