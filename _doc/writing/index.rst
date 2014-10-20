****************
共同寫作操作流程
****************

相關軟體安裝
============

#. `TortoiseGit <https://code.google.com/p/tortoisegit/>`_ `(安裝教學) <../software/TortoiseGit.html>`_
#. `Git <http://www.git-scm.com/download/win>`_ `(安裝教學) <../software/Git.html>`_

建立使用者帳號(SSH-KEY)
=======================

在安裝好TortoiseGit與Git後，使用此軟體建立ssh公鑰(Public Key)與私鑰(Private Key)，安裝的兩個軟體都可以建立ssh-key，使用安裝TortoiseGit附帶一起安裝的 `Puttygen <http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html>`_ 建立，此方式是有圖形介面(GUI)，較容易看到所產生的內容，操作方式請參照 :ref:`ssh-key-puttygen`，如果要使用Git Bash建立ssh-key請參照 :ref:`ssh-key-gitbash`，此方式是屬於文字介面，操作方式如Windows的『命令題示字元模式』與Linux的『console模式』，但操作的指令比較像Linux的console模式。

.. _ssh-key-puttygen:

Puttygen建立ssh-key
-------------------

* 啟動Puttygen，打開『開始程式集』，找到 **TortoiseGit** 點選打開後就會看到如下圖的內容，點選執行『Puttygen』

 .. image:: pic/puttygen-001.png

* 啟動Puttygen後的畫面如下

 .. image:: pic/puttygen-002.png

* 點選畫面中的『Generate』，或者是上方選單的『Key->Generate key pair』，點選後會看到畫面上多了一串字『Please generate some randmness by moving the mouse over the blank area.』，簡單來說就是『請在key的空白區塊移動滑鼠以產生ssh-key』及一個Process Bar以顯示ssh-key產生的進度。

 .. image:: pic/puttygen-003.png

* 不斷的在key的空白區塊移動滑鼠時，Process Bar的目前進度就會一直增加

 .. image:: pic/puttygen-004.png

* 當Process Bar跑完全都變綠色時，代表已完成產生ssh-key，這時key的空白區塊就會改變成顯示所產生的ssh-key

 .. image:: pic/puttygen-005.png

* 這時可用下方的『Save private key』按鈕來儲存私鑰，點選按鈕後會跳出存儲視窗，先選擇要存放的資料夾，接著在檔案名稱的地方輸入檔名，副檔名為『ppk』，最後點選存檔即可。

  公鑰正常來說也是點選『Save public key』然後一樣的方式就可以完成，但發現直接存檔，把此公鑰放在伺服器上面時會無法正常使用，最後發現因為在每64個字母後面就加一個空白，因為此空白造成上傳到伺服器時無法正常的運作，只要用文字編輯器打開，將每64個字母後方的空白刪除後存檔即可，另外一個方式就是將『Public key for pasting into OpenSSH authorized_keys file:』下方區塊的內容全選複製，然後打開文字編輯器，貼上所選取的public key，再儲存檔案就可以了，公鑰的副檔名為『pub』。

  建議：公鑰部分，直接複製貼上畫面中的Public key，避免在刪除空白時不小時刪錯，造成無法使用。

 **點選『Save public key』所儲存的內容如下**

 .. code-block:: text 

	---- BEGIN SSH2 PUBLIC KEY ----
	Comment: "rsa-key-20140925"
	AAAAB3NzaC1yc2EAAAABJQAAAQEAieoX4nQSi9b0wm5phNZA7wimvtBLiK37IUcG
	YzGX0FukwmPDF6hZlqIvxwPHn5QvluI4EIFdTH1ybWAhlK8awmQuoSKkaFwRxM8q
	x2DXyHdHGTwbFjNSnh/mRD9dNrROkXfqqkb7SyT5wGfi5dDRpquo9y8Mv8kkXkUo
	x0olI7bT377FBT1Yl9VAFIF9PpNeBYpwI+lKR5aB6q7ABx5ynWo6YFDVPN03czBl
	lslrSo7/Y3r1vB8r0zxSyTMj8OXo4ZirzefwOc1ge8fpfs0XiGgOT6FrTerXzxWE
	zF7Scl15SdLsz122G4znCpf3AIQ795Zcwg5/Qpm9KFJ/6gUl/Q==
	---- END SSH2 PUBLIC KEY ----

 **將儲存的內容刪除每64個字母後方的空白**	

 .. code-block:: text

	---- BEGIN SSH2 PUBLIC KEY ----
	Comment: "rsa-key-20140925"
	AAAAB3NzaC1yc2EAAAABJQAAAQEAieoX4nQSi9b0wm5phNZA7wimvtBLiK37IUcGYzGX0FukwmPDF6hZlqIvxwPHn5QvluI4EIFdTH1ybWAhlK8awmQuoSKkaFwRxM8qx2DXyHdHGTwbFjNSnh/mRD9dNrROkXfqqkb7SyT5wGfi5dDRpquo9y8Mv8kkXkUox0olI7bT377FBT1Yl9VAFIF9PpNeBYpwI+lKR5aB6q7ABx5ynWo6YFDVPN03czBllslrSo7/Y3r1vB8r0zxSyTMj8OXo4ZirzefwOc1ge8fpfs0XiGgOT6FrTerXzxWEzF7Scl15SdLsz122G4znCpf3AIQ795Zcwg5/Qpm9KFJ/6gUl/Q==
	---- END SSH2 PUBLIC KEY ----

