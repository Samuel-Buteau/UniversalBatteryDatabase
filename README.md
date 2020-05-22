# Universal Battery Database

The Universal Battery Database is an open source software for managing Lithium-ion cell data. Its primary purposes are:
1. Organize and parse experimental measurement (e.g. long term cycling and electrochemical impedance spectroscopy) data files of Lithium-ion cells.
2. Perform sophisticated modelling using machine learning and physics-based approaches.
3. Describe and organize the design and chemistry information of cells (e.g. electrodes, electrolytes, geometry), as well as experimental conditions (e.g. temperature).
4. Automatically refresh a database as new data comes in.
5. Visualize experimental results.
6. Quickly search and find data of interest.
7. Quality control.

The Universal Battery Database was developed at the [Jeff Dahn Research Group](https://www.dal.ca/diff/dahn/about.html) at Dalhousie University.

## Table of Contents

- [Installation](#installation)
  * [Prerequisites](#prerequisites)
  * [Two Installation Options](#two-installation-options)
- [Using the Software](#using-the-software)
  * [ML Smoothing](#ml-smoothing)
- [Theoretical Physics and Computer Science Behind the Software](#theoretical-physics-and-computer-science-behind-the-software)
- [Contributing](#contributing)
  * [Code Conventions](#code-conventions)

## Installation

### Prerequisites

- [Python 3](https://www.python.org/downloads/)
- [pip and virtualenv](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

### Two Installation Options

1. If you only want to play around with modelling and you have a compiled dataset from somewhere else, you can [install without a database](https://github.com/Samuel-Buteau/universal-battery-database/wiki/Installing-Without-a-Database-(Windows)). This option is simpler and you can always install a database later.
2. If you want to use the full database features such as parsing and organising experimental data and metadata, you should [install with a database](https://github.com/Samuel-Buteau/universal-battery-database/wiki/Installing-With-a-Database-(Windows)).


## Using the Software

[Load the virtual environment](https://github.com/Samuel-Buteau/universal-battery-database/wiki/Loading-a-Python-environment.) containing the software in a new terminal.

To quickly see the web page and start developing, run
```
python3 manage.py runserver 0.0.0.0:8000
```
then visit `http://localhost:8000/` with a web browser.

When running the code in production, run
```bash
python3 manage.py process_tasks
```
in a separate terminal to allow background tasks (such as parsing data files). This will process the tasks as they are defined.

### ML Smoothing
cmd (Windows)
```cmd
>smoothing.bat path-figures dataset-version
````

Bash (macOS and Linux)
```Bash
$ sh smoothing.sh path-figures dataset-version
```

## Theoretical Physics and Computer Science Behind the Software

We hypothesize that we can make [good generalizations](https://github.com/Samuel-Buteau/universal-battery-database/wiki/Generalization-Criteria) by [approximating](https://github.com/Samuel-Buteau/universal-battery-database/wiki/The-Universal-Approximation-Theorem) the functions that map one degradation mechanism to another using neural networks. 

We aim to develop a theory of lithium-ion cells. We first break down the machine learning problem into smaller sub-problems. From there, we develop frameworks to convert the theory to practical implementations. Finally, we apply the method to experimental data and evaluate the result.

## Contributing

### Code Conventions

Generally, we follow [Google's Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md).
