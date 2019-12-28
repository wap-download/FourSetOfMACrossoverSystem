FourSetOfMACrossoverSystem
==========================

\@[TOC](四均线交易系统)

\# 名词术语

\#\# 期货

[什么是期货？-- 傅建朝](https://www.zhihu.com/question/19903936/answer/78060981)

\#\# 头寸：承诺买卖合约的最初部位

头寸（position）是一个金融术语，指的是个人或实体持有或拥有的特定商品、证券、货币等的数量。汉语将其翻译为“头寸”，源于旧社会作为货币的“袁大头”每十个摞起来为一寸
。

\#\#\# 多头：买进合约者

头寸是一种市场约定，承诺买卖合约的最初部位，买进合约者是多头，处于盼涨部位。

\#\#\# 空头：卖出合约者

头寸是一种市场约定，承诺买卖合约的最初部位，卖出合约者为空头，处于盼跌部位。

\#\# 均线多头排列：看涨

![均线多头排列](https://img-blog.csdnimg.cn/20191225223308397.png)

特征1：短期移动平均线在上，中期移动平均线在中，长期移动平均线在下。

特征2：多个移动平均线一起上移，这就是典型的均线多头排列。

总结：

多头排列代表多方（买方）力量强大，后市将由多方主导行情，此时是中线进场的机会。这是一个比较常见的上涨信号，此时应该以持股为主，不要轻易卖出。

\#\# 均线空头排列：看跌

![均线空头排列](https://img-blog.csdnimg.cn/2019122522354031.png)

特征1：长期移动平均线在上方，中期移动平均数在中间，短期移动平均值在下。

特征2：多个移动平均线同时呈弧形下降，这种就是典型的均线空头排列。

总结：

当大盘(单个股票)的均价走低时，意味着大盘(单个股票)已经进入了下跌周期，这时大盘(单个股票)的走势趋弱。特别是当大盘(单个股票)之前刚有过相对大幅度的上涨时，均线空头排列，表明大盘(单个股票)很大可能有大幅度的下跌。这个时候应该果断卖出手中的股票，止损离场，持币观望。

\#\# K线图(蜡烛图)

股市及期货市场中的K线图的画法包含四个数据，即开盘价、最高价、最低价、收盘价，所有的k线都是围绕这四个数据展开，反映大势的状况和价格信息。

![K线图](https://img-blog.csdnimg.cn/2019122522550558.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mjg0NzEyNg==,size_16,color_FFFFFF,t_70)

\#\# Bar

Bar代表K线图(蜡烛图)的每根条子。

\#\# 入场

\#\#\# 多头入场

多头主力大量买入股票的行为

\#\#\# 空头入场

空头主力大量卖出股票的行为

\#\# 出场

\#\#\# 多头出场

多头主力清头寸

\#\#\# 空头出场

空头主力清头寸

\# TB公式

\#\# 用户函数

\#\#\# CallAuctionFilter()

// 简称: CallAuctionFilter

// 名称: 集合竞价与小节过滤函数

// 输出: 布尔型

//
说明：此函数可以处理1分钟、3分钟、5分钟、15分钟、30分钟、1小时、日线、周线、月线交易的集合竞价与小节过滤，避免发出废单。

\#\#\# Text()

将变量转换为字符串格式(String)

\#\# 交易函数

\#\#\# Buy, SellShort, BuyToCover, Sell

\#\#\#\# 多头

Buy：对当前合约发出买入开仓的指令，如果图标讯号显示当前持有空仓，则会先平掉空仓，再开多仓；

Sell：对当前合约发出平多仓的指令，当图表讯号显示有多头持仓时，方可执行此指令。

\#\#\#\# 空头

SellShort：对当前合约发出卖出开仓的指令，如果图表讯号显示当前持有多仓，则会先平掉多仓，
再开空仓；

BuyToCover：对当前合约发出平空仓的指令，当图表讯号显示有空头持仓时，方可执行此指令；

\#\#\#\# 语法格式

Bool Buy(Numeric Share=0,Numeric Price=0)

Bool BuyToCover(Numeric Share=0,Numeric Price=0)

Bool Sell(Numeric Share=0,Numeric Price=0)

Bool SellShort(Numeric Share=0,Numeric Price=0)

\#\#\#\# 参数说明

Share：数量，为整型值，默认值为0表示使用系统设置参数；

Price：价格，为浮点数，默认值为0表示使用现价（非最后Bar为Close) 。

\#\#\# MarketPosition

获得当前持仓状态。

\-1：当前位置为持空仓；

0：当前位置为持平；

1：当前位置为持多仓。

\#\# 关键字

\#\#\# Bar数据系统函数

![Bar数据系统函数](https://img-blog.csdnimg.cn/20191226185310726.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mjg0NzEyNg==,size_16,color_FFFFFF,t_70)

![续表](https://img-blog.csdnimg.cn/2019122619122886.png)

\#\#\# Marketposion

是指当前账户的持仓状态

初始持仓状态：marketposition==0

多头持仓状态：marketposition==1

空头持仓状态：marketposition==-1

\#\# 颜色

1. 黑色——用户自己声明的变量名或者参数名

2. 红色——数字

3. 蓝色——系统函数

4. 暗红色——已有的用户函数

5. 紫红色——运算符号

6. 果绿色——字符串(可以为中文字符)

7. 翠绿色——注释语句(注释符号后可为中文字符)

\#\# 数据输出和交易指令

![保留字](https://img-blog.csdnimg.cn/20191226185123503.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mjg0NzEyNg==,size_16,color_FFFFFF,t_70)

\#\# 其他

序列变量可以通过"[nOffset]"来回溯以前的变量值。

全局变量设置值：SetGlobalVar(\<索引值\>,\<值\>);

全局变量读取值：GetGlobalVar(\<索引值\>);

单个公式应用中，全局变量索引仅支持0到499共500个全局变量。

\# 四均线交易系统

\#\# 策略说明

该系统由两个双均线系统构成，可以看做是双均线系统的升级版。构建思想是捕捉大周期顺势入场、小周期出场的趋势行情。

多头入场条件为两组均线均成多头排列时且当前价高于上根BAR最高价，并且当前Bar有一定成交量时，多头入场；出场条件为小周期多头均线组合成空头排列出场或两组均线分别空头排列且低于上根BAR最低价出场。

空头入场条件为两组均线均成空头排列且当前价低于上根Bar最低价，并且当前Bar有一定成交量时，空头入场；出场条件为小周期空头均线组合成多头排列出场或两组均线分别多头排列且高于上根BAR最高价出场。

(PS: 多头排列, 短期移动平均线在上，长期移动平均线在下，并同时上移；空头排列,
短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降)

\#\# 优势

1. 具有正向收益预期，可以让人跟踪趋势，均线系统直观清晰；

2. 可以配合K线(蜡烛线)使用，可以跟踪趋势作为判断做多和做空的依据

3. 通过大小周期的双均线系统的配合，进一步强化趋势走向的判断。

\#\# 劣势

1. 价格走势多数情况下不确定，趋势性行情极少出现，因此在“震荡”型行情中胜率偏低；

2.
并且均线以过去行情走势为依据，预测行情不够细粒度，因此在不定的市场中，很可能出现盈利回吐等情况；

3.
当行情经历回撤，尤其是大幅度回撤时，四均线交易系统只有在收盘价走出来，才可能出现明显的转折走势，此时利润可能已经大量回吐或者亏损幅度已经偏大；

4. 缺乏及时能力。

\#\# 场景

适合：趋势型行情

不适合：震荡型行情

\#\# 改进策略

\#\#\# 四均线交易系统(多头)动态仓(代码及注释详见附录)

在四均线交易系统(多头)的基础上，在首次开仓之后，设置固定盈利30跳加仓一次，每次1手，最多加仓3次；加仓后固定亏损30跳后减仓1手。

\#\#\# 四均线交易系统(多头)动态跟踪(代码及注释详见附录)

在四均线交易系统(多头)动态仓的基础上，进行跟踪止损，当盈利达到50跳后启动第一级跟踪止损，此时回撤30跳即进行止损减仓；当盈利达到80跳之后启动第二级跟踪止损，此时回撤20跳即进行止损减仓。并设定初始止损回撤跳数为50.

\# 源代码

\#\# 四均线交易系统 多

\`\`\`powershell

//------------------------------------------------------------------------

// 简称: A_FourSetofMACrossoverSys_L

// 名称: 四均线交易系统

// 类别: 公式应用

// 类型: 用户应用

// 输出:

// 策略说明:

// 基于4均线系统进行判断交易

//

// 系统要素:

// (5和20周期均线),(3和10周期均线)构成的两组不同周期的均线组合

//

// 入场条件:

// 当2组均线均成多头排列时且当前价高于上根BAR最高价入场

//

// 出场条件:

// 1 小周期多头均线组合成空头排列

// 2 两组空头均线分别空头排列且低于上根BAR最低价出场

//

//------------------------------------------------------------------//

Params

Numeric LEFast(5); //多头入场短均线周期参数

Numeric LESlow(20); //多头入场长均线周期参数

Numeric LXFast(3); //多头出场短均线周期参数

Numeric LXSlow(10); //多头出场长均线周期参数

Numeric SEFast(5); //空头入场短均线周期参数

Numeric SESlow(20); //空头入场长均线周期参数

Numeric SXFast(3); //空头出场短均线周期参数

Numeric SXSlow(10); //空头出场长均线周期参数

Vars

NumericSeries MALEFast;//多头入场短均线

NumericSeries MALESlow;//多头入场长均线

NumericSeries MALXFast;//多头出场短均线

NumericSeries MALXSlow;//多头出场长均线

NumericSeries MASEFast;//空头入场短均线

NumericSeries MASESlow;//空头入场长均线

NumericSeries MASXFast;//空头出场短均线

NumericSeries MASXSlow;//空头出场长均线

Begin

// 集合竞价和小节休息过滤

// CallAuctionFilter是返回值为bool型的用户函数

//
处理1分钟、3分钟、5分钟、15分钟、30分钟、1小时、日线、周线、月线交易的集合竞价与小节过滤，避免发出废单

If(!CallAuctionFilter()) Return;

MALEFast=Average(Close,LEFast);//多头入场短均线

MALESlow=Average(Close,LESlow);//多头入场长均线

MALXFast=Average(Close,LXFast);//多头出场短均线

MALXSlow=Average(Close,LXSlow);//多头出场长均线

MASEFast=Average(Close,SEFast);//空头入场短均线

MASESlow=Average(Close,SESlow);//空头入场长均线

MASXFast=Average(Close,SXFast);//空头出场短均线

MASXSlow=Average(Close,SXSlow);//空头出场长均线

// 多头入场的条件设置

If(Marketposition \<\> 1 and Currentbar \>= 100) //
当前位置没有持多仓，并且当前Bar索引值大于等于100

{

//
两组均线均成多头排列时且当前价高于上根BAR最高价，并且当前Bar有一定成交量时，多头入场

// 多头排列：短期移动平均线在上，长期移动平均线在下，并同时上移

If(MALEFast[1] \> MALESlow[1] and MALXFast[1] \> MALXSlow[1] and High \>=
High[1] And Vol \> 0)

{

//
对当前合约发出买入开仓的指令，如果图标讯号显示当前持有空仓，则会先平掉空仓，再开多仓；

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Max(Open,High[1])表示选择(当前Bar的开盘价，前一Bar的最高价)的较大值进行开多仓操作

Buy(0,Max(Open,High[1]));

}

}

// 多头出场的条件设置

If(marketposition == 1 and BarsSinceEntry \> 0 And Vol \> 0) //
当前位置为持多仓，当前持仓的第一个建仓位置到当前位置的Bar计数不为0(即当前Bar开多仓时下一Bar之后才可平多仓)，当前Bar有一定成交量

{

// 小周期多头均线组合成空头排列出场

// 空头排列：短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降

If(MALXFast[1] \< MALXSlow[1] )

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

// 采用当前Bar的开盘价进行平多仓操作

Sell(0,Open);

}

// 两组均线分别空头排列且低于上根BAR最低价出场

Else If( MASEFast[1] \< MASESlow[1] and MASXFast[1] \< MASXSlow[1] and Low \<=
Low[1])

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Min(Open,Low[1])表示选择(当前Bar的开盘价，前一Bar的最低价)的较小值进行开多仓操作

Sell(0,Min(Open,Low[1]));

}

}

End

//------------------------------------------------------------------------

// 编译版本 GS2015.12.25

// 用户版本 2019/12/26 16:15:09

// 版权所有 user_wap

// 更改声明 TradeBlazer Software保留对TradeBlazer平台

// 每一版本的TradeBlazer公式修改和重写的权利

//------------------------------------------------------------------------

\`\`\`

\#\# 四均线交易系统 空

\`\`\`powershell

//------------------------------------------------------------------------

// 简称: A_FourSetofMACrossoverSys_S

// 名称: 四均线交易系统

// 类别: 公式应用

// 类型: 用户应用

// 输出:

// 策略说明:

// 基于4均线系统进行判断交易

//

// 系统要素:

// (5和20周期均线),(3和10周期均线)构成的两组不同周期的均线组合

//

// 入场条件:

// 当2组均线均成空头排列时且当前价低于上根BAR最低价入场

//

// 出场条件:

// 1 小周期空头均线组合成多头排列

// 2 两组多头均线分别多头排列且低于上根BAR最高价出场

//

//----------------------------------------------------------------------//

Params

Numeric LEFast(5); //多头入场短均线周期参数

Numeric LESlow(20); //多头入场长均线周期参数

Numeric LXFast(3); //多头出场短均线周期参数

Numeric LXSlow(10); //多头出场长均线周期参数

Numeric SEFast(5); //空头入场短均线周期参数

Numeric SESlow(20); //空头入场长均线周期参数

Numeric SXFast(3); //空头出场短均线周期参数

Numeric SXSlow(10); //空头出场长均线周期参数

Vars

NumericSeries MALEFast;//多头入场短均线

NumericSeries MALESlow;//多头入场长均线

NumericSeries MALXFast;//多头出场短均线

NumericSeries MALXSlow;//多头出场长均线

NumericSeries MASEFast;//空头入场短均线

NumericSeries MASESlow;//空头入场长均线

NumericSeries MASXFast;//空头出场短均线

NumericSeries MASXSlow;//空头出场长均线

Begin

// 集合竞价和小节休息过滤

// CallAuctionFilter是返回值为bool型的用户函数

//
处理1分钟、3分钟、5分钟、15分钟、30分钟、1小时、日线、周线、月线交易的集合竞价与小节过滤，避免发出废单

If(!CallAuctionFilter()) Return;

MALEFast=Average(Close,LEFast);//多头入场短均线

MALESlow=Average(Close,LESlow);//多头入场长均线

MALXFast=Average(Close,LXFast);//多头出场短均线

MALXSlow=Average(Close,LXSlow);//多头出场长均线

MASEFast=Average(Close,SEFast);//空头入场短均线

MASESlow=Average(Close,SESlow);//空头入场长均线

MASXFast=Average(Close,SXFast);//空头出场短均线

MASXSlow=Average(Close,SXSlow);//空头出场长均线

// 空头入场的条件设置

If(Marketposition \<\> -1 and Currentbar \>= 100) //
当前位置没有持空仓，并且当前Bar索引值大于等于100

{

//
两组空头均线均成空头排列且当前价低于上根Bar最低价，并且当前Bar有一定成交量时，空头入场

// 空头排列：短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降

If(MASEFast[1] \< MASESlow[1] and MASXFast[1] \< MASXSlow[1] and Low \<= Low[1]
And Vol \> 0)

{

// 对当前合约发出卖出开仓的指令，如果图表讯号显示当前持有多仓，则会先平掉多仓，
再开空仓

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Min(Open,Low[1])表示选择(当前Bar的开盘价，前一Bar的最低价)的较小值进行开空仓操作

SellShort(0,Min(Open,Low[1]));

}

}

// 空头出场的条件设置

If(MarketPosition == -1 and BarsSinceEntry \> 0 And Vol \> 0) //
当前位置为持空仓，当前持仓的第一个建仓位置到当前位置的Bar计数不为0(即当前Bar开空仓时下一Bar之后才可平空仓)，当前Bar有一定成交量

{

// 小周期空头均线组合成多头排列出场

// 多头排列：短期移动平均线在上，长期移动平均线在下，并同时上移

If(MASXFast[1] \> MASXSlow[1])

{

// 对当前合约发出平空仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

// 采用当前Bar的开盘价进行平空仓操作

BuyToCover(0,Open);

}

// 两组均线分别多头排列且高于上根BAR最高价出场

Else if( MALEFast[1] \> MALESlow[1] and MALXFast[1] \> MALXSlow[1] and High \>=
High[1] )

{

// 对当前合约发出平空仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Max(Open,High[1])表示选择(当前Bar的开盘价，前一Bar的最高价)的较大值进行平空仓操作

BuyToCover(0,Max(Open,High[1]));

}

}

End

//------------------------------------------------------------------------

// 编译版本 GS2015.12.25

// 用户版本 2019/12/26 16:19:52

// 版权所有 user_wap

// 更改声明 TradeBlazer Software保留对TradeBlazer平台

// 每一版本的TradeBlazer公式修改和重写的权利

//------------------------------------------------------------------------

\`\`\`

\#\# 新代码

\#\#\# 四均线交易系统(多头)_动态仓

\`\`\`powershell

//------------------------------------------------------------------------

// 简称: A_NewFourSetofMACrossoverSys_L

// 名称: 四均线交易系统(多头)_动态仓

// 类别: 公式应用

// 类型: 用户应用

// 输出:

//------------------------------------------------------------------------

Params

Numeric LEFast(5); //多头入场短均线周期参数

Numeric LESlow(20); //多头入场长均线周期参数

Numeric LXFast(3); //多头出场短均线周期参数

Numeric LXSlow(10); //多头出场长均线周期参数

Numeric SEFast(5); //空头入场短均线周期参数

Numeric SESlow(20); //空头入场长均线周期参数

Numeric SXFast(3); //空头出场短均线周期参数

Numeric SXSlow(10); //空头出场长均线周期参数

Vars

NumericSeries MALEFast;//多头入场短均线

NumericSeries MALESlow;//多头入场长均线

NumericSeries MALXFast;//多头出场短均线

NumericSeries MALXSlow;//多头出场长均线

NumericSeries MASEFast;//空头入场短均线

NumericSeries MASESlow;//空头入场长均线

NumericSeries MASXFast;//空头出场短均线

NumericSeries MASXSlow;//空头出场长均线

Numeric MinPoint; // 一个最小变动单位，也就是一跳

NumericSeries firstPrice; // 第一次开仓价格

NumericSeries LastPrice; // 最后一次开仓价格

Numeric AddSet(30); // 加仓设置固定系数30

Numeric SubSet(30); // 减仓设置固定系数30

Begin

// 集合竞价和小节休息过滤

// CallAuctionFilter是返回值为bool型的用户函数

//
处理1分钟、3分钟、5分钟、15分钟、30分钟、1小时、日线、周线、月线交易的集合竞价与小节过滤，避免发出废单

If(!CallAuctionFilter()) Return;

MALEFast=Average(Close,LEFast);//多头入场短均线

MALESlow=Average(Close,LESlow);//多头入场长均线

MALXFast=Average(Close,LXFast);//多头出场短均线

MALXSlow=Average(Close,LXSlow);//多头出场长均线

MASEFast=Average(Close,SEFast);//空头入场短均线

MASESlow=Average(Close,SESlow);//空头入场长均线

MASXFast=Average(Close,SXFast);//空头出场短均线

MASXSlow=Average(Close,SXSlow);//空头出场长均线

MinPoint = MinMove\*PriceScale; //最小变动价位

If(MarketPosition==0) // 空仓时

{

If(Currentbar \>= 100) // 当前Bar索引值大于等于100

{

//
两组均线均成多头排列时且当前价高于上根BAR最高价，并且当前Bar有一定成交量时，多头入场

// 多头排列：短期移动平均线在上，长期移动平均线在下，并同时上移

If(MALEFast[1] \> MALESlow[1] and MALXFast[1] \> MALXSlow[1] and High \>=
High[1] And Vol \> 0)

{

firstPrice = Open;//第一次开仓价格

LastPrice = firstPrice;//最后一次开仓价先赋值为开仓价

Buy(0,firstPrice);//以第一次开仓价买入

}

}

}

else If(MarketPosition==1) // 多仓时，加减仓的具体操作

{

If(BarsSinceEntry \> 0 And Vol \> 0) //
当前持仓的第一个建仓位置到当前位置的Bar计数不为0(即当前Bar开多仓时下一Bar之后才可平多仓)，当前Bar有一定成交量

{

// 小周期多头均线组合成空头排列出场

// 空头排列：短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降

If(MALXFast[1] \< MALXSlow[1] )

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

// 采用当前Bar的开盘价进行平多仓操作

Sell(0,Open);

}

// 两组均线分别空头排列且低于上根BAR最低价出场

Else If( MASEFast[1] \< MASESlow[1] and MASXFast[1] \< MASXSlow[1] and Low \<=
Low[1])

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Min(Open,Low[1])表示选择(当前Bar的开盘价，前一Bar的最低价)的较小值进行开多仓操作

Sell(0,Min(Open,Low[1]));

}

}

While(CurrentEntries \< 4 && High \>= LastPrice + AddSet\*MinPoint) //
加仓操作，当持仓的建仓次数小于4次，并且最高价 大于等于 （最后一次开仓 +
固定系数30乘以最小跳动价格）

{

LastPrice = LastPrice + AddSet\*MinPoint;//
循环累加，符合条件的累次加仓直到不符合条件

if(Open \> LastPrice) // 开盘价大于最后一次开仓价

LastPrice = Open;// 把开盘价赋予给最后一次开仓价

Buy(1,LastPrice);// 以最后一次开仓价，加仓一手

}

While(CurrentEntries \> 0 && Low \<= firstPrice - SubSet\*MinPoint) //
减仓操作，当持仓的建仓次数大于0，并且最低价 小于 （第一次开仓价 -
固定系数30乘以最小跳动价格）

{

firstPrice = firstPrice -
SubSet\*MinPoint;//循环累减，符合条件的依次减，直到没有持仓

if(Open \< firstPrice) // 开盘价小于第一次开仓价

firstPrice = Open;// 把开盘价赋值给第一次开仓价

Sell(1,firstPrice);// 以第一次开仓价，平掉一手

}

}

End

//------------------------------------------------------------------------

// 编译版本 GS2015.12.25

// 用户版本 2019/12/27 20:21:21

// 版权所有 user_wap

// 更改声明 TradeBlazer Software保留对TradeBlazer平台

// 每一版本的TradeBlazer公式修改和重写的权利

//------------------------------------------------------------------------

\`\`\`

\#\#\# 四均线交易系统(多头)_动态跟踪

\`\`\`powershell

//------------------------------------------------------------------------

// 简称: A_New_FourSetofMACrossoverSys_L

// 名称: 四均线交易系统(多头)_动态跟踪

// 类别: 公式应用

// 类型: 用户应用

// 输出:

//------------------------------------------------------------------------

Params

Numeric LEFast(5); //多头入场短均线周期参数

Numeric LESlow(20); //多头入场长均线周期参数

Numeric LXFast(3); //多头出场短均线周期参数

Numeric LXSlow(10); //多头出场长均线周期参数

Numeric SEFast(5); //空头入场短均线周期参数

Numeric SESlow(20); //空头入场长均线周期参数

Numeric SXFast(3); //空头出场短均线周期参数

Numeric SXSlow(10); //空头出场长均线周期参数

Vars

NumericSeries MALEFast;//多头入场短均线

NumericSeries MALESlow;//多头入场长均线

NumericSeries MALXFast;//多头出场短均线

NumericSeries MALXSlow;//多头出场长均线

NumericSeries MASEFast;//空头入场短均线

NumericSeries MASESlow;//空头入场长均线

NumericSeries MASXFast;//空头出场短均线

NumericSeries MASXSlow;//空头出场长均线

Numeric MinPoint; // 一个最小变动单位，也就是一跳

NumericSeries firstPrice; // 第一次开仓价格

NumericSeries LastPrice; // 最后一次开仓价格

Numeric AddSet(30); // 加仓设置固定系数30

Numeric SubSet(30); // 减仓设置固定系数30

Numeric MyEntryPrice; // 开仓价格，本例是开仓均价，可设置为某次入场价

Numeric TrailingStart1(50); // 跟踪止损启动设置1，固定系数为50

Numeric TrailingStart2(80); // 跟踪止损启动设置2，固定系数为80

Numeric TrailingStop1(30); // 跟踪止损设置1，固定系数为30

Numeric TrailingStop2(20); // 跟踪止损设置2，固定系数为20

Numeric StopLossSet(50); // 止损设置，固定系数为50

Numeric MyExitPrice; // 平仓价格

NumericSeries HighestAfterEntry; // 开仓后出现的最高价

NumericSeries LowestAfterEntry; // 开仓后出现的最低价

Begin

// 集合竞价和小节休息过滤

// CallAuctionFilter是返回值为bool型的用户函数

//
处理1分钟、3分钟、5分钟、15分钟、30分钟、1小时、日线、周线、月线交易的集合竞价与小节过滤，避免发出废单

If(!CallAuctionFilter()) Return;

MALEFast=Average(Close,LEFast);//多头入场短均线

MALESlow=Average(Close,LESlow);//多头入场长均线

MALXFast=Average(Close,LXFast);//多头出场短均线

MALXSlow=Average(Close,LXSlow);//多头出场长均线

MASEFast=Average(Close,SEFast);//空头入场短均线

MASESlow=Average(Close,SESlow);//空头入场长均线

MASXFast=Average(Close,SXFast);//空头出场短均线

MASXSlow=Average(Close,SXSlow);//空头出场长均线

MinPoint = MinMove\*PriceScale; //最小变动价位

If(MarketPosition==0) // 空仓时

{

If(Currentbar \>= 100) // 当前Bar索引值大于等于100

{

//
两组均线均成多头排列时且当前价高于上根BAR最高价，并且当前Bar有一定成交量时，多头入场

// 多头排列：短期移动平均线在上，长期移动平均线在下，并同时上移

If(MALEFast[1] \> MALESlow[1] and MALXFast[1] \> MALXSlow[1] and High \>=
High[1] And Vol \> 0)

{

firstPrice = Open;//第一次开仓的价格，就是以开盘价来开了。//

LastPrice = firstPrice;//刚开始的最后一次开仓价先赋值为开仓价。//

Buy(0,firstPrice);//以第一次开仓价买2手，方便加减操作的，当然实盘多少都是随个人的习惯。//

}

}

}

else If(MarketPosition==1) // 多仓时，加减仓的具体操作

{

If(BarsSinceEntry \> 0 And Vol \> 0) //
当前持仓的第一个建仓位置到当前位置的Bar计数不为0(即当前Bar开多仓时下一Bar之后才可平多仓)，当前Bar有一定成交量

{

// 小周期多头均线组合成空头排列出场

// 空头排列：短期移动平均值在下方，长期移动平均线在上方，并同时呈弧形下降

If(MALXFast[1] \< MALXSlow[1] )

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

// 采用当前Bar的开盘价进行平多仓操作

Sell(0,Open);

}

// 两组均线分别空头排列且低于上根BAR最低价出场

Else If( MASEFast[1] \< MASESlow[1] and MASXFast[1] \< MASXSlow[1] and Low \<=
Low[1])

{

// 对当前合约发出平多仓的指令

// 默认值为0表示使用系统设置参数，通过全局交易设置，修改默认交易数量

//
Min(Open,Low[1])表示选择(当前Bar的开盘价，前一Bar的最低价)的较小值进行开多仓操作

Sell(0,Min(Open,Low[1]));

}

}

While(CurrentEntries \< 4 && High \>= LastPrice + AddSet\*MinPoint) //
加仓操作，当持仓的建仓次数小于4次，并且最高价 大于等于 （最后一次开仓 +
固定系数30乘以最小跳动价格）

{

LastPrice = LastPrice + AddSet\*MinPoint;//
循环累加，符合条件的累次加仓直到不符合条件

if(Open \> LastPrice) // 开盘价大于最后一次开仓价

LastPrice = Open;// 把开盘价赋予给最后一次开仓价

Buy(1,LastPrice);// 以最后一次开仓价，加仓一手

}

While(CurrentEntries \> 0 && Low \<= firstPrice - SubSet\*MinPoint) //
减仓操作，当持仓的建仓次数大于0，并且最低价 小于 （第一次开仓价 -
固定系数30乘以最小跳动价格）

{

firstPrice = firstPrice -
SubSet\*MinPoint;//循环累减，符合条件的依次减，直到没有持仓

if(Open \< firstPrice) // 开盘价小于第一次开仓价

firstPrice = Open;// 把开盘价赋值给第一次开仓价

Sell(1,firstPrice);// 以第一次开仓价，平掉一手

}

}

If(BarsSinceentry == 0) //
获得当前持仓的第一个建仓位置到当前位置的Bar计数，条件满足：开仓Bar

{

HighestAfterEntry = Close;// 开仓后的最高价为收盘价。//

LowestAfterEntry = Close; // 开仓后的最低价为收盘价。//

If(MarketPosition \<\> 0)// 有持仓时执行以下代码

{

// 开仓Bar，将开仓价和当时的收盘价的较大值保留到HighestAfterEntry

HighestAfterEntry = Max(HighestAfterEntry,AvgEntryPrice);

// 开仓Bar，将开仓价和当时的收盘价的较小值保留到LowestAfterEntry

LowestAfterEntry = Min(LowestAfterEntry,AvgEntryPrice);

}

}

else //非开仓Bar时进行以下运算

{

// 记录下当前Bar的最高点，用于下一个Bar的跟踪止损判断

HighestAfterEntry = Max(HighestAfterEntry,High);

// 记录下当前Bar的最低点，用于下一个Bar的跟踪止损判断

LowestAfterEntry = Min(LowestAfterEntry,Low);

}

Commentary("HighestAfterEntry="+Text(HighestAfterEntry));//在超级图表当前Bar添加一行注释信息，显示最高价HighestAfterEntry

Commentary("LowestAfterEntry="+Text(LowestAfterEntry));
//在超级图表当前Bar添加一行注释信息，显示最低价LowestAfterEntry

MinPoint = MinMove\*PriceScale;// 最小跳动价公式

MyEntryPrice = AvgEntryPrice; // 把开仓均价赋值给MyEntryPrice

If(MarketPosition==1 And BarsSinceEntry\>=1) // 有多仓的情况

{

// 第二级跟踪止损的条件表达式

If(HighestAfterEntry[1] \>= MyEntryPrice + TrailingStart2\*MinPoint) //
假如最高价 大于等于 （开仓均价 + 跟踪止损启动设置2 \* 最小跳动价）

{

If(Low \<= HighestAfterEntry[1] - TrailingStop2\*MinPoint)// 假如当前Bar最低价
小于等于 (最高价 - 跟踪止损设置2 \* 最小跳动价）

{

MyExitPrice = HighestAfterEntry[1] - TrailingStop2\*MinPoint;// 平仓价 等于
(最高价 - 跟踪止损设置2 \* 最小跳动价）

If(Open \< MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

Sell(0,MyExitPrice); // 以计算得的平仓价，平仓

}

}

else if(HighestAfterEntry[1] \>= MyEntryPrice + TrailingStart1\*MinPoint)//
第一级跟踪止损的条件表达式

{

If(Low \<= HighestAfterEntry[1] - TrailingStop1\*MinPoint)// 假如当前Bar最低价
小于等于 (最高价 - 跟踪止损设置1 \* 最小跳动价）

{

MyExitPrice = HighestAfterEntry[1] - TrailingStop1\*MinPoint;// 平仓价 等于
(最高价 - 跟踪止损设置1 \* 最小跳动价）

If(Open \< MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

Sell(0,MyExitPrice);// 以计算得的平仓价，平仓

}

}

else if(Low \<= MyEntryPrice - StopLossSet\*MinPoint)
//初始的固定止损处理，即为当前Bar最低价 小于等于 (开仓均价 - 固定止损系数 \*
最小跳动价)

{

MyExitPrice = MyEntryPrice - StopLossSet\*MinPoint;// 平仓价 等于 (开仓价 -
止损系数 \* 最小跳动价）

If(Open \< MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

Sell(0,MyExitPrice);// 以计算得的平仓价，平仓

}

}else if(MarketPosition==-1 And BarsSinceEntry\>=1) //
有空仓的情况。代码都差不多，但就是意思反过来了。//

{

// 第二级跟踪止损的条件表达式

If(LowestAfterEntry[1] \<= MyEntryPrice - TrailingStart2\*MinPoint) //
假如最低价 小于等于 （开仓均价 - 跟踪止损启动设置2 \* 最小跳动价）

{

If(High \>= LowestAfterEntry[1] + TrailingStop2\*MinPoint)// 假如当前Bar最高价
大于等于 (最低价 + 跟踪止损设置2 \* 最小跳动价）

{

MyExitPrice = LowestAfterEntry[1] + TrailingStop2\*MinPoint;// 平仓价 等于
(最低价 + 跟踪止损设置2 \* 最小跳动价）

If(Open \> MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

BuyToCover(0,MyExitPrice);// 以计算得的平仓价，平仓

}

}

else if(LowestAfterEntry[1] \<= MyEntryPrice - TrailingStart1\*MinPoint)//
第一级跟踪止损的条件表达式

{

If(High \>= LowestAfterEntry[1] + TrailingStop1\*MinPoint)// 假如当前Bar最高价
大于等于 (最低价 + 跟踪止损设置1 \* 最小跳动价）

{

MyExitPrice = LowestAfterEntry[1] + TrailingStop1\*MinPoint;// 平仓价 等于
(最低价 + 跟踪止损设置1 \* 最小跳动价）

If(Open \> MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

BuyToCover(0,MyExitPrice);// 以计算得的平仓价，平仓

}

}

else If(High \>= MyEntryPrice +
StopLossSet\*MinPoint)//初始的固定止损处理，即为当前Bar最高价 大于等于 (开仓均价
+ 固定止损系数 \* 最小跳动价)

{

MyExitPrice = MyEntryPrice + StopLossSet\*MinPoint;// 平仓价 等于 (开仓价 +
止损系数 \* 最小跳动价）

If(Open \> MyExitPrice) MyExitPrice = Open; //
如果该Bar开盘价即跳空触发，则用开盘价代替

BuyToCover(0,MyExitPrice);// 以计算得的平仓价，平仓

}

}

End

//------------------------------------------------------------------------

// 编译版本 GS2015.12.25

// 用户版本 2019/12/27 21:21:21

// 版权所有 user_wap

// 更改声明 TradeBlazer Software保留对TradeBlazer平台

// 每一版本的TradeBlazer公式修改和重写的权利

//------------------------------------------------------------------------

\`\`\`