* 當執行完畢後，將會在所存放的資料夾內容看到公鑰(user2.pub)與私鑰(user2.ppk)

 .. image:: pic/puttygen-006.png

.. _ssh-key-gitbash:

Git Bash建立ssh-key 
-------------------

* 啟動Git Bash，打開『開始程式集』，找到 Git 點選打開後就會看到如下圖的內容，點選執行『Git Bash』

 .. image:: pic/gitBash-001.png

* 建立ssh-key的指令

 .. code-block:: text
 
     ssh-keygen -t rsa -C "user2@host"

 進入畫面後，可以先用pwd確認目前的資料夾路徑，然後進入到想要存放ssh公鑰(Public Key)與私鑰(Private Key)的資料夾，然後執行『ssh-keygen -t rsa』即可，『-C "user2@host"』這是加入註解說明文字，有加這個參數，會將雙引號中的文字加在所產生ssh-key的最後方，在建立過程會出現『Enter passphrase』這部分如果是空白沒有輸入密碼，在使用git操作時將不會要求輸入密碼，反之，在這些輸入密碼後，在操作git也會出現要輸入密碼訊息，輸入正確的密碼後才會執行git指令。

 .. image:: pic/gitBash-002.png

* 執行完後，可以輸入『ls -al』列出目前資料夾產生了什麼檔案，基本上會出現公鑰(id_rsa.pub)與私鑰(id_rsa)這兩個檔案，接著將公鑰(id_rsa.pub)複製成另一個檔案，例如目前的使用者名稱為user2，所以執行『cp id_rsa.pub user2.pub』，再次執行『ls -al』檢查資料夾中是否有新增一個『user2.pub』檔案。

 .. image:: pic/gitBash-003.png

* ssh-keygen指令說明，可以執行『ssh-keygen -h』將會列出如下圖的內容

 .. image:: pic/ssh-keygen-help.png

轉換Git Bash產生的私鑰格式
^^^^^^^^^^^^^^^^^^^^^^^^^^

* 當使用 :ref:`ssh-key-gitbash` 的方式建立ssh公鑰(Public Key)與私鑰(Private Key)後，在之後使用Pgageant做連線時會出現下面的視窗, 顯示所選擇的key不能載入，因為格式為OpenSSH而所使用的工具是Putty系列的工具，所以需要做一下式格的轉換
 
 .. image:: pic/openssh-putty-001.png

