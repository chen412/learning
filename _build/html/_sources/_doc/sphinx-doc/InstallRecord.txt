執行記錄
========

安裝SPHINX-DOC
--------------
**執行指令:**  sudo apt-get install python3-sphinx

.. code-block:: text

	allen@ubuntu:~$ sudo apt-get install python3-sphinx
	Reading package lists... Done
	Building dependency tree       
	Reading state information... Done
	The following extra packages will be installed:
	  docutils-common libjs-jquery libjs-sphinxdoc libjs-underscore
	  python3-docutils python3-jinja2 python3-pil python3-pygments python3-roman
	  sphinx-common
	Suggested packages:
	  javascript-common texlive-latex-recommended texlive-latex-base
	  texlive-lang-french fonts-linuxlibertine ttf-linux-libertine docutils-doc
	  python-jinja2-doc python-pil-doc python3-pil-dbg ttf-bitstream-vera jsmath
	  libjs-mathjax dvipng texlive-latex-extra texlive-fonts-recommended
	  sphinx-doc
	The following NEW packages will be installed:
	  docutils-common libjs-jquery libjs-sphinxdoc libjs-underscore
	  python3-docutils python3-jinja2 python3-pil python3-pygments python3-roman
	  python3-sphinx sphinx-common
	0 upgraded, 11 newly installed, 0 to remove and 0 not upgraded.
	Need to get 2,228 kB of archives.
	After this operation, 10.4 MB of additional disk space will be used.
	Do you want to continue? [Y/n] y
	Get:1 http://tw.archive.ubuntu.com/ubuntu/ trusty/main docutils-common all 0.11-3 [143 kB]
	Get:2 http://tw.archive.ubuntu.com/ubuntu/ trusty/main libjs-jquery all 1.7.2+dfsg-2ubuntu1 [78.8 kB]
	Get:3 http://tw.archive.ubuntu.com/ubuntu/ trusty/main libjs-underscore all 1.4.4-2ubuntu1 [45.6 kB]
	Get:4 http://tw.archive.ubuntu.com/ubuntu/ trusty-updates/main libjs-sphinxdoc all 1.2.2+dfsg-1ubuntu1.1 [41.4 kB]
	Get:5 http://tw.archive.ubuntu.com/ubuntu/ trusty/main python3-roman all 2.0.0-1 [7,836 B]
	Get:6 http://tw.archive.ubuntu.com/ubuntu/ trusty/main python3-docutils all 0.11-3 [347 kB]
	Get:7 http://tw.archive.ubuntu.com/ubuntu/ trusty/main python3-jinja2 all 2.7.2-2 [163 kB]
	Get:8 http://tw.archive.ubuntu.com/ubuntu/ trusty/main python3-pil amd64 2.3.0-1ubuntu3 [281 kB]
	Get:9 http://tw.archive.ubuntu.com/ubuntu/ trusty/main python3-pygments all 1.6+dfsg-1ubuntu1 [458 kB]
	Get:10 http://tw.archive.ubuntu.com/ubuntu/ trusty-updates/main sphinx-common all 1.2.2+dfsg-1ubuntu1.1 [392 kB]
	Get:11 http://tw.archive.ubuntu.com/ubuntu/ trusty-updates/main python3-sphinx all 1.2.2+dfsg-1ubuntu1.1 [270 kB]
	Fetched 2,228 kB in 23s (95.0 kB/s)                                            
	Selecting previously unselected package docutils-common.
	(Reading database ... 167021 files and directories currently installed.)
	Preparing to unpack .../docutils-common_0.11-3_all.deb ...
	Unpacking docutils-common (0.11-3) ...
	Selecting previously unselected package libjs-jquery.
	Preparing to unpack .../libjs-jquery_1.7.2+dfsg-2ubuntu1_all.deb ...
	Unpacking libjs-jquery (1.7.2+dfsg-2ubuntu1) ...
	Selecting previously unselected package libjs-underscore.
	Preparing to unpack .../libjs-underscore_1.4.4-2ubuntu1_all.deb ...
	Unpacking libjs-underscore (1.4.4-2ubuntu1) ...
	Selecting previously unselected package libjs-sphinxdoc.
	Preparing to unpack .../libjs-sphinxdoc_1.2.2+dfsg-1ubuntu1.1_all.deb ...
	Unpacking libjs-sphinxdoc (1.2.2+dfsg-1ubuntu1.1) ...
	Selecting previously unselected package python3-roman.
	Preparing to unpack .../python3-roman_2.0.0-1_all.deb ...
	Unpacking python3-roman (2.0.0-1) ...
	Selecting previously unselected package python3-docutils.
	Preparing to unpack .../python3-docutils_0.11-3_all.deb ...
	Unpacking python3-docutils (0.11-3) ...
	Selecting previously unselected package python3-jinja2.
	Preparing to unpack .../python3-jinja2_2.7.2-2_all.deb ...
	Unpacking python3-jinja2 (2.7.2-2) ...
	Selecting previously unselected package python3-pil.
	Preparing to unpack .../python3-pil_2.3.0-1ubuntu3_amd64.deb ...
	Unpacking python3-pil (2.3.0-1ubuntu3) ...
	Selecting previously unselected package python3-pygments.
	Preparing to unpack .../python3-pygments_1.6+dfsg-1ubuntu1_all.deb ...
	Unpacking python3-pygments (1.6+dfsg-1ubuntu1) ...
	Selecting previously unselected package sphinx-common.
	Preparing to unpack .../sphinx-common_1.2.2+dfsg-1ubuntu1.1_all.deb ...
	Unpacking sphinx-common (1.2.2+dfsg-1ubuntu1.1) ...
	Selecting previously unselected package python3-sphinx.
	Preparing to unpack .../python3-sphinx_1.2.2+dfsg-1ubuntu1.1_all.deb ...
	Unpacking python3-sphinx (1.2.2+dfsg-1ubuntu1.1) ...
	Processing triggers for man-db (2.6.7.1-1) ...
	Processing triggers for shared-mime-info (1.2-0ubuntu3) ...
	Processing triggers for sgml-base (1.26+nmu4ubuntu1) ...
	Setting up docutils-common (0.11-3) ...
	Setting up libjs-jquery (1.7.2+dfsg-2ubuntu1) ...
	Setting up libjs-underscore (1.4.4-2ubuntu1) ...
	Setting up libjs-sphinxdoc (1.2.2+dfsg-1ubuntu1.1) ...
	Setting up python3-roman (2.0.0-1) ...
	Setting up python3-jinja2 (2.7.2-2) ...
	Setting up python3-pil (2.3.0-1ubuntu3) ...
	Setting up python3-pygments (1.6+dfsg-1ubuntu1) ...
	Setting up sphinx-common (1.2.2+dfsg-1ubuntu1.1) ...
	Processing triggers for sgml-base (1.26+nmu4ubuntu1) ...
	Setting up python3-docutils (0.11-3) ...
	update-alternatives: using /usr/share/docutils/scripts/python3/rst-buildhtml to provide /usr/bin/rst-buildhtml (rst-buildhtml) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2html to provide /usr/bin/rst2html (rst2html) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2latex to provide /usr/bin/rst2latex (rst2latex) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2man to provide /usr/bin/rst2man (rst2man) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2odt to provide /usr/bin/rst2odt (rst2odt) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2odt_prepstyles to provide /usr/bin/rst2odt_prepstyles (rst2odt_prepstyles) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2pseudoxml to provide /usr/bin/rst2pseudoxml (rst2pseudoxml) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2s5 to provide /usr/bin/rst2s5 (rst2s5) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2xetex to provide /usr/bin/rst2xetex (rst2xetex) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rst2xml to provide /usr/bin/rst2xml (rst2xml) in auto mode
	update-alternatives: using /usr/share/docutils/scripts/python3/rstpep2html to provide /usr/bin/rstpep2html (rstpep2html) in auto mode
	Setting up python3-sphinx (1.2.2+dfsg-1ubuntu1.1) ...

