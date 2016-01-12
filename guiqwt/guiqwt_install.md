# guiqwt How-To

# Description
guiqwt includes a "set of tools for curve and image plotting".  It also includes "GUI-based application development helpers".  Based on PythonQwt.

## Dependencies

 - **guidata**: <https://github.com/PierreRaybaut/guidata>
 - **PythonQwt**: <https://github.com/PierreRaybaut/PythonQwt>
  - Replaces **PyQwt** (below)?
 - **guiqwt**: <https://github.com/PierreRaybaut/guiqwt>
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

# guiqwt Installation (Other platforms)

Unclear at the moment.

# guiqwt Installation Issues

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

