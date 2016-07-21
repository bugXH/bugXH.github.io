---
layout: post
title: Add modules to Anaconda2
---
Today I installed Anaconda2, which helps to build a "hassle-free Python experience". Previously I had a custom module for coding. However, just adding the folder to pkgs/ doesn't work. I tried to build a conda package following this [tutorial](http://conda.pydata.org/docs/build_tutorials/pkgs2.html) but it doesn't work. So I add a setup.py file and installed it using pip (pip needs to be installed within Anaconda). The setup.py looks like:

{% highlight python %}
from setuptools import setup, find_packages

setup(
    name="XXX",
    packages=['XXX'],
    version="X.X.X",
    author='XXX XXX',
)
{% endhighlight %}

After installing the module using pip, use **conda list** to check.

**Update:**

After installing Anaconda, the python script that keeps my modified key-mapping working failed. The problem is that dbus and gobject are not installed in Anaconda. There are only some third party channels provide the packages. So I just change the "python" to "/usr/bin/python" in command of the start applications.
