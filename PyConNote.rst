GIL: global interpretor lock

celery on docker swarm

producer 寄件者
broker 郵局
-exchange 分發
-queue 信箱：routing key
consumer
-celery worker 收件人

configuration：
borker_url
celery_inports

app = Celery().config_from_object("config")

@app.task
def kick(id)


docker：host & container

Host
docker daemon
cont 1
cont 2
...


docker swarm：管理docker cluster

celery canvas





Applying Deep Learning in Information Retrieval System

query -> encoding
    neural network

logistic regresssion 
28*28->784 pixels 
x1*w1+...... sum = y1
x1*w1+...... sum = y2
.
.
.	
n neurons

::

  MLP
  x1 -> a1 -> ... -> y1
  x2 -> a2 -> ... -> y2
  x3 -> a3 -> ... -> y3
      hidden layers


convolutional neural networks

pic->convolution->max pooling ->convolution->max pooling ->...->flatten->MLP
    (translation invariance)(subsampling)


representation


recurrent neural net

sentence->encode->[z1,z2,...]->decode->sentence


time
open 
close
high
low
volume

移動平均線
MA = (p_1+..p_n)/n

隨機指標
KD









supersive learning---已知答案














@ianMLewis

deep learning 101
part of ML
special deep neural netowrk

input->hidden->output(label)

classfication problem
NN -- find a way to solve a problem

hidden --add different aspect

each neuron give a classify line

tensor -- n deminsional matrix

usign flow graoh: data flow computation framemwork

sigmoid function
if i < 0;
o -> 0
else o -> 1
rectified linear
if i < 0;
o -> 0
else o -> i



心得


這次非常幸運的從jserv手中拿到一張Pycon的邀請票，這是我第一次參加像Pycon這種conference的活動，大概也是我第一次參加社群的活動，
Python是我第一個接觸到的程式語言，而非常巧合的，今年Pycon正好是我開始學Python過了一年的日子，也就是我開始踏入這個領域這個世界
滿一週年的日子，正因為Python是我第一個接觸的語言，我對Python一直有種特殊的情感在，只是身為一個學生，又是在學期末很多事的時間點，
原本我並沒有打算要參加Pycon，但在身邊學長姐們的感染下，我突然覺得「就算必須要翹掉期中考我也想去參加一回」，正當我決定要參加時，
票卻早賣光了，有趣的是，這時候突然看到jserv手上有些邀請票要給學生，於是在這樣一坡三折之後，我拿到了一張票，對我來說這樣的經驗
是非常難得的，一大早搭著客運去台北、晚上住大通鋪的民宿，在各個會議室來回跑動、聽著各個講者分享他們做了什麼有趣的事情，有的教你
做分散式的運算、有的在講解非同步程式，不管是用機器學習分析了各種資料、還是用類神經網路結合藝術風格，每一場議程都是一種新的感受
新的世界，非常的有趣，以前曾經聽一位學長說：「參加這種conf只是找個理由讓大家畢業後有時間再聚一聚，議程不太是重點」，一開始我不太
懂這是什麼意思，後來我才了解，其實最重要的是人，是講者與參與者，因為參加了Pycon，我碰到了很多有趣的人，很多的學長姐，
聽他們分享、討論各種的想法或是技術，這或許才是整個conf中最有價值的一部份，不管怎麼說，在Pycon的這幾天真的非常開心，看著每個在過程
中發光發熱的人，不知不覺中在心裡埋下種子，希望明年的時候我也有能力站在台上、有一天我也能在開源世界中作出貢獻、我也可以憑著那一股熱誠去自幹、
去成就什麼。非常的感謝jserv給了我這張票讓我有種種難得的經驗以及在Pycon的做的那場keynote，還有因為那場keynote而有感而發的人，
以及陪我度過這三天的人們。現在想想，翹掉期末考也算值得吧。






