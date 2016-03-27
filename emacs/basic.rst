=====================
＝Emacs 基本語法＝
=====================

指令
====================
*   Ctr = C
*   ESC = ESC


游標移動
====================
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
   ESC- C-a		函式首
   ESC- C-e		函式尾
   ESC- <		檔案首
   ESC- >		檔案尾	
   C-v  		下一頁
   ESC			上一頁
   ESC-g g +(number)	移動到指定行


重複指令
=======================
指令

.. code-block:: 

   C-u			重複執行四次
   C-u C-u.....		重複執行4X4X...次


刪除
========================
指令

.. code-block:: 

   C-d			delete
   C-k			刪除游標後(直到換行)
   C-@			標記起始點
   C-w			剪下(由起始點到游標)
   ESC-w		複製(由起始點到游標)
   C-y			貼上
   ESC-y		貼上前一次的
   ESC- DEL		刪除游標以左一個字
   ESC- d		刪除游標以右一個字
   C-x u		還原


搜尋＆取代
========================
指令

.. code-block::  

   收尋
   C-s			後向收尋(Enter後輸入收尋字)
   C-r 			前向收尋(Enter後輸入收尋字)
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


儲存＆檢索
=====================      
指令

.. code-block:: 

   C-x C-s		儲存
   C-x C-c		退出
   C-x C-w + </PATH>	另存新檔(接著輸入檔名)


多視窗
=====================
指令

.. code-block:: 

   C-x 2		新視窗(橫向)
   C-x 3		新視窗(縱向)
   C-x o		切換視窗
   C-x C-f + </PATH>	開啟檔案
   C-x 1   		關閉所有其它視窗


emacs內編譯
======================
指令

.. code-block:: 

   ESC-x compile	編譯(接著輸入編譯指令:g++, gcc, clang,......)
   C-x ` 		下一個error
   

Shell
====================
指令

.. code-block::  

   ESC-x shell		開啟shell
   <shell特殊指令>
   C-c C-c		中斷
   C-c C-z		背景執行
   C-c C-r		移動到上一次命令輸出
   C-c C-y		取得上一次shell命令     