* 注意一下在Git Bash產生ssh-key後，的內容，會有兩個檔案，在私鑰的部分是沒有副檔名ppk的，
 
 .. image:: pic/openssh-putty-002.png

 **Git Bash產生的私鑰格式**

 .. code-block:: text

	-----BEGIN RSA PRIVATE KEY-----
	MIIEowIBAAKCAQEA21wVMmtJSprBBhBifFDyIvTMdFd3oGQw4XegQunAR0N/MdGd
	aQSJdOJzljkd8lpOXnpkdBjfpnvxQOO9Ad0QbpfLu1/hOb/74S8MlIvc3tHPmefd
	DDDAGokEd8vevJGyXceLv6yIoZxgNP9npDAE1k+DiHAVUtk3IBMxaP6bUy36RZbx
	CakSemFqGtO2L51/9YI4j3LmGbbnHh8K4YLD9dHfbey7CN3KgvPKkptW/49LrbWZ
	QhWl6mXGRWfSIwWEML6B+EsUFqwhVte9TFTtxINJa3cvHwbxmsgmVP51M0MiWpUf
	iK7LM4BdW7dpy5KW+FzGj5UwVxpoku2HRRA14wIDAQABAoIBAQCgW1dvjTh93lV+
	/llQscfgv/36irp7uOJ24IF6iPCz5+bC345n6BYoKScASW7X7SZfMK/goxJT3UVG
	/3T7OMS7ZCJeLsAx/GPAgSl8KiZjiRNvWi2grL6yZzmp7ZI9XXD711UU4KbdJbi6
	5X65axUOKgBorC8aaoo+22kCbSXVDmrprYoJUOkAbc2JpjP64j+/9Lz1WA679l/W
	mtt9xdlDBYVMBbDIYhqpax7xQ1rN1YgpdwLUI6kKlmyAW2ZOUrOqT2a0rysYvKnO
	e9d8qaGrtNqcl9/Qb1BALg3PaME+oIPkODloqI86g/WtjQgjfmYvaS7SVnyjOp9j
	EE2XiK4pAoGBAP/isRKIJzIOaUgImE5yOcALeJK5kvJuDiAxlkRVToujXkZqx+t4
	dvYQRrtaVuw1NF4EWKr6kMCqHXu/cSuPGFhoFMyyD25ujiPuU+bZLwF3hyUtXuU0
	XDYHtuq19XW01RgII2txyPVXSdGuWDKkLqqaBwP+7ymo4mBpnJF0DHafAoGBANt1
	NSK4qFI4PYCKjruyIpUucou4tGsQlgckTj4lpSNNNJdaWAYKUDtspPevZJGDdi92
	BElXhSrEq2gS5dpG/x6qYvHMnyz1hLyG8qlKHBV93pXOB3cgRZlBkTK+Rn4RWuGY
	eDl34GFckp+GhWri8AvzCqgJjFBAOOeopbWa3M49AoGAKkD+yHafMk7a58AzllCa
	ZLIAOQpXz5yIzJwjmikUDU7u1GXxmVqNGljZtTpXvC2U9il1ktZJbOcqczLLt0ur
	031sYdjNX4j2A8zpIeefMXjRYjw5vVOGHo3rkJp3a/Zuccd2QdnKO2kskWleuw4N
	frJskiZYy+JNb2pBJmupWzUCgYBWHAhMZm5NTJn9PODCjyP4qy/w2PmZ5PkpNjqp
	MfY5Ass29BED1bojhv633Q819YJDHyiRapDq9h5XiMq9ugvSiYKnY+W1K2T44G6I
	tHaOjEPxPdU6DeShPNPvOC/KuZ6SVFQgIIRfT4aMp6jkBsWvup6czppKxthNNaRH
	vMsU9QKBgHbJQJugAdxLqJh0udFQDo/5dZlBQlGL0PPcCVrWCU8D04dzPM89JguN
	fmG0aqT4a4hPCclfOrz71LKe6VkvVcqMYqE99PaSxshPptVqOWr36mOeHaC5wogS
	3U8V3u06mNwLPqIaRPnIQ/FAiRDHwheAkPxji/KOlDTWFxYioFo5
	-----END RSA PRIVATE KEY-----

 **經Puttygen轉換後的私鑰內容**

 .. code-block:: text

	PuTTY-User-Key-File-2: ssh-rsa
	Encryption: none
	Comment: imported-openssh-key
	Public-Lines: 6
	AAAAB3NzaC1yc2EAAAADAQABAAABAQDbXBUya0lKmsEGEGJ8UPIi9Mx0V3egZDDh
	d6BC6cBHQ38x0Z1pBIl04nOWOR3yWk5eemR0GN+me/FA470B3RBul8u7X+E5v/vh
	LwyUi9ze0c+Z590MMMAaiQR3y968kbJdx4u/rIihnGA0/2ekMATWT4OIcBVS2Tcg
	EzFo/ptTLfpFlvEJqRJ6YWoa07YvnX/1gjiPcuYZtuceHwrhgsP10d9t7LsI3cqC
	88qSm1b/j0uttZlCFaXqZcZFZ9IjBYQwvoH4SxQWrCFW171MVO3Eg0lrdy8fBvGa
	yCZU/nUzQyJalR+IrsszgF1bt2nLkpb4XMaPlTBXGmiS7YdFEDXj
	Private-Lines: 14
	AAABAQCgW1dvjTh93lV+/llQscfgv/36irp7uOJ24IF6iPCz5+bC345n6BYoKScA
	SW7X7SZfMK/goxJT3UVG/3T7OMS7ZCJeLsAx/GPAgSl8KiZjiRNvWi2grL6yZzmp
	7ZI9XXD711UU4KbdJbi65X65axUOKgBorC8aaoo+22kCbSXVDmrprYoJUOkAbc2J
	pjP64j+/9Lz1WA679l/Wmtt9xdlDBYVMBbDIYhqpax7xQ1rN1YgpdwLUI6kKlmyA
	W2ZOUrOqT2a0rysYvKnOe9d8qaGrtNqcl9/Qb1BALg3PaME+oIPkODloqI86g/Wt
	jQgjfmYvaS7SVnyjOp9jEE2XiK4pAAAAgQD/4rESiCcyDmlICJhOcjnAC3iSuZLy
	bg4gMZZEVU6Lo15GasfreHb2EEa7WlbsNTReBFiq+pDAqh17v3ErjxhYaBTMsg9u
	bo4j7lPm2S8Bd4clLV7lNFw2B7bqtfV1tNUYCCNrccj1V0nRrlgypC6qmgcD/u8p
	qOJgaZyRdAx2nwAAAIEA23U1IrioUjg9gIqOu7IilS5yi7i0axCWByROPiWlI000
	l1pYBgpQO2yk969kkYN2L3YESVeFKsSraBLl2kb/Hqpi8cyfLPWEvIbyqUocFX3e
	lc4HdyBFmUGRMr5GfhFa4Zh4OXfgYVySn4aFauLwC/MKqAmMUEA456iltZrczj0A
	AACAdslAm6AB3EuomHS50VAOj/l1mUFCUYvQ89wJWtYJTwPTh3M8zz0mC41+YbRq
	pPhriE8JyV86vPvUsp7pWS9VyoxioT309pLGyE+m1Wo5avfqY54doLnCiBLdTxXe
	7TqY3As+ohpE+chD8UCJEMfCF4CQ/GOL8o6UNNYXFiKgWjk=
	Private-MAC: 86abfdef11715e764427eff2a62554b9697682aa

