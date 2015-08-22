---
layout: post
title:  "CMake cheat sheet"
date:   Thu Aug 20 21:49:18 HKT 2015
categories: blog
---

* TOC
{:toc}

Configure to link to specific OpenCV
-------------------------------------

Sometimes we have more than one version of OpenCV installed. To tell CMake
to link to OpenCV in a specific path, use

{% highlight cmake %}
set (OpenCV_DIR /OPENCV/INSTALL/PATH)
find_package (OpenCV REQUIRED)
{% endhighlight %}

The `/OPENCV/INSTALL/PATH` includes file `OpenCVConfig.cmake`


Loops
-----

{% highlight cmake %}
set (TARGETS 
    foo
    bar)

foreach (TARGET ${TARGETS})
    add_executable(${TARGET} ${TARGET}.cpp)
endforeach (TARGET)
{% endhighlight %}

Add flags
---------

{% highlight cmake %}
set (CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -mavx2")
set (CMAKE_C_FLAGS  "${CMAKE_C_FLAGS} -mavx2")
{% endhighlight %}

Set generator
-------------

For example, to use Xcode

{% highlight bash %}
cmake -G Xcode .
{% endhighlight %}

Debug command line options
--------------------------

{% highlight bash %}
# turn on debug
cmake -DCMAKE_BUILD_TYPE=DEBUG .
{% endhighlight %}


Macro definitions
------------------------

If in the code, there is something like this

{% highlight cpp %}
#ifdef NO_DEBUG
{% endhighlight %}

and you want to turn on `NO_DEBUG`, then use either of the following:

{% highlight cmake %}
# method 1 : valid for this directory and below
add_definitions(-DNO_DEBUG) 
# method 2
set (CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -DNO_DEBUG") 
# method 3 : better control; can specify which target
set_target_properties(main PROPERTIES COMPILE_DEFINITIONS NO_DEBUG)
{% endhighlight %}

Install targets and files
-------------------------

The default installation prefix is `/usr/local`.

{% highlight cmake %}
install(TARGETS yscires DESTINATION lib)
install(FILES ${INCLD_SRCS} DESTINATION include/yscires)
{% endhighlight %}

To change default installation path

{% highlight bash %}
cmake -DCMAKE_INSTALL_PREFIX=/path
{% endhighlight %}

Link libraries
--------------

If on command line we have :

    g++ main.cpp -lfoo -o main

Then in CMake:

{% highlight cmake %}
add_executable (main main.cpp)
target_link_libraries (main foo)
{% endhighlight %}

Sometimes we need to specify the path of the library (as in the case
that Xcode don't look for libraries in `/usr/local/lib`):

{% highlight cmake %}
find_library (FOO NAMES foo PATHS /usr/local/lib)
add_executable (main main.cpp)
target_link_libraries (main ${FOO})
{% endhighlight %}
