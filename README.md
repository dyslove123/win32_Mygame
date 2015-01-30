# win32_Mygame
win32项目提交

参照cocos2d-x的设计结构，想模仿他做一个简单的win32 设计类游戏

目前提供射击 移动 敌方单位添加 等功能

因为后期急于添加新功能 所以后期代码比较混乱 

##功能描述
这是一个基于win32的射击类游戏。
主要功能：休闲娱乐。
玩家可以与电脑产生的敌人互相射击。玩家坚持的时间越久，玩家得分越高。
玩家拥有3次清屏技能，3滴血，高速的攻击速度，高速的移动速度
敌人拥有源源不断的数量，5滴血，7种不同的子弹发射方式。


##示例
###游戏开始界面：
游戏开始界面主要介绍游戏的控制方法,教会玩家基本的生存技能.
同时玩家可以在这进行部分基本的操作.保证游戏开始时玩家不会手忙脚乱.

![开始界面](https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E5%88%9D%E5%A7%8B%E7%95%8C%E9%9D%A2.jpg)

###游戏界面：
当玩家操控“原点”穿过起跑线时，就会正式开始游戏：
游戏开始前
的3秒倒计时  游戏中疯狂开火的敌人（吓得我忘记反击)

<img alt="游戏前" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E5%BC%80%E5%A7%8B%E5%89%8D.jpg" width="30%" height="30%">
<img alt="游戏界面1" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E4%B8%AD%20(1).jpg" width="30%" height="30%">
<img alt="游戏界面2" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E4%B8%AD%20(2).jpg" width="30%" height="30%">
<img alt="游戏界面3" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E4%B8%AD%20(3).jpg" width="30%" height="30%">
<img alt="游戏界面4" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E4%B8%AD%20(4).jpg" width="30%" height="30%">

上方显示三个基础信息 包括清屏技能数量  游戏难度  以及得分   
左下角是玩家的血量

###游戏结束场景：
显示玩家分数以及最高分，同时提供三个按钮调整到其他的游戏界面

<img alt="游戏后" src="https://github.com/dyslove123/win32_Mygame/blob/master/%E6%B8%B8%E6%88%8F%E7%A8%8B%E5%BA%8F%E6%88%AA%E5%9B%BE/%E6%B8%B8%E6%88%8F%E7%BB%93%E6%9D%9F.jpg" width="30%" height="30%">


##对程序设计的原则、理念及开发过程的简单介绍
该程序模仿cocos2d-x游戏引擎的设计框架，应用游戏引擎中使用的几个基础概念：director scene sprite  
依据自己对win32程序开发的了解及cocos2d-x架构的了解，开发出来的一个简单的设计类游戏。

###设计原则及理念：
尽可能提高程序的可复用度，让程序可以经过简单的修改及复写，便可以得到不同的结果。
开发过程
在接到通知后，抱着试一试的心态，开始写的这个程序。初期的架构花了大概4天的时间，包括实现director scene shape selftime
但之后的游戏逻辑只花了不到两天的时间，实现了enemy bigenemy 
同时程序中的很多逻辑都可以通过简单的修改。设定出一个游戏自己的有流程。
在之后就是不时的改进，包括:

1. 添加背景图案
2. 添加背景音乐
3. 添加设计音效
4. 添加游戏结束音效
5. 增加了玩家反击的能力
6. 添加能够跟踪玩家位置进行攻击的敌人

程序中存在几个比较遗憾的地方：

1. 因为时间问题，之后添加的功能没有按照一定的标准进行封装，这导致后代码朝着混乱，复杂的状态变化
2. 经过长时间测试，发现了一个错误，这个错误导致运行程序到150s时，游戏会崩溃，提示错误是“第一机会异常”，错误原因不明。所以该错误也没有受到修正

##其他事项
###以下是程序所涉及的技术及介绍：

1. 在窗体过程（Window Procedure）中处理各类消息：
  * 将各类按键信息，鼠标信息发送给Mydirector类 进行进一步的处理
2. 在处理WM_PAINT 消息的过程中，实现窗体内容的重绘（repaint）:
  *因为使用的是封装好的director，所以重绘消息下只是调用了director的绘制函数。
3. 使用图形设备接口（GDI），实现多种图形的绘制；
  *为了方便碰撞检测，所有的精灵单位都采用空心圆作为图案
4. 利用各类鼠标与键盘消息，支持合理的用户操作
  *允许玩家通过键盘控制自己的单位进行移动与攻击
  *在GameLost界面中添加了三个按钮，对鼠标操作进行响应。
5. 借助Windows 定时器（Windows timer），实现特别的用户界面效果
  *使用定时器进行窗体刷新绘制 也就是通过定时器 设定游戏的刷新频率

###补充：
6. 用双缓存技术解决了屏幕闪烁的问题
7. 使用mciSendComment函数进行音频的播放，提供了一个背景音乐以及三个其他的音效，可以同时播放多个音效
8. 使用到了类的继承、多态、封装 使程序可读性，复用性，可扩展性提高



以上写的冠冕堂皇的其实是为了应付作业文档。。