* 這時再次開啟Puttygen程式，直接點選『Load』按鈕，將會開起一個檔案讀取視窗

 .. image:: pic/openssh-putty-003.png

* 首先選取存放ssh-key的資料夾，此時可能會發現什麼檔案都沒有，接著變更下方的副檔名篩選欄，將預設的『PuTTY Private Key Files』變更設定為『All Files』，就會出現檔案，選取要載入的私鑰後點選下方的『開啟』按鈕

 .. image:: pic/openssh-putty-004.png

* 開啟私鑰檔案後Pageant將會自動判斷到此檔為OpenSSH的格式，也有教學該如何轉換到Putty的格式

 .. image:: pic/openssh-putty-005.png

* 點選『確認』關閉提示視窗後將會出現載入私鑰後的內容，依提示視窗所給的訊息，執行『Save private key』按鈕來儲存私鑰
  
 .. image:: pic/openssh-putty-006.png

* 點選『Save private key』按鈕後會跳出存儲視窗，先選擇要存放的資料夾，接著在檔案名稱的地方輸入檔名，副檔名為『ppk』，最後點選存檔即可

 .. image:: pic/openssh-putty-007.png

* 最後打開檔案管理員，找到存放ssh-key的資料夾，確認是否有完成存檔

 .. image:: pic/openssh-putty-008.png


