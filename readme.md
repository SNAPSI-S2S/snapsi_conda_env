# SNAPSI conda environment

This repository contains a conda environment for use within the SNAPSI
project. Using this environment will help to ensure that our results are
reproducible.

## Using the environment via SSH

The recommended way to implement the environment on JASMIN is to use Mamba
(though the below is also possible with Conda). This can be installed by
copying and pasting the following:

``` 
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
bash Mambaforge-$(uname)-$(uname -m).sh
```

After this you'll need to close and then restart your shell session. Then the
environment can be created as follows (the command below assumes you are within
the `snapsi_conda_env` directory created by cloning this respository):

```
mamba env create -f env_frozen.yml
```

This may take 5-10 minutes. The environment can then be activated with 

```
mamba activate snapsi
```

Now you're all set to use the environment. 

## Using the environment via Jupyter notebook service

To use the SNAPSI conda environment on the [JASMIN notebook
service](https://notebooks.jasmin.ac.uk/), we'll first create the environment
using the Terminal window option and following the instructions above (you can
skip this step if you have already created the environment via SSH as
above). The following command will then allow the snapsi environment to be used
within a notebook:

```
conda run -n snapsi python -m ipykernel install --user --name snapsi
```

You can use this environment by selecting the `snapsi` kernel when creating a
notebook.

## Adding packages

If you would like to add some packages you can do this by adding them to the
`env.yml` file. You can then install them to the environment with

```
mamba env update --name snapsi --file env.yml
```

and export the solved frozen dependencies with

```
mamba env export > env_frozen.yml
```


