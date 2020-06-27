# alpha-factor-show
代表性alpha因子测试结果展示
* 回测划分：样本内为2010-2016，样本外为2017-2020；
* 每张图展示因子的四个指标：tbdf10, top10, top20, IC
  - tbdf10 = top10 return - bottom10 return
  - top10 = top10 return - mean return of all stocks
  - top20 = top20 return - mean return of all stocks
  - IC = corr($f_t, r_{t+1}$)
* 三种收益率：OCDay2, OCDay5, OCDay10, 分别表示未来2天、5天、10天收益率的平均值；

<img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/%E5%9F%BA%E4%BA%8E%E6%97%A5%E7%BA%BF%E6%95%B0%E6%8D%AE%E7%9A%84%E5%9B%A0%E5%AD%90.jpg" width="400"/><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/%E5%9F%BA%E4%BA%8E%E5%88%86%E9%92%9F%E6%95%B0%E6%8D%AE%E7%9A%84%E5%9B%A0%E5%AD%90.jpg" width="400"/>
<p align="center">(左)基于日线数据的因子，(右)基于分钟数据的因子</p>

* 基于公司因子库和xgboost对因子进行组合；
<p align="left"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/xgb-excess-nav.png"/></p>
