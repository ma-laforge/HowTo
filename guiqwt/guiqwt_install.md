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

 1. [Install PyPlot (+Anaconda)](julia/julia_install.md#PyPlot): To avoid headaches, ensure PyPlot is working once Anaconda is installed.

 1. Download/install Pierre's Python libraries, ensuring `$PATH` still makes Anaconda the default `python`:

		git clone https://github.com/PierreRaybaut/guidata.git
		git clone https://github.com/PierreRaybaut/PythonQwt.git
		git clone https://github.com/PierreRaybaut/guiqwt.git
		cd guidata; python setup.py install
		cd ../PythonQwt; python setup.py install
		cd ../guiqwt; python setup.py build install

 1. Test guiqwt installation:

		$ guiqwt-tests

 1. Re-test Julia/PyPlot installation:

		julia> using PyPlot

# guiqwt Installation (Other platforms)

Unclear at the moment.