上傳公鑰(Public Key)
====================

不論是用 :ref:`ssh-key-puttygen`. 或是 :ref:`ssh-key-gitbash`. 將私鑰留在要操作的電腦上，只要將公鑰，副檔名為pub的檔案寄給管理人員，請管理人員將公錀放到伺服器中設定後供使用者連線使用，檔案名稱格式參照 :ref:`publickey-filename-format`.


.. _publickey-filename-format:

公鑰檔案名稱格式
----------------

使用者英文名字@單位名稱.pub

存取檔案庫(Repo)
================

Pageant自動對應連線
-------------------

* 啟動Pageant，打開『開始程式集』，找到 **TortoiseGit** 點選打開後就會看到如下圖的內容，點選執行『Pageant』

 .. image:: pic/pageant-001.png

* 執行後可以在工作列右下角的找到如下圖的通知區域中是否有Pageant在運作中

 .. image:: pic/pageant-002.png

* 點選該Pageant的圖示，將會出現『Pageant Key List』的視窗

 .. image:: pic/pageant-003.png

* 點選『Add Key』後將會出現『Select Private Key File』的視窗，請找到存放私鑰的資料夾，選取副檔名為ppk的私鑰檔案，點選開啟

 .. image:: pic/pageant-004.png
 
* 這樣就完成載入，如果電腦有需要連接不同的伺服器，可以重複上面的動作，加入N個私錀，Pageant將會自動對應

 .. image:: pic/pageant-005.png

使用TortoiseGit Clone Repo
---------------------------

* 當使用者的ssh-key建立好，伺服器上的設定也完成後，接下來就是將檔案庫(Repo)從伺服器上複製(clone)到操作電腦上，使用TortoiseGit軟體的圖形介面(GUI)去操作控制檔案庫(Repo)，道先用開起檔案管理員，找到要建立檔案庫(Repo)的資料夾，然後在資料夾空白區塊點選滑鼠右鍵，就會有TortoiseGit的功能列選項可以使用，因為第一次存取檔案庫(Repo)，所以要使用clone(中文版為：克隆)複製到本機操作電腦中。

 .. image:: pic/tortoisegit-clone-001.png

* 點選右鍵功能列的『Git Clone...』或『Git 克隆...』後或出現設定視窗，在這邊最主要就是『URL』，目前的URL格式為『ssh://user@server/project.git』或『user@server:project.git』，依URL格式轉換到目前伺服器的URL為『ssh://git@allen.go38.net/user2.git』或『git@allen.go38.net:user2.git』，所以在視窗中的URL輸入正確的內容後，下方的目錄欄位會自動帶入project的名稱，此範例為user2，最後點選『確定』就開始執行複製(clone)
 
 **英文版**
 
 .. image:: pic/tortoisegit-clone-002.png
 
 **中文版**
 
 .. image:: pic/tortoisegit-clone-003.png

* 下圖為開始執行Git指令進度的視窗
 
 .. image:: pic/tortoisegit-clone-004.png

* 在執行Git指令進度視窗的過程中，如果出現下圖的話有可能是Pageant沒有啟動，如果有啟動則要檢查一下私鑰是否有加入

 .. image:: pic/tortoisegit-clone-005.png

