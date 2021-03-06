
![Build Status](https://travis-ci.org/henices/Tcp-DNS-proxy.svg?branch=master)

How to use this python script ?
-------------------------------

1.    change your dns server to 127.0.0.1

   ```bash
  $ vi /etc/resolve.conf  
  nameserver 127.0.0.1
  ```
2.    restart the network

  ```bash
  $ sudo /etc/init.d/networking restart
  ```
3.    run the script

  ```bash
  $ sudo python tcpdns.py -f tcpdns.json
  ```
  
  
Configuration file
----------------------------

``` json
{
    "socket_timeout": 20,
    "tcp_dns_server": ["8.8.8.8:53",
                       "8.8.4.4:53",
                       "156.154.70.1:53",
                       "156.154.71.1:53",
                       "208.67.222.222:53",
                       "208.67.220.220:53",
                       "74.207.247.4:53",
                       "209.244.0.3:53",
                       "8.26.56.26:53"],
    "udp_dns_server": ["208.67.222.222:5353"],
    "enable_lru_cache": true,
    "lru_cache_size"  : 100,
    "use_gevent"      : false,
    "udp_mode"        : false,
    "daemon_process"  : false,
    "private_host"     : {"*google.com": "203.117.34.162"}
}


```

  
Dependencies
----------------------------

### libraries
   * [libev] (http://libevent.org/)

### python moudules
   * [gevent] (https://github.com/surfly/gevent)
   * [pylru] (https://github.com/jlhutch/pylru)
   * [python-daemon] (https://pypi.python.org/pypi/python-daemon)

INSTALL
---------------------

### Super-quick installation

#### Linux system

```bash

  chmod +x ./install.sh
  ./install.sh
```

#### Windows system

Use tcpdns.exe in win directory.


### Manual Installation


#### Ubuntu or Debian installation guide

1. Use the following commands to install python modules

   ```bash
   
     sudo apt-get install libevent-dev
     sudo apt-get install python-pip
     sudo pip install gevent
     sudo pip install python-daemon
   ```

2. Pull the submodule source code.

   ```bash
     cd Tcp-DNS-proxy
     git submodule update --init --recursive
   ```

#### Windows installation guide
   
   In order to build gevent library you should install Visual Studio, 
   although tcpdns.py can run perfectly without python gevent.
   
   
1. Pull the submodule source code.
   ```bash
     cd Tcp-DNS-proxy
     git submodule update --init --recursive
   ```

2. Install pip.exe

   Download get-pip.py from [get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py),
   execute the following commands:
   
   ```
   python get-pip.py
   ```
3. Install python gevent
   
   ```
   C:\Python27\Scripts\pip.exe install gevent
   ```


LICENSE
----------------------

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License 
as published by the Free Software Foundation, either version 2 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty
of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see 
http://www.gnu.org/licenses/
