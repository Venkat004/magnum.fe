magnum.fe
=========

Installation
------------

### Prerequisites
magnum.fe requires the following software/libraries to be installed:

* FEniCS >= 1.4
* Gmsh >= 2.8.0 (headers and library)
* CMake >= 2.8
* SWIG >= 2.0
* G++ >= 4.0
* dev-version of CBC.Block (optional)
* BEM++ 2.0.1 (optional)

#### Install dependencies in Ubuntu 14.04
Install FEniCS

    $ sudo add-apt-repository ppa:fenics-packages/fenics
    $ sudo apt-get update
    $ sudo apt-get install fenics

Install Gmsh with headers and build dependencies

    $ sudo apt-get install libgmsh-dev g++ swig cmake

Install CBC.Block

    $ git clone https://bitbucket.org/fenics-apps/cbc.block.git
    $ cd cbc.block
    $ sudo python setup.py install

For installation of BEM++, see http://www.bempp.org/. magnum.fe requires the H-matrix library AHMED 1.0 that is optional for BEM++, see http://bebendorf.ins.uni-bonn.de/AHMED.html.

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

    $ cd /path/to/magnum.fe/docker
    $ cp /path/to/AHMED-1.0.tar.gz .
    $ sudo docker build .

You need Docker >= 1.0 to build the container. Note that you have to place the AHMED 1.0 tarball in the `docker` directory for a successfull build (http://bebendorf.ins.uni-bonn.de/AHMED.html).

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

License
-------
Released under the GNU General Public License 3 (included).
