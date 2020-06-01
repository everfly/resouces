# Install CDF Library

Installation on Linux requires both a C and a Fortran compiler; a recent GCC is recommended (the C compiler is likely included with your distribution). Also it is recommended to install the ncurses library; on Ubuntu and Debian:

`sudo apt install gfortran ncurses-dev -y`

## Dependencies via conda

Install Miniconda as the base conda development environment:

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
```

Installation via `pip` will automatically install most Python dependencies (but not the [NASA CDF library](https://spacepy.github.io/install_linux.html#linux-cdf)). They can also be installed from conda:

```
conda install numpy scipy matplotlib networkx h5py
pip install pycdf
```

## Dependencies via system packages

SpacePy usually works with the system Python on Linux. To install dependencies via the package manager on Debian or Ubuntu:

`sudo apt install python-dev python-h5py python-matplotlib python-networkx python-numpy python-scipy`

For Python 3, use:

`sudo apt install python3-dev python3-h5py python3-matplotlib python3-networkx python3-numpy python3-scipy`

Download the [latest CDF library](https://spdf.gsfc.nasa.gov/pub/software/cdf/dist/cdf37_1/cdf-dist-all.tar.gz "Download 3.7.1"). Choose the file ending in `-dist-all.tar.gz` from the linux directory. Untar `tar -zxvf cdf-dist-all.tar.gz` and cd into the resulting directory. Then build:

`make OS=linux ENV=gnu CURSES=yes FORTRAN=no UCOPTIONS=-O2 SHARED=yes all`

Use `CURSES=no` if the curses library is not installed. (The distribution-specific directions above will install curses.)

Install:

`sudo make install`

This will install the library into the default location ~~/usr/local/cdf~~, where SpacePy can find it. If you choose to install elsewhere, see the CDF documentation, particularly the notes on the `CDF_BASE` and `CDF_LIB` environment variables. SpacePy uses these variables to find the library.

## Install on MacOS

Download the precompiled version at <https://spdf.gsfc.nasa.gov/pub/software/cdf/dist/cdf37_1/macosx/cdf37_1_0-setup_universal_binary.tar.gz>

At the installation step, choose a custom path to install such as `/Home/Users/Your_User_Name/Your_Wanted_Place/`, And the CDF Library Path is located at `/Home/Users/Your_User_Name/Your_Wanted_Place/lib/`