建立SPHINX-DOC專案
------------------
**執行指令:**  sphinx-quickstart

.. code-block:: text

	 allen@ubuntu:~$ sphinx-quickstart
	Welcome to the Sphinx 1.2.2 quickstart utility.

	Please enter values for the following settings (just press Enter to
	accept a default value, if one is given in brackets).

	Enter the root path for documentation.
	> Root path for the documentation [.]: sphinx_test

	You have two options for placing the build directory for Sphinx output.
	Either, you use a directory "_build" within the root path, or you separate
	"source" and "build" directories within the root path.
	> Separate source and build directories (y/n) [n]: y

	Inside the root directory, two more directories will be created; "_templates"
	for custom HTML templates and "_static" for custom stylesheets and other static
	files. You can enter another prefix (such as ".") to replace the underscore.
	> Name prefix for templates and static dir [_]:

	The project name will occur in several places in the built documentation.
	> Project name: test
	> Author name(s): 陳國華

	Sphinx has the notion of a "version" and a "release" for the
	software. Each version can have multiple releases. For example, for
	Python the version is something like 2.5 or 3.0, while the release is
	something like 2.5.1 or 3.0a1.  If you don't need this dual structure,
	just set both to the same value.
	> Project version: 1.0
	> Project release [1.0]:

	The file name suffix for source files. Commonly, this is either ".txt"
	or ".rst".  Only files with this suffix are considered documents.
	> Source file suffix [.rst]:

	One document is special in that it is considered the top node of the
	"contents tree", that is, it is the root of the hierarchical structure
	of the documents. Normally, this is "index", but if your "index"
	document is a custom template, you can also set this to another filename.
	> Name of your master document (without suffix) [index]:

	Sphinx can also add configuration for epub output:
	> Do you want to use the epub builder (y/n) [n]: y

	Please indicate if you want to use one of the following Sphinx extensions:
	> autodoc: automatically insert docstrings from modules (y/n) [n]:
	> doctest: automatically test code snippets in doctest blocks (y/n) [n]:
	> intersphinx: link between Sphinx documentation of different projects (y/n) [n]:
	> todo: write "todo" entries that can be shown or hidden on build (y/n) [n]:
	> coverage: checks for documentation coverage (y/n) [n]:
	> pngmath: include math, rendered as PNG images (y/n) [n]:
	> mathjax: include math, rendered in the browser by MathJax (y/n) [n]:
	> ifconfig: conditional inclusion of content based on config values (y/n) [n]:
	> viewcode: include links to the source code of documented Python objects (y/n) [n]:

	A Makefile and a Windows command file can be generated for you so that you
	only have to run e.g. `make html' instead of invoking sphinx-build
	directly.
	> Create Makefile? (y/n) [y]:
	> Create Windows command file? (y/n) [y]:

	Creating file sphinx_test/source/conf.py.
	Creating file sphinx_test/source/index.rst.
	Creating file sphinx_test/Makefile.
	Creating  file sphinx_test/make.bat.

	Finished: An initial directory structure has been created.

	You should now populate your master file sphinx_test/source/index.rst and create other documentation
	source files. Use the Makefile to build the docs, like so:
	   make builder
	where "builder" is one of the supported builders, e.g. html, latex or linkcheck.