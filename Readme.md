# QUIZ 2022 Jan

以下编程题目解答中: \
(1). 使用docker构建集成环境为加分项 \
(2). 正确使用commenting为加分项 \
(3). 正确使用docstring为加分项 \
(4). 良好且一致的代码风格为加分项

## 1. "轮流"拔河比赛

两位拔河选手参加一个轮流拔河对决，比赛规则如下: \
1. 比赛开始时，标记置于绳子的正中间，标记为0点 
2. 两位选手依次向自己方向拉动绳子，为方便说明，规定左边选手拉动绳子的距离a标记为-a, 右边选手拉动的距离b标记为+b 
3. a, b 满足以下条件:<img src="https://render.githubusercontent.com/render/math?math=a,b \sim N(0,1)"> 
4. 首先拔过<img src="https://render.githubusercontent.com/render/math?math=\frac{1}{2}">则右边选手获胜; 反之，首先拔过<img src="https://render.githubusercontent.com/render/math?math=-\frac{1}{2}">左边选手获胜

比赛组织者发现: 这种规则下先拔的选手会获得一定的优势，为保证公平，必须给后发选手一定的补偿以保证比赛公平。请问中间标记需要向后发选手移动多少距离才能保证比赛的绝对公平? 

答题要求: 可以通过编程或者数学方法推导结果，结果保留六位有效数字


## 2. 数据清洗与挖掘

附件中包含两个文件:
1. CF205_20211208.csv 为棉花期货在2021年12月8日的一档行情
2. CF205C19200_20211208.csv 为棉花期权strike price=19200 Call Option在2021年12月8日的一档行情

请完成以下任务:

1. 按时间戳对齐期权与期货的数据，输出为 step_one.csv
2. 基于step_one.csv, 按时间戳计算每个tick的Bid_ImpliedVol, Ask_ImpliedVol和Mid_ImpliedVol, 分别对应期货的BidPrice1, AskPrice1和MidPrice, 输出为step_two.csv (无风险利率记为1.5%)
3. 根据step_two.csv 计算200sec三种vol的移动均线和5sec三种vol移动均线，输出为 step_three.csv
4. 计算期货每十分钟的realized vol, 输出为 step_four.csv

答题要求: 计算过程请使用Python JupyterNotebook(.ipynb)文件保存

## 3. 简单策略

我们试图验证如下策略的有效性:每10分钟期货的量价指标可以预测realized vol变化

请基于#2提供的数据进行验证

1. 请挑选不少于五个Feature，并计算出来，输出为 forecast_one.csv
2. 请基于你挑选出来的feature对 step_four.csv的数据进行回归分析

答题要求: 计算过程请使用Python JupyterNotebook(.ipynb)文件保存，若涉及使用其它语言/框架(如Tensoflow C++)，请另行打包，并附Readme.txt说明编译/运行环境和方法
