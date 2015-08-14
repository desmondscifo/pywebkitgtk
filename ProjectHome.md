# Related #

  * [HOWTO Create Python GUIs using HTML](http://www.aclevername.com/articles/python-webgui/)


# Project Description #

PyWebKitGtk allows Python (Gtk) developers to create software on top of the WebKitGtk rendering engine.

Screenshot of a sample web browser and Web Inspector:

![http://farm4.static.flickr.com/3259/3086536526_5072cc5919_o.jpg](http://farm4.static.flickr.com/3259/3086536526_5072cc5919_o.jpg)

# Using #

Firstly grab the pywebkitgtk package from your distribution. If you want to build from source, follow the steps below.

  1. Grab the source tarball at http://code.google.com/p/pywebkitgtk/downloads/list and extract it.
  1. Build the library by following the command lines below:
```
$ ./configure --prefix=/pywebkitgtk/install/path
$ make
$ make install
```

That's it. As an extra step, you can try the demo browser by following this step:
```
$ python demos/tabbed_browser.py
```

If you have installed pywebkitgtk in a non-standard location (i.e. not in /usr or /usr/local), you might want to use the following:

```
$ PYTHONPATH=/pywebkitgtk/install/path python demos/browser.py
```

Are you a user? &lt;wiki:gadget url="http://www.ohloh.net/projects/22820/widgets/project\_users\_logo.xml" height="43"  border="0" /&gt;

# Help? #

Need help on how to use pywebkitgtk? Got an idea and want to code it up? Then [let us know!](http://groups.google.com/group/pywebkitgtk)

