# Julia How-To

<a name="Installation"></a>
# Julia Installation

## Ubuntu Distributions

 1. From the linux shell, run the following commands:

		$ sudo add-apt-repository ppa:staticfloat/juliareleases
		$ sudo apt-get update
		$ sudo apt-get install julia

Should the installation fail, try following the instructions for other operating systems/platforms ([below](#InstallationDefault)).

<a name="InstallationDefault"></a>
## Other Operating Systems/Platforms

 1. Go to the Julia language download page <http://julialang.org/downloads/>.
 1. Download the distribution of Julia that best matches the requirements of your operating system.  The 64-bit version is highly recommended, if supported.
 1. Follow the installation instructions from the Julia website.

<a name="PyPlot"></a>
# PyPlot Package Installation (bash)

 1. [Install Anaconda](../conda/conda_install.md#Py27Installation) from Continuum Analytics - a well maintained distribution of Python.

 1. Make sure the new Anaconda distribution is used by default:

		$ export PATH=[PATH_TO_ANACONDA]/bin:$PATH

 1. Lanuch Julia:

		$ julia

 1. Install PyPlot & try loading it:

		julia> Pkg.update()
		julia> Pkg.add("PyPlot")
		julia> using PyPlot

## PyPlot Installation Issues

The PyPlot installation is usually fairly robust.  However, at the time of writing, some of the newer distributions appear to be suffer installation issues.  The following tries to solve known issues if the direct installation failed.

 1. Make sure the new Anaconda distribution is default (NOTE: Anaconda 2.4.1/64-bit is known to work):

		$ export PATH=[PATH_TO_ANACONDA]/bin:$PATH

 1. Ensure Anaconda uses a working package set.  At the time of writing, the following seems to work:

		# Seems to require all packages specified on a single call:
		$ conda install numpy=1.9.0 python=2.7.8 cairo=1.12.2 matplotlib=1.4

 1. Lanuch Julia:

		$ julia

 1. Rebuild PyPlot & try loading it:

		julia> Pkg.build("PyPlot")
		julia> using PyPlot

Should the installation still fail, please refer to the main PyPlot repository on Github: <https://github.com/stevengj/PyPlot.jl>.
