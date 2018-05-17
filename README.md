magnum.fe
=========

**The open-source version of magnum.fe is currently not maintained any more.
Please have a look at the documentation of the commercial branch at [http://micromagnetics.org/magnum.fe](http://micromagnetics.org/magnum.fe) and [contact us](http://micromagnetics.org/about/) if you are interesed in an evaluation copy of magnum.fe.**

magnum.fe is a finite-element package for the solution of dynamical micromagnetic problems. It is written in Python and C++ and largely relies on the multi purpose finite-element library [FEniCS](http://fenicsproject.org/). For the solution of open-boundary problems a hybrid FEM/BEM method is implemented that uses the [BEM++](http://www.bempp.org/) library. magnum.fe is free software and can be extended to your needs.

To get started, visit http://micromagnetics.org/magnum.fe .

Features
--------
* Integration of the Landau-Lifshitz-Gilbert Equation
* Demagnetization-field computation via shell transformation or hybrid FEM/BEM method
* Oersted-field computation via shell transformation or hybrid FEM/BEM method
* Solution of the spin-diffusion model

Installation
------------
### Prerequisites
magnum.fe requires the following software/libraries to be installed:

* FEniCS = 1.5
* CMake >= 2.8
* SWIG >= 2.0
* G++ >= 4.0
* dev-version of CBC.Block (optional)
* BEM++ 2.0.3 python-pseudoinverse branch (optional)

#### Install dependencies in Ubuntu 14.04
Install FEniCS

    $ sudo add-apt-repository ppa:fenics-packages/fenics
    $ sudo apt-get update
    $ sudo apt-get install fenics

Install build dependencies

    $ sudo apt-get install g++ swig cmake

Install CBC.Block

    $ git clone https://bitbucket.org/fenics-apps/cbc.block.git
    $ cd cbc.block
    $ sudo python setup.py install

For installation of BEM++, see http://www.bempp.org/.

### Build and install
To build magenum.fe with cmake do

    $ cd /path/to/magnum.fe
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make
    $ sudo make install

### Create docker container
magnum.fe can be virtualized with docker (http://www.docker.com) for easy deployment to other machines.
In order to create a docker container run

    $ cd /path/to/magnum.fe
    $ sudo docker build .

This procedure should download all necessary software and install magnum.fe into the container.
You need Docker >= 1.0 to build the container.

### Test
You can test your installation by running the unit tests

    $ cd tests
    $ python run_all.py

### Build documentation
The following applies to Ubuntu.

Install sphinx

    $ sudo apt-get install python-sphinx

Install RTD theme

    $ sudo apt-get install python-pip
    $ sudo pip install sphinx_rtd_theme

Generate documentation (HTML)

    $ cd /path/to/magnum.fe/doc
    $ make html

License and Disclaimer
----------------------
magnum.fe is free software: you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

magnum.fe is distributed in the hope that it will be useful, but without any warranty; without even the implied warranty of merchantability or fitness for a particular purpose. See the GNU Lesser General Public License for more details.
