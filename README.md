# How to with Conda
Helpful information related to conda environment

## Create environment 
- Optionally, specify a python version
```
conda create --name env-name python==version
```

## Activating and deactivating
```
conda activate env-name
conda deactivate
```

## List all environment
```
conda env list
conda info --envs
```

## Remove environment
```
conda env remove -n env_name
```

## Install packages in the current env
```
conda install pkg_name==version
```

## List packages 
In the current environment
```
conda list
```

In the specified environment
```
conda list -n env-name
```

## Reproduce an environment
### Create env spec file 
```
conda list --explicit > spec-file.txt
```

## 
```
conda create --name env-name --file spec-file.txt
```
Example output

```# This file may be used to create an environment using:
# $ conda create --name <env> --file <this file>
# platform: osx-64
@EXPLICIT
https://conda.anaconda.org/conda-forge/osx-64/gh-2.5.2-h990441c_0.tar.bz2
https://conda.anaconda.org/bioconda/osx-64/sra-tools-2.8.0-0.tar.bz2
https://conda.anaconda.org/conda-forge/noarch/_r-mutex-1.0.1-anacondar_1.tar.bz2
https://conda.anaconda.org/conda-forge/osx-64/_r-xgboost-mutex-2.0-cpu_0.tar.bz2
https://conda.anaconda.org/conda-forge/osx-64/aws-c-common-0.6.2-h0d85af4_0.tar.bz2
https://conda.anaconda.org/bioconda/osx-64/bmfilter-3.101-3.tar.bz2
https://conda.anaconda.org/conda-forge/osx-64/bzip2-1.0.8-h0d85af4_4.tar.bz2
https://conda.anaconda.org/conda-forge/osx-64/c-ares-1.18.1-h0d85af4_0.tar.bz2
```
> The list can be very long depending on the content of the env.


## Sharing environment across platforms
- Export from history by adding --from-history
- The re-create the environment
```
conda env export --from-history > environment.yml
conda env create -f environment.yml
```

## Rollback to conda revisions
- Conda stores changes made using the conda commands. 
- We can roll back changes by using revision numbers.

Conda revisions and revision numbers
```
conda list --revisions
```

Example output
```
2022-09-20 19:58:49  (rev 0)
    +bzip2-1.0.8 (conda-forge/osx-64)
    +ca-certificates-2022.9.14 (conda-forge/osx-64)
    +libffi-3.4.2 (conda-forge/osx-64)
    +libsqlite-3.39.3 (conda-forge/osx-64)
    +libzlib-1.2.12 (conda-forge/osx-64)
    +ncurses-6.3 (conda-forge/osx-64)
    +openssl-3.0.5 (conda-forge/osx-64)
    +pip-22.2.2 (conda-forge/noarch)
    +python-3.10.6 (conda-forge/osx-64)
    +readline-8.1.2 (conda-forge/osx-64)
    +setuptools-65.3.0 (conda-forge/noarch)
    +tk-8.6.12 (conda-forge/osx-64)
    +tzdata-2022c (conda-forge/noarch)
```

## Restoring previous revision
```
conda install --rev 0
```

## Reference

```
@web_page{SelvaCondaEnv2022,
   author = {Selva Prabhakaran},
   title = {Conda create environment and everything you need to know to manage conda virtual environment - Machine Learning Plus},
   url = {https://www.machinelearningplus.com/deployment/conda-create-environment-and-everything-you-need-to-know-to-manage-conda-virtual-environment/},
   year = {2022},
}
```

