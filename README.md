# A Tool for the Estimation of Lattice Parameters
A `sage <sagemath.org>`_ library to find secure parameter sets of popular versions of lattice problems (LWE and SIS in their integer, ring, and module versions) given various :math:`\ell_p`-norms. 


## Setup
Install required Python packages by 

```
    pip install -r requirements.py
```

The tool can either be used as a submodule or installed as a Python library in your environment by running the setup script, e.g. by 

```
    python setup.py install
``` 

## Usage Examples

The main functionality of the library is encapsulated in the module [param_search.py](https://github.com/krebsni/a-tool-for-the-estimation-of-lattice-parameters/blob/main/lattice_parameter_estimation/param_search.py) which contains a generic search to find secure parameters for a given set of problems. In addition, the library includes moduls for distributions and $$\ell_p$$-norms and norm inequations that help to specify error and secret distributions and bounds. Classes for LWE and SIS and their variants can be found in [problem.py](https://github.com/krebsni/a-tool-for-the-estimation-of-lattice-parameters/blob/main/lattice_parameter_estimation/problem.py). The estimation can be configured in the configuration class in  [attacks.py](https://github.com/krebsni/a-tool-for-the-estimation-of-lattice-parameters/blob/main/lattice_parameter_estimation/algorithms.py). 

To start a parameter search simply import the module [param_search](https://github.com/krebsni/a-tool-for-the-estimation-of-lattice-parameters/blob/main/lattice_parameter_estimation/param_search.py) and ```generic_search``` with customized parameters. The library can also be installed as a python package by running the setup script. 

In Linux, you can run your script by

```
    sage <my_script>.py
```

Examples of what can be done with the module can be found in the script [usage_examples.py](https://github.com/krebsni/a-tool-for-the-estimation-of-lattice-parameters/blob/main/usage_examples.py)


Bugs
----
Sage 9.0 is known to have memory leaks. To mitigate the issue, it is recommended to avoid running multiple generic searches with memory heavy estimation algorithms (i.e. bkw-coded, arora-gb and primal-decoded) in the same script. Hopefully this issue will be resolved with Sage 9.3.
