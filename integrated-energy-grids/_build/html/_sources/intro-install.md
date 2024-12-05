## Python and Conda

:::{note}

This material is mostly adapted from the following resources:

[Earth and Environmental Data Science: Python Environments](https://earth-env-data-science.github.io/lectures/environment/python_environments.html)

[ Data Science for Energy System Modelling](https://fneum.github.io/data-science-for-esm/intro.html)

:::

Python is a programming language. Packages are built using this language, e.g. `numpy`, `matplotlib`, `pandas`, and `pvlib` .
When we are writing a piece of code, we can benefit from functions that are included in packages previously developed by others. To do that we need to (a) install that package on our computer and (b) import it into our script.  
 
Python and nearly all of the software packages in the scientific python
ecosystem including [pvlib](https://pvlib-python.readthedocs.io/en/stable/) are [open-source](https://opensource.org/). Coordinating the compatibility between these different packages and their multiple versions used to be a nightmare! Fortunately, the problem is solved by using a Python
_distribution_ and/or _package manager_. You should use a package manager!

## Installing the package manager `conda`

### Anaconda Python distribution

The easiest way to set up a full-stack scientific Python deployment is to use a
Python distribution. This is an installation of Python with a set of curated
packages which are guaranteed to work together.

For instance, you can install on your computer the popular
[Anaconda Python Distribution](https://www.anaconda.com/download/).
Follow the link to obtain a one-click installer for your operating system.

The instructions below  assume you have access to a command line. For **Linux and MacOS users**, you can access the command line by opening the _terminal_ program. For **Windows users**, you should first install Anaconda (described above) or miniconda/micromamba (described below), which gives you access to the "Anaconda Prompt" desktop application. (Instructions for this are given on the [Anaconda Website](https://docs.anaconda.com/anaconda/user-guide/getting-started/#write-a-python-program-using-anaconda-prompt-or-terminal).) Alternatively, you can use the Anaconda Navigator. 

### Anaconda Navigator

If you do not want to use the command line, [Anaconda navigator](https://docs.anaconda.com/free/navigator/overview/) can also be used to create environments and install packages using a graphical user interface. 

To create new enviroment, open the Anaconda navigator, select `Environments` on the left menu and use the button `+` to create a new environment. You can add new channels by selecting `Channels` on the top menu where you can also search and install packages.


### Lightweight alternatives: micromamba and miniconda

If you don't want to download a large file like the Anaconda Python Distribution (ca. 800 MB), there are
lightweight alternative installation methods (like `micromamba` and `miniconda`).

1. [Micromamba Installation](https://mamba.readthedocs.io/en/latest/installation.html#micromamba)
2. [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html)

### Installing Python without a package manager

If you do not wish to install a package manager (not recommended), an
alternative is to directly install official Python distributions.

A good tutorial for this can be found [here](https://realpython.com/installing-python/).

### Using Python without a local installation

You can even read the solution to the problems without a local Python installation using online services like  [Google Colab (colab.google)](https://colab.google) which provide an online Python version
in a [Jupyter Notebook](jupyter.org/) environment.

## Managing environments with `conda`

Python coupled with a package manager provides a way to make isolated,
reproducible _environments_ where you have fine-tuned control over all packages
and configuration. Think of the environment as a group of curated package versions that work together. 
You might have different environments on your local computer for different purposes. 

To create a conda environment, you execute the following command:

    conda create --name my_environment

To use this environment, simply "activate" it by executing:

    conda activate my_environment

You should now see the string `(my_environment)` prepended to your prompt.
Now, if you execute any Python-related tool from the
command line, it will first search in your environment.

To install additional packages into your environment:

    conda install <package-name>

Some packages are community-maintained (e.g. `conda-forge`) and require you to specify a different "channel":
You can think of conda-forge as a library where developers make their packages available to other users.

    conda install -c conda-forge <package-name>

You can deactivate your environment by typing:

    conda deactivate

To see all the environments on your system:

    conda info --envs

To get a complete summary of all the packages installed in your environment, run

    conda list

If you want to permanently remove an environment and delete all the data
associated with it:

    conda env remove --name my_environment --all

A conda environment can also be defined through an `environment.yaml` file. With that file, a new environment with the exact configuration can be installed by executing

    conda env create -f my_environment.yml

Below we will see an example of an environment file.

For extensive documentation on using environments, please see
[the conda documentation](https://conda.io/docs/using/envs.html).

If you do not want to use the command line, [Anaconda navigator](https://docs.anaconda.com/free/navigator/overview/) (described above) can also be used to create environments and install packages using a graphical user interface. 

## Speeding things up with Mamba

In order to put together an actual Python environment from your package specifications, sometimes
`conda` has to solve a difficult puzzle, to ensure that the combination of packages is mutually compatible.
Each package specified has certain dependencies on other packages.
Moreover, each version of one package requires certain minimum versions of other
packages.
Other packages in your environment may have different or incompatible versions.
The default implementation of `conda` can be very slow.
Fortunately, there is a much faster alternative called [mamba](https://mamba.readthedocs.io/en/latest/index.html).
To install it, just run:

    conda install -n base -c conda-forge mamba

Now you can install environments and packages as before, but using the `mamba` command
instead of `conda`. Everything will be faster.

## Python environment for this book: `pv-texbook`

## With `conda` or `mamba`

The latest environment specification for this course can be downloaded under the following link as a [`YAML`-file](https://en.wikipedia.org/wiki/YAML):

https://github.com/martavp/pv-textbook/blob/main/environment.yaml

There is a download button at the top-right corner.

After navigating to the folder where the `environment.yaml` file is stored,
you can reate this environment using `conda` or `mamba` (faster)

    conda env create -f environment.yml

or

    mamba create -f environment.yml

Activate this environment

    mamba activate pv-textbook

This environment should be sufficient for all of the problems in this repository.

The environment has to be activated whenever you open a new terminal,
*before* starting a new Jupyter window with

    jupyter notebook

### With `pip`

If you want to use `pip` for managing your environment, download

https://github.com/martavp/pv-textbook/blob/main/requirements.txt

There is a download button at the top-right corner.

After navigating to the folder where the `requirements.txt` file is stored,
you can install the required packages with

    pip install -r requirements.txt

This should allow you to start a new Jupyter window:

    jupyter lab

## JupyterLab and Jupyter Notebooks

[JupyterLab](https://jupyterlab.readthedocs.io) will be our primary method for
solving the problems. JupyterLab contains a complete environment for
interactive data science which runs in your web browser.

JupyterLab has excellent documentation. Rather than repeat that documentation
here, we point you to their docs. The following pages are particularly relevant:

- [The JupyterLab Interface](https://jupyterlab.readthedocs.io/en/stable/user/interface.html)
- [Working with Files](https://jupyterlab.readthedocs.io/en/stable/user/files.html)
- [The Text Editor](https://jupyterlab.readthedocs.io/en/stable/user/file_editor.html)
- [Notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html)
- [Terminals](https://jupyterlab.readthedocs.io/en/stable/user/terminal.html)
- [Managing Kernels and Terminals](https://jupyterlab.readthedocs.io/en/stable/user/running.html)

## Markdown Syntax

When using Jupyter Nootebooks, you might want to write rich text documents using Markdown.
Here are some useful references on Markdown syntax.

- [Markdown Guide / Basic Syntax](https://www.markdownguide.org/basic-syntax)
- [Official Markdown Documentation](https://daringfireball.net/projects/markdown/)
