*************************
SPHINX-DOC 安裝 (Windows)
*************************

測試環境
========
* 作業系統：Windows 7(64位元)
* Python：3.4.1 
* SPHINX-DOC：1.2.3


下載 Python
===========
* `Python官方網站 <https://www.python.org/>`_ 

 .. image:: pic/Python-Download-001.png

* `Python Download <https://www.python.org/downloads/>`_ ：進入下載頁面後，選擇『Download Python 3.x.x』下載Python3的版本

 .. image:: pic/Python-Download-002.png
   
安裝 Python
===========

* 執行Python安裝程式『python-3.4.1.msi』，使用預設值『Install for all users』

 .. image:: pic/Python-Install-001.png
 
* 選擇安裝目錄，使用預設值『C:\\Python34\\』

 .. image:: pic/Python-Install-002.png

* 客製化安裝，這地方移到最後一個項目『Add python.exe to Path』，這預設是沒有選的，因為是第一次安裝，所以就把這個選項一起安裝，主要是將「C:\\Python34\\;C:\\Python34\\Scripts;」這一串文字自動加入到環境變數的Path中，如果沒有選取安裝，需自行手動加入。

 .. image:: pic/Python-Install-003.png

* 軟體安裝進度

 .. image:: pic/Python-Install-004.png

* 安裝完成

 .. image:: pic/Python-Install-005.png

* 執行命令提示字元「開始->所有程式->附屬應用程式->命令提示字元」，然後直接輸入『python』，就會看到如下的畫面，如果沒有請先確認系統環境變數的path是否有設定python的資料夾路徑「C:\\Python34\\;C:\\Python34\\Scripts;」

 .. image:: pic/Python-Install-006.png

安裝easy_install
================

* 下載 `ez_setup.py <https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py>`_ , 如下圖所下載的「ez_setup.py」存放在「C:\\Users\\Allen\\」下並使用命令提示字元執行『python ez_setup.py』

 .. image:: pic/Python-ezSetup-001.png

* 下圖為安裝完會的畫面

 .. image:: pic/Python-ezSetup-002.png
 
安裝Sphinx
==========

* 安裝好『easy_install』，接著輸入『easy_install sphinx』，安裝的時後需要一點時間
  
 .. image:: pic/Python-Sphinx-001.png
 
* 下圖為安裝完成的畫面

 .. image:: pic/Python-Sphinx-002.png

* 安裝完成後，請輸入『sphinx-build』測試是否可以正常執行，如下圖

 .. image:: pic/Python-Sphinx-003.png

參考網站連結
============
* `Sphinx-Doc Install <http://sphinx-doc.org/install.html>`_ 