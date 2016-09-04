=========================
＝Emacs 基本語法＝
=========================

指令
=========================
*   Ctr = C
*   ESC = ESC | Meta鍵(alt or ESC) == C-[
*   C-g	      		中斷指令
   

Indentation
=========================
指令

.. code-block::

   TAB			對齊
   ESC-C-\	        對指定區塊一次對齊
   ESC-m		游標移到對齊
   ESC-C-o		產生一行


游標移動
=========================
指令

.. code-block:: 

   C-p			上
   C-n  	 	下
   C-b   		左
   C-f   		右
   ESC-b 		單字的頭
   ESC-f 		單字的尾
   C-a			行頭
   C-e  		行尾
   ESC-a		段落首
   ESC-e		段落尾
   ESC- C-a		函式首
   ESC- C-e		函式尾
   ESC- <		檔案首
   ESC- >		檔案尾	
   C-v  		下一頁
   ESC-v		上一頁
   ESC-g g +(number)	移動到指定行
   C-l	   		將畫面移到游標正中央

重複指令
==========================
指令

.. code-block:: 

   C-u			重複執行四次
   C-u C-u.....		重複執行4X4X...次
   ESC-(n) + (x)	重複執行n次(x)指令


文字處理
==========================
指令

.. code-block:: 

   ESC-l		將文字轉小寫
   ESC-u		將文字轉大寫
   ESC-c		將文字首大寫
   C-x ESC-l		將區域文字轉小寫
   C-x ESC-u		將區域文字轉大寫
   ESC-q		段落重新排列
   ESC-h		標記段落   


刪除
===========================
指令

.. code-block:: 

   C-d			delete
   C-k			刪除游標後(直到換行)
   ESC-k		刪除游標後(直到段落尾)
   C-x k		刪除游標前(直到段落首)
   C-@			標記起始點
   C-w			剪下(由起始點到游標)
   ESC-w		複製(由起始點到游標)
   C-y			貼上
   ESC-y		貼上前一次的
   ESC- DEL		刪除游標以左一個字
   ESC- d		刪除游標以右一個字
   C-x u | C-_		還原
   C-x i   		插入檔案內容


搜尋＆取代＆交換
===========================
指令

.. code-block::  

   搜尋
   ESC-C-d		regular express搜尋
   C-s			後向搜尋(Enter後輸入搜尋字)
   C-r 			前向搜尋(Enter後輸入搜尋字)
   <目標字被反白後>
   C-s			移動到下一個目標字
   C-r			移動到前一個目標字

   取代
   SC-%			輸入後接著輸入被取代字跟取代字
   <目標字被反白後>
   SPACE | y		取代，下一個
   !	     		全部取代
   DEL | n		不取代，下一個
   ESC | q		(不取代)退出
   .	   		(取代)退出
   ^			前一個
   
   交換
   C-t			交換游標兩邊字元
   ESC-t		交換游標兩邊字串
   C-x C-t		交換游標前兩行


儲存＆檢索
==============================      
指令

.. code-block:: 

   C-x C-s		儲存
   C-x C-c		退出
   C-x C-w + </PATH>	另存新檔(接著輸入檔名)
   C-x d     		瀏覽資料夾


多視窗
===========================
指令

.. code-block:: 

   C-x 2		新視窗(橫向)
   C-x 3		新視窗(縱向)
   C-X 0		關閉當前視窗
   C-x {                放大視窗(向左)
   C-x }                放大視窗(向右)
   C-x ^                放大視窗(向上)
   C-x o		切換視窗
   C-x C-f + </PATH>	開啟檔案
   C-x C-v   		開啟其他檔案
   C-x 1   		關閉所有其它視窗
   C-x k		關掉目前編輯區(buffer)
   C-x C-b		列出所有編輯檔案(buffer)
   C-x b		切換到其他編輯區(buffer)
   C-x 4 f		在其它視窗開啟檔案
   C-x 4 b		在其它視窗切換編輯區(buffer)
   C-z 			背景化


emacs內編譯
===========================
指令

.. code-block:: 

   ESC-x compile	編譯(接著輸入編譯指令:g++, gcc, clang,......)
   ESC-x recompile	重新編譯
   ESC-x gdb		使用gdb除錯
   C-x ` 		下一個error


Shell
==========================
指令

.. code-block::  

   ESC-!                shell command
   ESC-x shell		開啟shell
   <shell特殊指令>
   C-c C-c		中斷
   C-c C-z		背景執行
   C-c C-r		移動到上一次命令輸出
   C-c C-y		取得上一次shell命令     
   C-c C-w		刪除前一個字
   C-c C-d		退出


巨集指令
=========================
指令

.. code-block::  

   C-x (		開始記錄按鍵
   C-x )		結束紀錄按鍵
   C-u C-x (		延伸上次記錄按鍵
   C-x e		執行紀錄按鍵指令
   ESC-(n) C-x e	執行n遍紀錄按鍵指令
   
HELP command
======================
指令

.. code-block::

   C-h








參考資料
==============================
http://www.study-area.org/cyril/opentools/opentools/x42.html

http://puremonkey2010.blogspot.tw/2012/03/gnu-emacs.html

http://blogkrogh.blogspot.tw/2010/11/emacs.html

http://www.math.uh.edu/~bgb/emacs_keys.html

http://www.oreilly.com.tw/sample_chap/a025_07.pdf

https://www.ptt.cc/bbs/Editor/M.1364189560.A.5E6.html


=====================================

.. image:: ./38f.gif
