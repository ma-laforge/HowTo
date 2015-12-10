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
# guiqwt Installation (Linux/Python 2.7)

**Warning**: At this point in time, the procedure required to successfully install the dependencies is poorly understood by the author.  Please refer to the original dependency documentation for more detailed installation instructions.

 1. [Install Anaconda distribution of Python 2.7](conda/conda_install.md#Py27Installation)
 1. **Install PyQwt**? Install sip & Qwt5 packages:

		conda install sip
		conda install -c pkgw Qwt5

  - Make sure to have proper version of Python in your path.
  - Source for Qwt5 package obtained from: <https://anaconda.org/pkgw/qwt5>?

 1. Download/install Pierre's Python libraries:

		git clone https://github.com/PierreRaybaut/guidata.git
		cd guidata; python setup.py install
		git clone https://github.com/PierreRaybaut/PythonQwt.git
		cd PythonQwt; python setup.py install
		git clone https://github.com/PierreRaybaut/guiqwt.git
		cd guiqwt; python setup.py build install

# guiqwt Installation (Ubuntu)

The guiqwt package is relatively easy to install on an Ubuntu distribution:

		sudo apt-get install python-guiqwt

Unfortunately, this package does not register guiqwt with the Anaconda/Python 2.7 distribution.  The resulting installation will likely make it difficult to access guiqwt facilities through the Juila/PyCall.jl module.

# guiqwt Installation (Other platforms)

Unclear at the moment.

# Installation Issues

The above installation procedure has been observed to break the Matplotlib/Pyplot Anaconda/Julia installation for some reason.  The fix appears to be a partial re-install:

 1. Blow way the `~/.julia` subdirectory

 1. Remove Matplotlib:

		conda uninstall matplotlib

 1. Re-install Matplotlib:

		conda install matplotlib

 1. Re-install Julia libraries

		julia> Pkg.add("PyPlot")
		julia> Pkg.add("HDF5")
		...


