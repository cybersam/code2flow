### Updates from April 2021
- I've entered into a contract with generous sponsor to update code2flow
- The new version will support Python3, ECMAScript 2018, PHP8, & Ruby3
- Most of the project will be rewritten and licensed under the MIT license. As always, existing code never changes license.
- The domain, code2flow.com is unrelated to this project and as far as I can tell through the internet archive, they launched their service after this repository was created. I've never heard anything from them and it doesn't appear like they use anything from here.
- The pip install, code2flow, has been claimed by a different unrelated project. For now, *don't install* code2flow from pip. Scroll to the installation section for instructions.

code2flow
=========

Turn your Python and Javascript source code into DOT flowcharts

Code2flow will sweep through your project source code looking for function definitions. Then it will do another sweep looking for where those functions are called. Code2flow connects the dots and presents you with a flowchart estimating the functional structure of your program.

In other words, code2flow generates callgraphs

Code2flow is especially useful for untangling spaghetti code and getting new developers up to speed.

Code2flow is EXPERIMENTAL and meant to provide a **rough overview** of the structure of simpler projects. There are many known limitations (see below). **Expect MOST aspects of this application to change in future releases.**

Here is what happens when you run it on jquery
![Alt text](jqueryexample.png)

On the python calendar module
![Alt text](calendarexample.png)

On code2flow/languages/python.py
![Alt text](pythonexample.png)

Installation
------------

[Download](https://github.com/scottrogowski/code2flow/archive/master.zip), navigate to the directory, and run:

```bash
sudo python setup.py install
```

If you don't have it already, you will also have to install graphviz

Using apt-get:
```bash
sudo apt-get install graphviz
```

Using port (for macs):
```bash
sudo port install graphviz
```

Usage
-----

To generate a DOT file run something like:

```bash
code2flow mypythonfile.py
```

Or, for javascript

```bash
code2flow myjavascriptfile.js
```

By default, code2flow will render a DOT file, out.gv and a PNG file, out.png.

You can also render the flowchart in any of the formats that graphviz supports:
bmp canon cgimage cmap cmapx cmapx_np dot eps exr fig **gif** gv imap imap_np ismap jp2 jpe **jpeg** jpg pct pdf pic pict plain plain-ext **png** pov ps ps2 psd sgi **svg** svgz tga tif tiff tk vml vmlz x11 xdot xlib

For example:
```bash
code2flow mypythonfile.py -o myflow.jpeg
```

Specify multiple files, import directories, and even use *
```bash
code2flow project/directory/*.js
```

```bash
code2flow project/directory --language js
```


Limitations
-----------

Code2flow is meant to provide a reasonable conjecture of the structure of simple projects and has many known limitations.

* Arrays of functions are not handled
* The logic for whether or not a function returns is simply looking for 'return' in that function
* Functions not declared in the initial class/object definitions (e.g. attached later) are mostly not handled
* Dynamically generated and lambda functions are mostly not handled
* In python, functions inherited from a parent class are not handled
* In python, import ... as ... is not handled correctly
* In javascript, prototypes will result in unpredictable results
* And many more

Basically, code2flow may not diagram your sourcecode exactly as you might expect it to


Feedback / Bugs / Contact
-----------------------------

Please do email!
scottmrogowski@gmail.com


How to contribute
-----------------------

1. You can contribute code! The project is open source and is new so any reasonably useful feature would probably be helpful and accepted. New languages are especially appreciated!

2. You can spread the word! A simple way to help is to share this project with others. If you have a blog, mention code2flow! Linking from relevant questions on StackOverflow or other programming forums also helps quite a bit. I would do it myself but it is unfortunately against the community guidelines. The more exposure this project gets, the more I can devote my time to building it!


Feature / Language Requests
----------------

1. Code2flow is open source and contributions are welcome!

2. You can email me. I am an independent contractor and can be convinced to add more for a suitable amount of money :).
