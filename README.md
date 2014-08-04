# Skyline dynamic data generator 

**Version 2.0** currently it is only implemented to run in an **Unix** environment.

Generator of dynamic data following the structure of a sensor net. For the relations between the data Kossman skyline generator was used.

## Set up ##

#### Install python 2.7 ####
* Ubuntu/Debian:       
```sudo apt-get install python2.7```
* Fedora:       
```sudo yum install python2.7```
* Arch:         
```sudo pacman install python2.7```

#### Install pip through package manager ####
* Ubuntu/Debian:      
```sudo apt-get install python-pip```
* Fedora:      
```sudo yum install python-pip```
* Arch:       
```sudo pacman install python-pip```

#### Python dependencies ####
* numpy      
```pip install numpy```
* linecache
```pip install linecahce```
* python resources <https://pypi.python.org/pypi/python-resources/0.3>

## Usage ##

### General options ###

For getting a specific dataset:
~~~~~
builder [options] -o <outputfile> -s <size> -d <dimentions> 
~~~~~

For getting a dataset randomly generated:
~~~~~
builder  -o <outputfile> --autodataset
~~~~~

For getting a tiny dataset (ideal for test):
~~~~~
builder  -o <outputfile> --autotiny
~~~~~

### Specific options ###

```option```                 | Function
-----------------------------| -------------
```-v```                     | verbose output
```--time```                 | specify the simulation time. Output may exceed this parameter. By default is a random number between 0 and 1800
```--arrivals <num>```       | sepcify how many arrivals per tuple will be generated by default poisson distribution is used
```--poissparameter <num>``` | poisson parameter to use when generating arrival events. The parameter specifies average arrival events per minute (defaut is a random number between 1 and 10)
```--poissarray <string>```  | specify a string containg poisson parameters separated with an '%' (used when different poisson parameters will be used to generate arrival events) example: --poissarray 5%2%10 for 3 dimentions
```--testcases <num>```      | generate different testcases according to the same file
```--leavereport```          | leave a report file describing the parameters used to create the testcase(s)
```--leavesettings <file>``` | leave a report similar to that generated with leavereport but adjusted to the Dynasty Algorithm input. The report will be appended to the file specified
```--expirations```          | specify when a value expires for each dimention. This value will not affect testcases generation, but will be used for report and written to settings if --leavesettings option is indicated. Input is a string containg expiration values separated with an '%'. Example: --expirations 5%2%10 for 3 dimentions
```--resume  <file>```       | resume execution from specified tmp file
```--dontdelete```           | keep kossmann tmp file (default is delete the file)
```--autodataset```          | generate medium to small random parameters for the entire dataset (to generate a quick and dirty dataset for tests)
```--autotiny```             | like --autodataset but generating a tiny dataset (to generate a quick and dirty tiny dataset for control)
```--anticorrelated```       | use anticorrelated data distribution
```--correlated```           | use correlated data distribution
```--uniform```              | use uniform data distribution (default)
```--distributearr```        | data distribution refers to arrivals (default)
```--distributedim```        | data distribution refers to dimentions 
```--rarrival```             | generate random arrival times, instead of exponential
