Requirements:
-------------------------
Generic:
* Dime (Daemon or Qt-Wallet)
* Python
* Twisted
* python-argparse (for Python <=2.6)

Linux:
* sudo apt-get install python-zope.interface python-twisted python-twisted-web
* sudo apt-get install python-argparse # if on Python 2.6 or older

Windows:
* Install Python 2.7: http://www.python.org/getit/
* Install Twisted: http://twistedmatrix.com/trac/wiki/Downloads
* Install Zope.Interface: http://pypi.python.org/pypi/zope.interface/3.8.0
* Install python win32 api: http://sourceforge.net/projects/pywin32/files/pywin32/Build%20218/
* Install python win32 api wmi wrapper: https://pypi.python.org/pypi/WMI/#downloads
* Unzip the files into C:\Python27\Lib\site-packages

Running P2Pool:
-------------------------
To use P2Pool, you must be running your own local bitcoind. For standard
configurations, using P2Pool should be as simple as:

    python run_p2pool.py

Then run your miner program, connecting to 127.0.0.1 on port 9332 with any
username and password.

If you are behind a NAT, you should enable TCP port forwarding on your
router. Forward port 9333 to the host running P2Pool.

Run for additional options.

    python run_p2pool.py --help

Donations towards further development:
-------------------------
    1HNeqi3pJRNvXybNX4FKzZgYJsdTSqJTbk

Official p2pool wiki :
-------------------------
https://en.bitcoin.it/wiki/P2Pool

Alternate web front end :
-------------------------
* https://github.com/hardcpp/P2PoolExtendedFrontEnd

Notes for Dime:
=========================
Requirements:
-------------------------
In order to run P2Pool with the Dime network, you would need to build and install the
quark_hash_python module that includes the quark proof of work code that Dime uses for hashes.

https://github.com/Neisklar/quarkcoin-hash-python
Install this in the top level directory of p2pool-dime then:
./sudo python setup.py install


Linux:

    cd quarkcoin-hash-python
    sudo python setup.py install

Windows (mingw):
* Install MinGW: http://www.mingw.org/wiki/Getting_Started
* Install Python 2.7: http://www.python.org/getit/

In bash type this:

    cd quarkcoin-hash-python
    C:\Python27\python.exe setup.py build --compile=mingw32 install

Windows (microsoft visual c++)
* Open visual studio console

In bash type this:

    SET VS90COMNTOOLS=%VS110COMNTOOLS%	           # For visual c++ 2012
    SET VS90COMNTOOLS=%VS100COMNTOOLS%             # For visual c++ 2010
    cd litecoin_scrypt
    C:\Python27\python.exe setup.py build --compile=mingw32 install
	
If you run into an error with unrecognized command line option '-mno-cygwin', see this:
http://stackoverflow.com/questions/6034390/compiling-with-cython-and-mingw-produces-gcc-error-unrecognized-command-line-o

Running P2Pool:
-------------------------
Run P2Pool with the "--net dimecoin" option.

Example $:
python run_p2pool.py --net dimecoin -w 54094 -f 1 -a CKSdw1ehX79EUaUJ3i9H5ZTmgA8VWQvrJC --give-author 0 -n 211.116.203.9 -n 75.69.84.211
