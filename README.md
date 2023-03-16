<h1>
![This is an image](https://cdn.pixabay.com/photo/2013/03/22/23/37/ferrari-96052_1280.png)
</h1>

<h4 align="center">A fast and efficient montecarlo analysis conductor</h4>

<h1><h/1>
	
**What is Leclerc?**

Leclerc is a Sun Cable initiative that creates a PERT wrapper around levelised cost formulas to identify Monte Carlo trends in PERT inputs.
This package has derived work done by Heiko Onnen which can be found at: https://towardsdatascience.com/python-powered-monte-carlo-simulations-fc3c71b5b83f and https://towardsdatascience.com/python-scenario-analysis-modeling-expert-estimates-with-the-beta-pert-distribution-22a5e90cfa79.

**How to Install**

1. To get started, you must first have a Development Environment. For ease of use, we recommend Visual Studio Code which can be downloaded at: https://code.visualstudio.com/Download

2. VS Code also requires that you have Python installed onto your desktop, which can be downloaded on Windows on the Python website or similarly done on Mac by downloading homebrew. Paste this command into your terminal: ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```. Once homebrew is installed, run ```brew install python3```. 

3. Code your desired formula into a python file and place in a folder as shown below:

**FILLER IMAGE**

4. Install pip from your VS Code Terminal using ```python get-pip.py```. For more information on pip: https://pip.pypa.io/en/stable/installation/

5. Running ```pip install leclerc``` will install the leclerc package. To download with all dependencies, run ```python3 -m pip install --upgrade --no-cache-dir --use-deprecated=legacy-resolver leclerc```


**How to Use**

To use this package, call a formula and add the parameters. For inputs that have uncertainty, apply the PERT parameter. The output should give a bokeh html showcasing a histogram of the levelised cost parameter and PDF plots for inputs. 


**Example Case for Area:**

```
@pert_monte_carlo
def rectangle_area(calculation, rectangle_name, length, height):
	return height*length
	
results = rectangle_area(
    "Area",
    "rectangle_1",
    PERT(min=1.0,mode=2.0,max=3.0, label="length"),
    PERT(min=4.0,mode=5.0,max=6.0,label="height")
)
```

**Dependencies**

Leclerc uses the following packages:

* scipy 
```pip install scipy```
* numpy
```pip install numpy```
* bokeh
```pip install bokeh```
* matplotlib
```pip install matplotlib```