* 下圖為Git指令執行成功的畫面

 .. image:: pic/tortoisegit-clone-006.png

* 接下來再回來檔案管理員視窗看一下剛剛所複製(clone)的檔案庫(Repo)『user2』

 .. image:: pic/tortoisegit-clone-007.png

使用TortoiseGit Push Repo
-------------------------
* 當文章內容修改完畢，要將檔案上傳推送(Push)到伺服器的檔案庫(Repo)，只要在本機的檔案庫(Repo)資料夾中點選滑鼠右鍵的功能列中操作即可，在這個地方要注意一下，如果是對檔案庫(Repo)的資料夾上點選滑鼠右鍵操作Git指令這種方式是對整個檔案庫(Repo)操作，如果是在檔案庫(Repo)裡面的資料夾或檔案上點選滑鼠右鍵操作Git指令，這樣只會對該資料夾或檔案做處理，下圖就是在檔案庫(Repo)上執行Git指令的增加(Add)，這個指令會將所有的檔案加入檔案庫(Repo)

 .. image:: pic/tortoisegit-push-001.png

* 當點選增加(Add)後會出現一個視窗，該視窗內所列出的檔案就是與本機檔案庫(Repo)最後一個版本比對後尚未加入的檔案清單，在這邊可以選擇檔案要不要加入到檔案庫(Repo)中，可以自行勾選，如果檔案有很多想要全選或全部取消勾選，可在下面『全部選擇或取消』，最後點選『確定』

 .. image:: pic/tortoisegit-push-002.png

 * 點選確定後，就會把所勾選的檔案加入到檔案庫(Repo)中，如果正常的狀況下，會出現所有的檔案都『已加入』，並且在最下面出現『完成』，這個時後並沒有將檔案上傳更新到伺服器，這些操作都還是在本機的檔案庫(Repo)中操作，接著點選如下圖中的提交(Commit)
 
 .. image:: pic/tortoisegit-push-003.png

* 接著就會看到提交(Commit)的視窗，在視窗最上方的『記錄信息』填寫這次提交的簡略內容，方便之後尋找並回復，在下方可以勾選設定作者日期、設定作者，點選『加入Signed-off-by』會自動把設定作者的內容自動填到『記錄信息』的最下方，在『變動』可以看到這次提交(Commit)的檔案異動狀況，最後點選『確定』後就會把這次提交(Commit)的內容加入到檔案庫(Repo)

 .. image:: pic/tortoisegit-push-004.png

* 點選『確定』後執行Git指令，這時就會出現『Git命令進度』的視窗，當看到『完成』後，本機的檔案庫(Repo)就把這次提交(Commit)的內容增加變更成最新的版本內容，但這時所有的操作還是都在本機的檔案庫(Repo)中操作，尚未上傳到遠端的伺服器中，如果要上傳推送(Push)，請點選畫面中的『推送』

 .. image:: pic/tortoisegit-push-005.png

* 點選『推送』後接著出現『推送』的設定視窗，在這邊先使用預設值，點選『確定』，開始將本機的檔案庫(Repo)上傳到遠端伺服器

 .. image:: pic/tortoisegit-push-006.png

* 接著又會出現上傳推送(Push)指令進度視窗，此時就會開始上傳到遠端伺服器，最後會出現『完成』，這時就完成整個更新的流程
 .. image:: pic/tortoisegit-push-007.png
 .. image:: pic/tortoisegit-push-008.png

* 這時可以到 `gitweb <http://allen.go38.net/cgi-bin/gitweb.cgi>`_ 上看到該檔案庫(Repo)的更新內容
 .. image:: pic/tortoisegit-push-009.png


使用Git Bash Clone Repo
-----------------------

* 當使用者的ssh-key建立好，伺服器上的設定也完成後，接下來就是將檔案庫(Repo)從伺服器上複製(clone)到操作電腦上，使用Git 軟體的文字介面(console)去操作控制檔案庫(Repo)，道先用開起檔案管理員，找到要建立檔案庫(Repo)的資料夾，然後在資料夾空白區塊點選滑鼠右鍵，就會有Git的功能列選項可以開啟Git Bash

 .. image:: pic/gitbash-clone-001.png

