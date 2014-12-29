BasicBenchmarker.py
===================

Python class to benchmark pieces of code by timer and resources usage.


Description
-----------

The object starts timer and usage capturing. 

The usage is not delimited to the piece of code but usage of whole operating 
system.

The start method is required to start the timer and usage recording.

The usage recording is optional and starts in a different thread at the same
time that timer.

Based on a Timer Class created by Frank Sebastia.


Usage
-----

Example of use with usage and memory in KB flag options enabled:

```
    >>> # Initializes object, set the usage and the memory in KB flag options
    >>> benchmarker = BasicBenchmarker(usage=True, memory_kb=True)
    
    >>> # Starts timer and usage if enabled
    >>> benchmarker.start()
    
    >>> # Put the piece of code to benchmark here
    >>> time.sleep(10)      # replace by your piece of code
    
    >>> # Stops timer and usage thread if enabled
    >>> benchmarker.stop()
    
    >>> # Gets key pairs with the relevant information
    >>> results = benchmarker.report()
    
        {'cpu_usage': 4.9, 'memory_usage': 2353964,
        'started_time': '2014-12-29T21:13:03.170977',
        'cpu_seconds': 0.01451, 'elapsed_seconds': 10.01,
        'stopped_time': '2014-12-29T21:13:13.181304'}
    
    >>> # Prints the relevant information
    >>> print benchmarker.report_to_str()
    
        Processing time 0.01 seconds
        Elapsed time 10.01 seconds
        CPU Usage 4.9 %
        Memory Usage 2353964 KB
```
    
    
Credits
-------

Jaume Mila Bea <jaume@westial.com>
Project home: https://github.com/westial/BasicBenchmarker.py


Requirements
------------

Python 2.7.3
psutil 2.1.3


License
-------

BasicBenchmarker is free software: you can redistribute it and/or modify it under 
the terms of the GNU General Public License as published by the Free Software 
Foundation, either version 3 of the License, or (at your option) any later 
version.

BasicBenchmarker is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS 
FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with 
BasicBenchmarker. If not, see http://www.gnu.org/licenses/.
