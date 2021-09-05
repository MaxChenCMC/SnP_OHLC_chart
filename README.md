# Application:

有別於一般報價網站只能依技術指標(i.e. MA、KD、MACD、RSI、BBand...)做為選股依據

我從K棒***開高低收量***的排列特徵與出現頻率

設計出有別於傳統的選股條件

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
</pre>

當以上***8個特徵符合6個以上***時就選為做多候選股
* * *
7/26收盤後所篩選出的股票之近期走勢 (from FINVIZ)
![amd,an,ktos,sam](https://i.imgur.com/YyHg2jf.png)
* * *
接著用隨機森林演算法

用過去一年多的資料樣本

前80%資料為訓練集

後20%資料為測試集

推估當特徵出現的***隔天***

該股票***漲幅超過S&P500指數***的機率是否超過50%

算出 **AN** (AutoNation, Inc.)在訓練集裡有66%的準確率，測試集仍有55.9%的準確率

# Tools:
yfinance, pandas, numpy, sklearn