* 在檔案管理員的資料夾下，使用滑鼠右鍵開啟Git Bash後也會一起切換到該資料夾目錄下
 
 .. image:: pic/gitbash-clone-002.png

* 接著就輸入git clone指令將要存取的檔案庫(Repo)複製下來，依URL的格式輸入『git clone ssh://git@allen.go38.net/user2.git』或『git clone git@allen.go38.net:user2.git』，正常無誤的話就會看到類似下圖的內容，接著執行『cd user2』切換到檔案庫user2，再使用『ls -al』列出該檔案庫(Repo)下的檔案內容

 .. image:: pic/gitbash-clone-003.png

使用Git Bash Push Repo

* 在圖形介面的操作方式有介紹過如何使用TortoiseGit將寫好的文件上傳推送(Push)到伺服器上，現在使用 Git Bash文字指令的方式將寫好的文件上傳推送(Push)到伺服器上，操作的指令主要有三個，和TortoiseGit的操作是相同的；首先打開要處理的檔案庫(Repo)，然後點選滑鼠右鍵，點選『Git Bash』，這時就會出現如下圖的視窗，操作的路徑會自動帶入
 .. image:: pic/gitBash-push-001.png

* 操作如同TortoiseGit的『增加』，在Git下就是『git add .』後面的『.』就是全部都加入的意思，在在TortoiseGit會有好看的圖形介面可以使用勾選的方式選擇要不要加入，如果在Git Bash下只能用『git add filename』的方式去手動加入

 .. image:: pic/gitBash-push-002.png

* 在這裡可以使用git status去顯示目前在本機檔案庫(Repo)內異動的狀況

 .. image:: pic/gitBash-push-003.png

* 使提交(Commit)指令，『git commit -m "記錄訊息"』，在使用Git提交一定要加入『記錄訊息』

 .. image:: pic/gitBash-push-004.png

* 最後使用上傳推送(Push)指令將所提交(Push)的內容上傳到伺服器中，『git push』

 .. image:: pic/gitBash-push-005.png

* 這時可以到 `gitweb <http://allen.go38.net/cgi-bin/gitweb.cgi>`_ 上看到該檔案庫(Repo)的更新內容

 .. image:: pic/gitBash-push-006.png

GitWeb 線上觀看修改內容
=======================
在伺服器上有安裝 `gitweb <http://allen.go38.net/cgi-bin/gitweb.cgi>`_ 此網站會將有開放的檔案庫(Repo)顯示在上面，下面有一些gitweb執行的畫面 

* 首頁 ，這裡會顯示所有檔案庫(Repo)的清單，後面會有一些連結可以不同的方式顯示記錄(summary | shortlog | log)，檔案內容(tree)

 .. image:: pic/gitweb-001.png

* 點選summary進入的頁面只會顯示比較近期的記錄，一樣後方也有一些連結，可以顯示commit的記錄，還有commitdiff與上一個版本的差異內容，snapshot可以打包下載這個版本的內容

 .. image:: pic/gitweb-002.png

* 點選commit後會進詳細的內容，例如有幾個檔案新增、修改、刪除等，可點選diff去看該檔案的版本差異內容

 .. image:: pic/gitweb-003.png

* 點選diff進入該檔案詳細的修改內容，如下圖，有『-』符號而且是紅色的文字代表被刪除，而有『+』符號並且是綠色文字代表新增內容，黑色文字就是沒有變動的內容

 .. image:: pic/gitweb-004.png

* 在專案名稱下方有一些超連結可點選觀看，下面的圖片為點選『log』，會顯示比較完整的記錄項目

 .. image:: pic/gitweb-005.png

* 點選『tree』會顯示該檔案庫(Repo)下所有的檔案內容，如果為檔案點選後可觀看檔案內容，若為資料夾則會進入該資料夾並顯示其檔案內容

 .. image:: pic/gitweb-006.png