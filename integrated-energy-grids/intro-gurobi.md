## Gurobi


In this course, we will use an external solver to solve optimization problems. We Will use Gurobi as solver and we need to get a license for that. 

To install Gurobi, you execute the following commands in the terminal

	conda config --add channels http://conda.anaconda.org/gurobi

        conda install gurobi


Now, you need to get a free academic license to use Gurobi, follow the instructions in [Gurobi webpage](https://www.gurobi.com/downloads/free-academic-license/ ) . You will need to register and log in to get a license.

Once you have registered, run the grbgetkey command to install the license on your computer:

Go to “My Account”  “My Licenses”  “Review your current licenses”  click on the license that you have created  At the bottom, you will see the exact command.

grbgetkey xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx


