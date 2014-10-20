***************
SPHINX-DOC 安裝
***************

目前對於一般使用者或系統開發者在記錄自已的學習心得的方式會隨著不同環境及狀況而所使用的工具有所不同，當在網路尚未普及到家家戶戶都接ADSL時，可能大都是寫在記事本、Microsft Office系列的文書軟體，但隨著網路的普及化加上全球資訊網出現，陸續出現BLOG、WIKI，到現在的雲端服務，如evernote、google雲端文件、Microsft Office系列等…，不論在桌上型電腦、筆記型電腦、平板、手機，在不同的作業系統都可以存取，但這些都注重於快速記事，如果要把所記錄的東西整合後出版到網路上公開，發佈成網頁、pdf、epub等格式，在出版這塊或許office是一般使用者最常用的，也可以發佈成PDF，而EPUB可以透過其他的軟體轉換，如果是發佈成網頁或許少數幾頁的文件是沒問題，大不了網頁內容長了點，但如果是一本書或使用手冊呢？將數十頁或數百頁的內容發佈成一個網頁，這就不太好觀看及使用了，這樣還需要花費更多的人力去建置網頁，檔案格式又不同了，當這個時後書本、使用手冊要改版時將會要修改多個版本的內容，再加上章節內容抽換時會出現文件格式變動的問題等…。上述的問題，在以建立書本、使用手冊為主，所要的需求如下：

* 編輯一份文件，即可同時發佈成網頁、PDF、EPUB等格式
* 在文件改版，可容易抽換章節內容
* 可在不同的文件編輯器上寫作
* 便於多人共筆寫作
  
綜合以上的需求，SPHINX-DOC可以幫我們完成這個任務
SPHINX-DOC有別於其他的文書出版軟體，SPHINX-DOC起初是為了創建新的 `PYTHON使用者手冊 <https://doc.python.org/3.5/index.html>`_ 而產生的，文件的內容是使用reStructuredText(reST)標記語言所編寫，reST是種跨平台及任何文字編號器都可以編輯，而且是個易讀的純文字標記語法，主要是透過Python中的Docutils元件將純文字轉換成不同的格式。

測試環境
========
* 作業系統：Ubuntu 14.04
* Python：3.4.0 
* SPHINX-DOC：1.2.2
* Apache：2.4.7

安裝SPHINX-DOC
==============
本系統使用python3的版本做架設，在ubuntu有sphinx-doc套件可以直接安裝，而且是最新的版本1.2.2的版本，套件有分Python2和Python3的版本，兩種版本所產生出來的內容經比對過後，主要差異在因為中文使用Unicode，使用Python2的版本所產生出來的內容，如果有中文字，在前方會加一個"u"。

**Python2和Python3中文差異**
 .. code-block:: text

	python2：project = u'中文專案' 
	python3：project = '中文專案'

**安裝sphinx使用python3**
 .. code-block:: text

   	sudo apt-get install python3-sphinx

**安裝sphinx使用python2**
 .. code-block:: text

   sudo apt-get install python-sphinx

`安裝執行畫面 <InstallRecord.html#sphinx-doc>`_

建立SPHINX-DOC專案
==================

`建立專案執行畫面 <InstallRecord.html#id2>`_

匯出HTML網站
============
在Ubuntu下，不論是Python2或是Python3都是用「 **make html** 」指令建立HTML網站

**匯出HTML指令**
 .. code-block:: text

	make html

**執行畫面**
 .. code-block:: text

	allen@uServer:~/git/allen$ make html
	sphinx-build -b html -d _build/doctrees   . _build/html
	Making output directory...
	Running Sphinx v1.2.2
	loading pickled environment... done
	building [html]: targets for 6 source files that are out of date
	updating environment: 0 added, 0 changed, 0 removed
	looking for now-outdated files... none found
	preparing documents... done
	writing output... [100%] index
	writing additional files... genindex search
	copying static files... done
	copying extra files... done
	dumping search index... done
	dumping object inventory... done
	build succeeded.

	Build finished. The HTML pages are in _build/html.

匯出PDF
=======
在全英文的內容下直接執行匯出PDF是沒有問題，但內容出現有中文的時後匯出就要做另外設定及中文字型的安裝與設定，如果Ubuntu是安裝中文版，文鼎字型會自動安裝好，英文版則需要自行安裝中文字型，安裝方式如下

**安裝文鼎標楷體與細明體**

 .. code-block:: text

	sudo apt-get install fonts-arphic-ukai fonts-arphic-uming

* fonts-arphic-ukai - 「文鼎 PL UKai」 (AR PL UKai) 中文萬國碼 TrueType 楷體字型
* fonts-arphic-uming - 「文鼎 PL UMing」 (AR PL UMing) 中文萬國碼 TrueType 明體字型 

**檢查系統中已安裝的中文字型**

 .. code-block:: text 

	fc-list :lang=zh


**執行畫面**

 .. code-block:: text

	allen@uServer:~$ fc-list :lang=zh
	/usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing TW MBE:style=Light
	/usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai CN:style=Book
	/usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai HK:style=Book
	/usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai TW:style=Book
	/usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai TW MBE:style=Book
	/usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing TW:style=Light
	/usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing CN:style=Light
	/usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing HK:style=Light

**安裝匯出pdf所需要的套件**

 .. code-block:: text

	sudo apt-get install texlive-xetex texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended

**設定conf.py** ：為了要在pdf中顯示中文，在檔案中找到latex_elements，加入下面的文字，設定中文字型。

 .. code-block:: text

	'preamble': r'''
	\usepackage{fontspec}     % 引入 fontsepc，這樣才可以用下面的設定字型的指令
	\setmainfont{AR PL UMing TW}  % 預設字型
	\setsansfont{AR PL UMing TW}  % sans family 字型
	\setromanfont{AR PL UMing TW} % roman 字型
	\setmonofont{AR PL UMing TW}  % 等寬字型

	\XeTeXlinebreaklocale "zh"          % 設定斷行演算法為中文
	\XeTeXlinebreakskip = 0pt plus 1pt  % 設定中文字距與英文字距
	''', 


**如果是在pytoh2的版本，在conf.py檔案最前面加入下面的文字以正常顯示中文**

 .. code-block:: text

	import sys, os
	# Avoid unicode problem for python2
	if sys.version_info.major == 2:
	    reload(sys)
	    sys.setdefaultencoding('utf8')

**如果沒有設定，會出現下面的錯誤訊息**

 .. code-block:: text

	Encoding error:
	'ascii' codec can't decode byte 0xe5 in position 385: ordinal not in range(128)
	The full traceback has been saved in /tmp/sphinx-err-eDbiuU.log, if you want to report the issue to the developers.


匯出ePub
========
在Ubuntu下，不論是Python2或是Python3都是用「 **make epub** 」指令建立ePub格式的電子書

**匯出HTML指令**
 .. code-block:: text

	make epub

**執行畫面**
 .. code-block:: text

	allen@uServer:~/git/allen$ make epub
	sphinx-build -b epub -d _build/doctrees   . _build/epub
	Making output directory...
	Running Sphinx v1.2.2
	loading pickled environment... done
	building [epub]: targets for 6 source files that are out of date
	updating environment: 0 added, 0 changed, 0 removed
	looking for now-outdated files... none found
	preparing documents... done
	writing output... [100%] index
	writing additional files... genindex search
	copying static files... done
	copying extra files... done
	writing mimetype file...
	writing META-INF/container.xml file...
	writing content.opf file...
	WARNING: unknown mimetype for _static/test, ignoring
	writing toc.ncx file...
	writing sphinx.epub file...
	build succeeded, 1 warning.

	Build finished. The epub file is in _build/epub.


參考網站連結
============
* http://docutils.sourceforge.net/rst.html
* http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html