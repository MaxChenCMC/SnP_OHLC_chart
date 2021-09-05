# Application:

有別於現成套裝技術指標(i.e. MA、KD、MACD、RSI、BBand...)做選股依據

我從自定義的價量條件與出現頻率

設計出符合自己交易屬性的動能選股策略

<pre>
舊策略：
1. 最近一個交易日跳空開高2%
2. 過去10個交易日裡有2天跳空開高2%
3. 最近一個交易實體K棒達3%
4. 過去10個交易日裡有2天實體K棒達3%
5. 過去連續3個交易日，每日高點都比前一天高、且每日低點都比前一天高
6. 過去10個交易日裡有6天今高過昨高、且今低比昨低還要高
7. 下一個交易日只要漲超過3%就會創10日新高
8. 最近一個交易日成交量超過10量均量2成
當8個條件符合6個以上時就於隔天開盤做多
</pre>

<pre>
新策略：
1. 最新收盤價距離近月新高不到3%
2. 當天紅K棒是過去10日平均實體K棒的2.5倍
3. 當天成交量是過去5日的1.3倍
4. 過去5天出現過5ma向上穿越10ma
當4個條件符合3個以上時就於隔天開盤做多
</pre>

9/3 收盤後所篩選出的股票之近期走勢 (screenshot from FINVIZ)
<br>
![image](https://raw.githubusercontent.com/MaxChenCMC/US_Stock_Momentum/master/img.png)


接著用`隨機森林`演算法

回測過去30個月

前80%資料為訓練集

後20%資料為測試集

推估當特徵出現時
與隔天漲贏Nasdaq的關係

算出`FTV (Fortive Corporation)`

訓練集準度|測試集準度|測試集ROC_AUC
---|---|---
0.553571|0.484127|0.479587

# Tools:
requests, yfinance, pandas, numpy, sklearn, matplotlib
