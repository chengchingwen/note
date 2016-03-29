=======================
=Range Query=
=======================


概念
==============
利用特殊的資料結構達成快速的區間操作

* segment tree
1 base,完全二元數

範例
===================
區間最大值  http://zerojudge.tw/ShowProblem?problemid=d539

::

 [3 2 4 5 6 8 1 2 9 7]
  =>[0,                   9,        
		   /		  \
               6,                     9,
	   /       \		  /        \
	 4,         6,          8,          9,
	/ \	  /   \	      /   \       /   \
      3,   4,    5,    6,    8,    2,    9,    7,
     /\	   /\	/ \   / \   / \	  / \   / \    / \
    3, 2, 0, 0, 0, 0, 0, 0, 8, 1, 0, 0, 0, 0, 0, 0,    ]
樹狀結構，上層儲存左右節點的最大值，0為不會被走訪的點

* 以陣列儲存樹圖資訊，index 1為root，左右子樹分別為2*index, 2*index+1



建樹(Build)
==================

.. code-block:: cpp

  void build(int L, int R, int k){
    if(L==R){     //當範圍只有一時，
      st[k]=T[R]; //直接取值
      return;
    }
    int m=(L+R)>>1;
    if(L<R){
      build(L,m,k<<1);     //左端點到中點建左子樹
      build(m+1,R,k<<1|1); //中點+1到右端點建右子樹
      st[k] = max(st[k<<1],st[(k<<1)|1]); //自己的值為左右兩子樹的最大值
    }
  }

查詢(Query)
====================

.. code-block:: cpp

  int query(int L, int R, int a, int b,int k){
    if(a<=L && R<=b){ //如果查詢範圍大於此數的範圍
      return st[k];   //回傳此節點的值
    }
    int m=(L+R)>>1;
    if(L<R){
    if(b<=m)return query(L,m,a,b,k<<1);     //如果查詢範圍被包在左子樹，查詢左子樹
    if(m<a)return query(m+1,R,a,b,k<<1|1);  //如果查詢範圍被包在右子樹，查詢右子樹
    return max(query(L,m,a,m,k<<1), query(m+1,R,m+1,b,k<<1|1)); //橫跨時，分別查詢左右子樹的最大值並取最大值
    }
  }
