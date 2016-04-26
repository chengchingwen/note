=======================
=Range Query=
=======================


概念
==============
利用特殊的資料結構達成快速的區間操作
(1 base,完全二元樹)

* segment tree

* Binary index tree (fenwick tree)


範例(segment tree)
===================
區間最大值  zerojudge_d539_

.. _zerojudge_d539:  http//zerojudge.tw/ShowProblem?problemid=d539

::

 [3 2 4 5 6 8 1 2 9 7]
  =>[0,                   9,        
  			     /		  \
               6,                     9,
	          /       \		  /        \
		   4,         6,          8,          9,
		   / \	        /   \	        /   \       /   \
      3,   4,    5,    6,    8,    2,    9,    7,
     /\	      /\ / \   / \   / \     / \   / \    / \
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

單點更新(update)
=====================

.. code-block:: cpp

  void update(int l, int r, int k, int x, int v){                   
    if(l==r){   //當l==x==r , 修改節點的值
      st[k]=v;                                               
      return;                                                
    }                                                        
    int m = (l+r)>>1;                                        
    if (l<r){                                                
      if(x<=m)update(l,m,k<<1, x, v);      //如果x在左子樹，更新左子樹                     
      else update(m+1, r, k<<1|1, x, v);   //如果x在右子樹，更新右子樹                     
      st[k]=max(st[k<<1], st[k<<1|1]);     //更新自己的值                        
    }                                                        
  } 



範例(Binary index tree)
=============================
區間合 uva12086_

.. _uva12086:  https://uva.onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&page=show_problem&problem=3238


:: 

    [1 2 3 4 5 6 7 8 9 10]
  =>[1 1   1       1     
       2   2       2  	  
         3 3       3  	   
	    4       4  	    
	         5 5   5     
		        6   6	 
			     7 7	 
			          8  	  
				  	       9  9
					       	          10
  =>[1 3 3 10 5 11 7 36 9 19]
類似精簡版的線段樹，只記錄左子樹

* 利用index 的二進位表示儲存不同區段的合

.. math:: 

  Bit_{i} = \sum_{i=i-lowbit(i)+1}^{n}{A_{i}}
 
 
預備函數
===========================

取最小的非0bit出來

.. code-block:: cpp

  int lowbit(int x){
    return x & (-x);
  }

更新(update)
============================

.. code-block:: cpp

   int update(int x, int v){
     for(;x<=n;x+=lowbit(x))bit[x]+=v;  //更新所有蓋到自己的點，加上v
   }


求前綴合(Sum)
==============================

.. code-block:: cpp

  int sum(int x){
    int k=0;
    for(;x;x-=lowbit(x))k+=bit[x]; //將蓋到x的範圍的點總合，得到前綴合
    return k;
  }
