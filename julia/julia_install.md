<a name="Installation"></a>
# Julia: How-To Install

1. Go to the Julia language download page <http://julialang.org/downloads/>.
1. Download the distribution of Julia that best matches the requirements of your operating system.  The 64-bit version is highly recommended, if supported.
1. Follow the instructions described on the Julia website: <https://julialang.org/downloads/platform.html>.

## Julia Installation Issues

### `curl` Library (Ubuntu Instructions)

It might be necessary to install the `curl` library on Linux distributions.  Though `curl` is not directly needed by Julia, it is required by certain key packages.

On Ubuntu systems, the `curl` library can be installed with the following:

		sudo apt-get install curl

If `curl` still causes issues, it might be necessary to add a `~/.curlrc` file with the following content:

		cacert=/etc/ssl/certs/ca-certificates.crt

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
		$ conda install numpy=1.10.4 matplotlib=1.5.1

 1. Lanuch Julia:

		$ julia

 1. Rebuild PyPlot & try loading it:

		julia> Pkg.build("PyPlot")
		julia> using PyPlot

Should the installation still fail, please refer to the main PyPlot repository on Github: <https://github.com/stevengj/PyPlot.jl>.
