FourSetOfMACrossoverSystem
==========================

四均线交易系统
--------------

### 策略说明

该系统由两个双均线系统构成，可以看做是双均线系统的升级版。构建思想是捕捉大周期顺势入场、小周期出场的趋势行情。

多头入场条件为两组均线均成多头排列时且当前价高于上根BAR最高价，并且当前Bar有一定成交量时，多头入场；出场条件为小周期多头均线组合成空头排列出场或两组均线分别空头排列且低于上根BAR最低价出场。

空头入场条件为两组均线均成空头排列且当前价低于上根Bar最低价，并且当前Bar有一定成交量时，空头入场；出场条件为小周期空头均线组合成多头排列出场或两组均线分别多头排列且高于上根BAR最高价出场。

(PS: 多头排列, 短期移动平均线在上，长期移动平均线在下，并同时上移；空头排列,
短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降)

### 优势

1.  具有正向收益预期，可以让人跟踪趋势，均线系统直观清晰；

2.  可以配合K线(蜡烛线)使用，可以跟踪趋势作为判断做多和做空的依据

3.  通过大小周期的双均线系统的配合，进一步强化趋势走向的判断。

### 劣势

1.  价格走势多数情况下不确定，趋势性行情极少出现，因此在“震荡”型行情中胜率偏低；

2.  并且均线以过去行情走势为依据，预测行情不够细粒度，因此在不定的市场中，很可能出现盈利回吐等情况；

3.  当行情经历回撤，尤其是大幅度回撤时，四均线交易系统只有在收盘价走出来，才可能出现明显的转折走势，此时利润可能已经大量回吐或者亏损幅度已经偏大；

4.  缺乏及时能力。

### 场景

适合：趋势型行情

不适合：震荡型行情

### 改进策略

#### 四均线交易系统(多头)动态仓

在四均线交易系统(多头)的基础上，在首次开仓之后，设置固定盈利30跳加仓一次，每次1手，最多加仓3次；加仓后固定亏损30跳后减仓1手。

#### 四均线交易系统(多头)动态跟踪

在四均线交易系统(多头)动态仓的基础上，进行跟踪止损，当盈利达到50跳后启动第一级跟踪止损，此时回撤30跳即进行止损减仓；当盈利达到80跳之后启动第二级跟踪止损，此时回撤20跳即进行止损减仓。并设定初始止损回撤跳数为50.

源代码
------

详见文件" FourSetOfMACrossoverSystem.fbk"
