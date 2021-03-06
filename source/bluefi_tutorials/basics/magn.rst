地磁计和指南针
======================

望文生义，地磁计就是利用传感器测量地球磁场的方法来确定物体水平方向(与地面垂直的方向)上的朝向。我们四大发明之一的指南针正是
利用地球磁场的原理，古代人们就已发现地球是一个很大的磁铁，而且南北极朝向南北极始终保持不变，周围无更强磁场的小磁铁受到地磁
方向的影响也始终朝向一个固定的方向。指南针的小磁极的指向始终保持不变，这样就可以帮助我们确定正确的方向，指南针诞生后对大航海
时代的发展起到积极推进作用，那个时代在海上行船全靠指南针(罗盘)和北斗星的指引，他们都具有始终不变的方向。

今天我们知道地球磁场并不稳定，甚至有科学预言，地球磁极会发生翻转。地磁南北极与地球南北极并不一致，如下图所示，他们方向相反，
而且两对极点连线之间存在夹角。

.. image:: /../../_static/images/basics/magnetic_sn.jpeg
  :scale: 100%
  :align: center


--------------------------------

地磁计的数据
--------------------------------

使用下面的程序示例，观察地磁计数据的变化规律。示例程序如下：

.. image:: /../../_static/images/basics/magn.png
  :scale: 100%
  :align: center

将本示例程序保存到BlueFi的/CIRCUITPY/code.py文件中，当BlueFi执行示例程序时，旋转BlueFi并观察地磁计给出的三个分量数值的变化。

示例代码分析：

    - 第1行，初始化程序，相当与程序下载进Bluefi之后告知Bluefi从此开始执行程序
    - 第2行，一个无穷循环的程序块
    - 第3行(无穷循环程序块的第1行)，打印值"X="，将地磁传感器的分量X打印出来
    - 第4行(无穷循环程序块的第2行)，打印值"Y="，将地磁传感器的分量Y打印出来
    - 第5行(无穷循环程序块的第3行)，打印值"Z="，将地磁传感器的分量Z打印出来
    - 第6行(无穷循环程序块的第4行)，等待0.1秒(即系统空操作0.1秒)

通过本示例的数据信息，你观察到地磁计的数据与BlueFi的姿态和朝向之间存在什么样的关系？


指北针和电子罗盘
--------------------------------

我们修改前一个示例，增加北方的指示，我们以BlueFi金手指的方向为准，当BlueFi的LCD显示器保持与地水平面平行时，
金手指对着正北方时地磁计指北针归零，旋转BlueFi过程中，将给出BlueFi的金手指水平方向与正北方的夹角。示例程序如下：

.. image:: /../../_static/images/basics/magn1.png
  :scale: 100%
  :align: center

在前一个示例的基础上，把罗盘方向角也打印出来。

现在你知道为什么指南针并不指向南方而是指向北方的原因了吗？

-----------------------------

.. admonition:: 
  总结：

    - 地球磁场
    - 地磁南北极和地理南北极
    - 地磁计
    - 指南针
    - 本节中，你总计完成了13行代码的编写工作

------------------------------------

.. Important::
  **出现的代码块**

    - 地磁传感器的分量(每个分量的有效值: -10.24~+10.24),地磁计的三个分量值
      x方向分量、y方向分量、z方向分量

    - 罗盘方向角(有效值: 0~359), 给出当前方向与正北方向的夹角
