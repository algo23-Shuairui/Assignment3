
Assignment3
==========

**参考研报：**<br>
20120814-光大证券-技术指标系列(七)：CMO动量波动指标的运用

**1. 回测数据来源**<br>
万得 Wind

**2. 回测样本**<br>
沪深300指数数据（2005-01-01至2023-03-17）

**3. 策略**<br>
AROON 指标分为两个具体指标，分别为 AROONUP 及 AROONDOWN。其<br>
具体的计算方式为︰ <br>
第一步：AROON_UP =[(计算期天数-最高价后的天数)/计算期天数]*100 <br>
第二步：AROON_DN =[(计算期天数-最低价后的天数)/计算期天数]*100 <br>
第三步：AROON = AROON_UP-AROON_DN <br>
常用参数为 20<br>

当 AROON_UP 指标向下跌破 50 时，表示向上的趋势正在失去动力；当<br>
AROON_DN 指标向下跌破 50 时，表示向下的趋势正在失去动力；如果两个<br>
指标都在低位，表示股价没有明确的趋势；如果指标在 70 以上，表示趋势十<br>
分强烈；如果在 30 以下，表明相反的趋势正在酝酿。 <br>
若计算期为 20，那么 AROON_UP=50，意味着最高价出现在第 10 天，<br>
AROON_DN=50，意味着最低价出现在第 10 天，AROON_UP-AROON_DN>0,<br>
意味着最高价比最低价较晚出现，离现在近。AROON_UP-AROON_DN>x，<br>
意味着最高价离现在比最低价离现在多 20x/100 天,即若 x=40，20x/100=8 天，<br>
表明现在还处于强势中，反之亦然。<br>

**4. 策略信号**<br>
当 AROON_UP 上穿 70，并且 AROON>0，买入，信号为 1 <br>
当 AROON_DN 上穿 70，并且 AROON<0，卖空，信号为-1 <br>
当 AROON_UP 下穿 50，并且 AROON<0，卖空，信号为-1<br> 
当 AROON_DN 下穿 50，并且 AROON>0，买入，信号为 1 <br>
参数为 20<br>

优化：增加了“二次确认”的过程。这样得到的信号更可靠。 <br>
下面以 x=50 为例，策略为：<br> 
AROON 上穿 50，买入，信号为 1 <br>
AROON 下穿-50，卖空，信号为-1<br>

**4. 计算指标并进行回测**<br>

**计算以下指标变化情况：**<br>
持仓收益<br>
持仓胜负<br>
累计持仓收益<br>
回撤<br>
超额收益

**并输出结果：**<br>
累计收益 <br>
多仓次数 <br>
多仓胜率<br>
多仓平均持有期<br>
空仓次数<br>
空仓胜率<br>
空仓平均持有期<br>
日胜率<br>
最大回撤<br>
年化收益/最大回撤<br>
年化收益<br>
年化标准差<br>
年化夏普 

**5. 多种情况的结果**(红色为沪深三百，蓝色为CMO）

A:复现研报原策略（2005-09-01至2012-09-01） N=12
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/A1.png)
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/A2.png)
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/A3.png)

B:策略优化（2012-09-01至今） N=13为例
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/B1.png)
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/B2.png)
![image](https://github.com/algo23-Shuairui/Assignment3/blob/main/IMG/B3.png)


