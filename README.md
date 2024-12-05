# Integrated Energy Grids

This repository includes relevant tutorials and solutions to problems proposed in the MSc course [Integrated Energy Grids](https://kurser.dtu.dk/course/2024-2025/46770?menulanguage=en) at DTU... 

If you detect any error, please [open an issue](https://github.com/martavp/integrated-energy-grids/issues) and we will try to fix it. Ideally, you can also pull request the fix.

## Usage

You can go to a nice visualization of the problems [here](https://martavp.github.io/integrated-energy-grids/intro.html) (or following the web address displayed on the top right corner of this repository).

There you will find instructions on how to install Python, learn the packages used to solve the problems and read the solutions in [Jupyter notebooks](https://jupyter.org/).

If you don't want to install anything on your computer, you will also find instructions on how to use [Google colab](https://colab.google/) to run the scripts online.


## Building the html version of this repository
If you want to build/modify the htlm version of this repository:

1. Clone this repository
> git clone https://github.com/martavp/integrated-energy-grids
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. Run `jupyter-book clean integrated-energy-grids/` to remove any existing builds
4. Run `jupyter-book build integrated-energy-grids/`



## Contributing

We welcome and recognize all contributions. If you'd like to contribute to the project by providing feedback, identifying a bug or working on a new feature, check out the [contributing guide](CONTRIBUTING.md) to get started.

You can see a list of current contributors in the [contributors tab](https://github.com/martavp/integrated-energy-grids/graphs/contributors).

## Acknowledgements

This template was inspired and made possible by the [Cookiecutter project](https://github.com/cookiecutter/cookiecutter) and the [Jupyter Book project](https://github.com/executablebooks/jupyter-book).
