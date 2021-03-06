手势识别
======================

如果你遇到一种机器能识别自己的手势，用手势给机器发指令，机器按照手势指令工作，这想想都是一件很酷的事儿！

BlueFi的集成光学传感器具有手势识别功能，能够识别四个方向的挥手手势：向上、向下、向左、向右。

----------------------------


用手势向计算机发指令
----------------------------

这个示例中，我们用四种手势告知BlueFi播放不同的音调，让自己临空弹奏音乐。示例代码如下：



这个示例程序的关键语句是“while True:”循环程序块内的嵌套逻辑，根据识别的手势结果播放对应的midi音节。具体程序代码的功能不再详细赘述。


-----------------------------

.. admonition:: 
  总结：

    - 手势指令
    - 手势识别和光学传感器
    - 多行文本显示的数据结构
    - 文本字体的缩放
    - 逻辑嵌套
    - 本节中，你总计完成了24行代码的编写工作

------------------------------------

.. Important::
  **Sensors类的手势传感器接口**

    - gesture (属性, 只读, 有效值：0, 1, 2, 3, 4), BlueFi的Sensors类gesture属性, 集成光学传感器的手势识别结果

      - 0: 未是被到任何手势
      - 1: 向上挥手(从B按钮向光学传感器方向)
      - 2: 向下挥手
      - 3: 向左挥手(从光学传感器向LCD屏幕方向)
      - 4: 向右挥手