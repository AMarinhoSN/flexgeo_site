+++
title = "Installation"
date = 2018-12-29T17:44:21+01:00
weight = 2
chapter = true
pre = "<b>2. </b>"
+++

# Installation

**1. Download FleXgeo**

  The easiest way is simply run:

```{bash}
 $ git clone https://github.com/AMarinhoSN/FleXgeo.git
 ```

If you are not familiar with *git clone*, you can just download from [FleXgeo github repository](https://github.com/AMarinhoSN/FleXgeo)


**2. Install requirements**

To run the analyses scripts you need [Python 3](https://www.python.org/download/releases/3.0/) and you can install the required python libraries using [pip3](https://pip.pypa.io/en/stable/installing/). You can install the python libraries directly on your default python environment using:

```{bash}
$ pip3 install cython
$ pip3 install -r /path/to/FleXgeo/requirements.txt  
```
  Another option is to create a specific FleXgeo python environment using *virtualenv* by:

```{bash}
$ pip3 install virtualenv
$ cd virtual_envs_location
$ virtualenv flexgeo_env
$ source flexgeo_env/bin/activate
$ cd FLEXGEO_LOCATION
$ pip3 install cython
$ pip3 install -r requirements.txt
```

You also gonna need [Lua](https://www.lua.org/start.html) interpreter to compute $d_{max}$. On Linux, you can install it by:

```{bash}
 $ sudo apt-get install luajit
```

If you want to access run FleXgeo easily on Linux terminal, just add `alias flexgeo='/full/path/to/FleXgeo/bin/FleXgeo_[MY_OS]'`, at my "MY_OS" you can choose between 'LINUX', 'MacOS_10.13.4' and 'WIN_10_64'

{{% notice note %}}
Here we assume you are a sane person and is working on a Linux environment. Everything should work similarly on MacOS and Windows, if you find any OS specific error (or of any other kind) feel free to check and create an issue at [FleXgeo repository](https://github.com/AMarinhoSN/FleXgeo/issues).
{{% /notice %}}
