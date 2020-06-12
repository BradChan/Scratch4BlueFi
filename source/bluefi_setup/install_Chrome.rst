安装Chrome浏览器
====================

几乎所有的嵌入式系统或单板机都没有桌面计算机的键盘、鼠标和大屏幕显示器等标准外设，对这些系统编程或开发时都必须借助于桌面计算机。
通常，我们把用于开发嵌入式系统或单板机的桌面计算机称作“宿主计算机”，待开发和编程的嵌入式系统或单板机称作“目标计算机”，两者通
过USB等标准的通讯接口连接。并且，宿主计算机系统必须预先安装必要的编程软件、编译软件和程序下载工具软件。同时，目标计算机系统
也应该具备一个小型的软件系统能够与宿主计算机系统连接，下载用户程序。

.. image:: /../_static/images/bluefi_setup/cross_dev.jpg
  :scale: 100%
  :align: center

(备注： 上图中以ARM Cortex-M系列处理器的单板机开发为例)

由于孩宝的努力，想对BlueFi进行编程及程序下载只需要安装Chrome浏览器，利用孩宝的易造云平台，完成对bluefi的程序编辑，再将bluefi
通过USB线与你的计算机进行连接，完成程序下载，即可让bluefi执行你想要的结果。

.. image:: /../_static/images/bluefi_setup/jiemian.png
  :scale: 100%
  :align: center
(上图即为孩宝易造云平台中bluefi的图形化编程工具)

1. 下载安装Chrome浏览器安装包
------------------------

在浏览器中打开Chrome的官网(https://www.google.cn/chrome/)，点击"下载Chrome"进入下载页面，选择你想要存放Chrome安装包的路径
下载安装包。下载完成后，鼠标双击浏览器安装包，完成安装。

.. image:: /../_static/images/bluefi_setup/download.png
  :scale: 100%
  :align: center

2. 打开bluefi在线编程工具
------------------------

浏览器安装完成之后，就可以进入bluefi的在线图形化编程工具了，打开孩宝易造云的网址(https://www.ezaoyun.com/)，将网页向下滑动，
找到工具中的cppBlockly(Scratch)，点击进入软件之后，点击左下角"硬件"，将硬件中的bluefi进行添加，现在你就可以对bluefi进行编程
了。

.. image:: /../_static/images/bluefi_setup/dakai.gif
  :scale: 100%
  :align: center
