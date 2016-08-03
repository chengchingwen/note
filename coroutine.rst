===========================
=Coroutine=
===========================
flow control 的一種，讓 function 可以執行到一半暫停與繼續
function -> subroutine ，function 也可以算是 flow control 的一種，又叫作 subroutine


**Synchronous** *v.s.* **Asynchronous**
==========================================
synchronous -> 當程式呼叫某個 function 時，等待它執行完才繼續執行
asynchronous -> 當程式呼叫某個 function 時，不等待它執行完就繼續執行


**note:** 
    asynchronous 重點在於等待不等待，實際實作上可以在 single thread 裡面也可以是開 multi thread，
    要討論到 async 對程式執行速度的影響就要先討論到電腦 I/O 的處理上面


I/O
==========================================
I/O 主要由系統 OS 負責，不管是要讀寫檔、發送 requests、輸入輸出......都要透過 OS 來執行，
程式是負責告訴 OS 我現在需要什麼樣的 I/O 處理，由 OS 來告訴程式這個 I/O 結束

Blocking-I/O
    一種特殊的 I/O，過程會將程式暫停，直到 I/O 結束


I/O-bound v.s. CPU-bound 
=============================================
I/O-bound
  程式花時間去做 I/O 相關處理，async 可能會加快這類程式

CPU-bound 
  程式花時間在 CPU 相關運算處理，如矩陣運算


Coroutine & Asynchronous
=======================================
event driven 是一種達到 async 的方式，透過一個 event loop 不斷的檢查程式現在執行到哪，
當現在這個 routine 執行到 I/O-bond function 上面處於等待中，就切換到下一個(或某個) routine 上面，
會有 overhead


Reference
========================
http://blog.kgriffs.com/2012/09/18/demystifying-async-io.html