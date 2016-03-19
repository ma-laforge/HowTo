# guiqwt How-To

# Description
guiqwt includes a "set of tools for curve and image plotting".  It also includes "GUI-based application development helpers".  Based on PythonQwt.

## Dependencies

 - **guiqwt**: <https://github.com/PierreRaybaut/guiqwt>
 - **PythonQwt**: <https://github.com/PierreRaybaut/PythonQwt>
  - Replaces **PyQwt** (below)?
 - **guidata**: <https://github.com/PierreRaybaut/guidata>
 - **PyQwt**: <http://pyqwt.sourceforge.net/home.html>
  - *Download page*? <http://sourceforge.net/projects/pyqwt/files/pyqwt5/>
  - *Source now on github*? <https://github.com/PyQwt/PyQwt5>
 - **Qwt**: Qt Widgets for Technical Applications (C++) <http://qwt.sourceforge.net/>

<a name="Py27Installation"></a>
# guiqwt Installation (Ubuntu/Anaconda/Python 2.7)

**Warning**: At the time of writing, the procedure required to successfully install guiqwt dependencies is poorly understood by the author.  Please refer to the original dependency documentation for more detailed installation instructions.

 1. Install (hopefully all) guiqwt dependencies using aptitude:

		# Will only register with Python provided by Ubuntu distribution:
		sudo apt-get install python-guiqwt

 1. [Install PyPlot (+Anaconda)](../julia/julia_install.md#PyPlot): To avoid headaches, ensure PyPlot is working once Anaconda is installed.

 1. Install guiqwt & dependencies, ensuring `$PATH` still makes Anaconda the default `python`:

		pip install guidata
		pip install pythonqwt
		pip install guiqwt

 1. Test guiqwt installation:

		$ guiqwt-tests

 1. Re-test Julia/PyPlot installation:

		julia> using PyPlot

## Working Package Set

The following list describes list of dependencies/versions that are known to work:

### Working set A

 - SciPy 0.17.0
 - NumPy 1.10.4
 - Pillow 3.1.1
 - guiqwt 3.0.2
 - PythonQwt 0.5.5
 - guidata 1.7.5

# guiqwt Installation (Other platforms)

Unclear at the moment.

# guiqwt Installation Issues (**No longer relevant**)

**NOTE:** Above installation now appears to work.  This section is merely left behind to help users that might experience similar installation issues.

The above installation instructions have been observed to generate a less-than-optimal guiqwt solution, though the reason is poorly understood.

**Observed Symptoms**

 - Solution mostly works.
 - Plotting is slower than with an optimal install.
 - Plotting will hang (mostly when dealing with large datasets?).

**Workaround (Ubuntu)**

For the moment, a workaround for the Ubuntu platform is to use the version of Python provided by aptitude:

 - python 2.7.6
 - numpy 1.8.2
 - guidata 1.6.1
 - guiqwt 2.3.1
 - other relevant packages??

Steps:

 1. Install guiqwt package:

		sudo apt-get install python-guiqwt

 1. Erase all installed Julia packages:

		$ rm -rf ~/.julia

 1. Remove anaconda distribution from active path.  Confirm that `python` points to default distribution, `/usr/bin/python`:

		$ which python

 1. Rebuild PyCall & try loading it:

		$ julia
		julia> Pkg.build("PyCall")
		julia> using PyCall

 1. Re-install C-Data 

