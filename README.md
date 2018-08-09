# conda_notes
## Installing miniconda
* Go to [miniconda](https://conda.io/miniconda.html) download page and get ready to download the installer of your choice/system.

  * For miniconda 2 on linux
`wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh`

  * For miniconda 3 on linux
`wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh`

  * (on a Mac you might use)
`curl -O https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh`

 * execute the installer (And be ready to interact with it a little bit)
```
chmod +x Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
```

## Configuring your conda with channels 
Now we install some useful channels (searchable repositories, essentially) for Miniconda
```
conda config --add channels r
conda config --add channels defaults
conda config --add channels conda-forge
conda config --add channels bioconda
```
## Using conda to install bioinformatics tools
Searching for packages by name
```
conda search kallisto
conda search sleuth
```

Installing named packages: You have choices. There are two ways to install things with conda.
1. Directly e.g. `conda install bowtie2`
2. Toggle-able Environments 
```
conda create -n [my_cool_env] [thing1] [thing2]
source activate [my_cool_env]
```
Using environments is smarter in the long run. Why?
It comes with cognitive costs, though. You have to remember to activate your desired environment after logging in.

## What did I install last week/month/year?
To check the configuration of your conda installation
`conda info`
If you forget the names of some of your Environments
`conda info -e`
to see what is a part of that Environment
`conda list -n my_cool_env`

## Modifying installed things
To install new things (here, seqtk) to an environment you previously made
`conda install -n kallisto_env seqtk`

Updating conda
`conda update conda`

Updating installed packages 
`conda update bowtie2`
`conda update -n kallisto_env seqtk`

Toggling Environments
```
source deactivate
source activate kallisto_env
```
