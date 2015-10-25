---
title:  "Cheat sheet for basic scripting with python"
layout: post
data:   2015-10-24 14:42:32.909475
categories: blog
---

I prefer python over shell scripts for basic scripting. 

* TOC
{:toc}


Equivalents of shell commands
-----------------------------

| shell commands | python  
|----------------|---------
|`cd`            | `os.chdir()`  
|`pwd`           | `os.getcwd()`  
|`ls`            | `os.listdir()`
|`rm <FILE>`     | `os.remove()`
|`rm -rf <DIR>`  | `shutil.rmtree()`
|`cp`            | `shutil.copy()` with [warning](https://docs.python.org/2/library/shutil.html)
|`cp -r`         | `shutil.copytree()`
|`mv`            | `shutil.move()`



Paths manipulation
-----------------
Let's say `fname = "/home/foo/a.cpp"`, then

| command                  | output  
|--------------------------|---------
|`os.path.split(fname)`    | `('/home/foo', 'a.cpp')`  
|`os.path.splitext(fname)` | `('/home/foo/a', '.cpp')`  
|`os.path.basename(fname)` | `a.cpp`  


Find files
----------
For finding files under current directory, we can use somthing like
`glob.glob("*.c")`. However, if we want to find recursively, as done by

{% highlight bash %}
find srcdir -name "*.c"
{% endhighlight %}

we need to (see [thread](http://stackoverflow.com/questions/2186525/use-a-glob-to-find-files-recursively-in-python))

{% highlight python %}
import os
import fnmatch

for root, dirs, fnames in os.walk("srcdir"):
    for f in fnmatch.filter(fnames, "*.c"):
        print os.path.join(root, f)
{% endhighlight %}

