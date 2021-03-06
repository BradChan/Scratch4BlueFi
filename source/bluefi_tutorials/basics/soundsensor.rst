给计算机装上“耳朵”
======================

标准的桌面计算机内置声音的输入和输出设备，此类音频接口俗称声卡，将耳机或音箱音频线插入声卡后我们能听到声音，将麦克风音频线插入声卡后
可以使用计算机录音。BlueFi也带有与声卡相似的功能，上一届我们了解了BlueFi音频输出的用法，包括输出基本音调和播放音频文件。这一节我们
来了解BlueFi的“耳朵”。

计算机一旦能听到世界的声音就能实现很多很酷的功能，譬如我们在RGB像素灯珠的那一节中已经使用BlueFi的麦克风输入信号去绘制柱状图，
BlueFi的彩灯将随着我们播放音乐或敲击桌子的节奏一起跳动，还记得那个很酷的作品吗？

------------------------

让声音可见(声音的数值)
------------------------

耳朵能听到声音，我们这一节的第一个示例打算让声音可见，就是能看见声音！也就是使用计算机记录并输出音量的数值，先看看代码：

.. image:: /../../_static/images/basics/soundsensor.png
  :scale: 50%
  :align: center

仅用4个代码积木块就可以让声音可见！在BlueFi上执行本示例程序，我们就可以在Bluefi的LCD屏幕上实时的看到音量的数值变化。


随着节奏跳动的光效
------------------------

或许你已经发现，只要我们使用“打印值”将变量或字符串显示到LCD屏幕(控制台)时，程序的执行速度明显下降，这是因为“打印值”
代码块功能使用串口将变量或字符串发送控制台和LCD屏幕上会消耗大量的时间，这些时间消耗甚至影响声音记录的速度。

我们的RGB像素灯珠的响应速度很快，而且仅有5颗灯珠，把声音信号的变化强弱用这些灯珠指示出来，显示数据的延迟几乎让人无感。

.. image:: /../../_static/images/basics/pixels3.png
  :scale: 50%
  :align: center

这就是我们在前面的示例中用彩灯画柱状图的方式将音量的数值反应出来的程序。这是实时的将音量用彩灯反应出来，你能不能修改
程序让彩灯的柱状图反应出声音的稳定性？


闻声自动开启的路灯
------------------------

晚上你走过一个漆黑的楼道时，会不会下意识地拍拍巴掌或跺跺脚希望能唤醒楼道的照明灯？生活中很多楼道灯都是这样设计的，有人路过时被声音
唤亮，延迟一会儿之后自动关闭，这样的工作模式可以节约耗电。

我们下面使用BlueFi的麦克风和5颗RGB像素灯珠来实现这一功能的楼道节能灯。

.. image:: /../../_static/images/basics/soundsensor1.png
  :scale: 50%
  :align: center

看起来这个程序代码块已经很多了！下面我们逐行分析代码的执行效果。

示例代码分析：

    - 右侧代码块第1行，开始定义一个函数，名为delayoff，无输入参数无返回值，该函数用来处理灯珠开启后自动延时关闭的工作
    - 右侧代码块第2行(函数delayoff程序块的第1行),等待0.01秒，即系统空操作10ms
    - 右侧代码块第3行(函数delayoff程序块的第2行)，判断变量delayCnt的值是否小于1
    - 右侧代码块第4行(函数delayoff程序块的第3行)，如果变量delayCnt的值小于1，清除所有像素，即关闭全部灯珠
    - 右侧代码块第5行(函数delayoff程序块的第4行)，否则，即如果变量delayCnt的值大于1
    - 右侧代码块第6行(函数delayoff程序块的第5行)，如果变量delayCnt的值大于1，将该变量自减1

    - 左侧代码块第1行，初始化程序，相当与程序下载进Bluefi之后告知Bluefi从此开始执行程序
    - 左侧代码块第2行，定义一个变量名叫delayCnt，用于处理节能开启后自动延迟关闭的延迟时长，初始赋0
    - 左侧代码块第3行，开始一个无穷循环的程序块
    - 左侧代码块第4行(无穷循环程序块的第1行)，调用自定义函数delayoff，处理延时自动关闭灯珠的事务
    - 左侧代码块第5行(无穷循环程序块的第2行)，判断声音大小是否很大(阈值设置为200)，如果条件为真，执行下面的程序块
    - 左侧代码块第6行(无穷循环程序块的第3行，逻辑判断条件为真时执行的程序块第1行)，设置所有像素颜色为白色，让所有灯珠发出白色照明光
    - 左侧代码块第7行(无穷循环程序块的第4行，逻辑判断条件为真时执行的程序块第2行)，设置变量delayCnt为1000


这个示例程序中，我们声明并定义一个名叫“delayoff”的函数来处理自动延迟关闭灯珠，在主程序的循环中调用该函数，主循环中只是根据声音传感器获取到的声音
大小的数值判断是否感知到很大的声音，如果感知到很大声音(代表有人需要开灯照明)则让灯珠亮起，并设置变量delayCnt的初始值为1000，在delayoff函数中，
我们会不停滴减少这个变量，当该变量变为0时关闭全部灯珠。

函数，几乎所有的程序都会用到函数的概念。用这个概念来设计程序有很多优点：1) 模块化程序设计风格，让程序的结构更合理，便于阅读和维护；2) 代码复用，
有些基础功能的程序被写出函数形式，可以在很多歌地方通过调用该函数实现需要的基础功能；3) 参数化，有些功能算法需要在程序的很多地方使用，但算法的输入
参数不完全相同，将功能算法封装成有输入参数的函数，我们可以大大提高编码效率。

在Bluefi图形化编程软件中中声明和定义函数非常容易。只需要点击自制积木代码块抽屉，制作新的积木。此外，绝大多数编程语言都要求先声明和定义函数，再调用
函数，Bluefi图形化编程软件也不例外。


.. admonition:: 
  总结：

    - 声音传感器
    - 音量的数值(记录并打印出数值)
    - 函数及其定义和调用
    - 本节中，你总计完成了21行代码的编写工作

------------------------------------


.. Important::
  **出现的代码块**

    - 声音大小 (有效值：0.0~65535.0), BlueFi的麦克风感知到声音信号变化的强弱
    - 自制积木，声明定义一个函数并调用它

