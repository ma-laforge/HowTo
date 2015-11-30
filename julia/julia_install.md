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
# PyPlot Package Installation

 1. [Install Anaconda](../conda/conda_install.md#Py27Installation) from Continuum Analytics - a well maintained distribution of Python.

 1. Lanuch Julia:

		$ julia

 1. Update Julia packages:

		julia> Pkg.update()

 1. Add PyPlot package:

		julia> Pkg.add("PyPlot")

Should the installation fail, please refer to the main PyPlot repository on Github: <https://github.com/stevengj/PyPlot.jl>.
