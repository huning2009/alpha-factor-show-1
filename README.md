# alpha-factor-show
代表性alpha因子测试结果展示
* 数据：日频价量、资金流、订单数据，分钟价量数据；
* 回测划分：样本内为2010-2016，样本外为2017-2020；
* 仅风格中性化，未考虑任何成本；
* 每张图展示因子的四个指标：tbdf10, top10, top20, IC
  - tbdf10 = top10 return - bottom10 return
  - top10 = top10 return - mean return of all stocks
  - top20 = top20 return - mean return of all stocks
  - IC = corr($f_t, r_{t+1}$)
* 三种收益率：OCDay2, OCDay5, OCDay10, 分别表示未来2天、5天、10天收益率的平均值；

<p align="center">
<img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/%E5%9F%BA%E4%BA%8E%E6%97%A5%E7%BA%BF%E6%95%B0%E6%8D%AE%E7%9A%84%E5%9B%A0%E5%AD%90.jpg" width="350"/><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/%E5%9F%BA%E4%BA%8E%E5%88%86%E9%92%9F%E6%95%B0%E6%8D%AE%E7%9A%84%E5%9B%A0%E5%AD%90.jpg" width="350"/></p>

<p align="center">(左)基于日线数据的因子，(右)基于分钟数据的因子</p>

* 基于日线数据的因子

| 年平均值| annret_tbdf10 | sharpe_tbdf10 | maxdd_tbdf10 | annret_top10 | sharpe_top10 | maxdd_top10 | annret_top20 | sharpe_top20 | maxdd_top20 | mean_IC | tstat_IC |
| -------: | ------------: | ------------: | -----------: | -----------: | -----------: | ----------: | -----------: | -----------: | ----------: | ------: | -------: |
|   OCDay2 |          0.33 |          8.57 |        -0.01 |         0.19 |         5.38 |       -0.02 |         0.17 |         7.09 |       -0.01 |    0.03 |    10.50 |
|   OCDay5 |          0.27 |         11.42 |        -0.01 |         0.15 |         7.00 |       -0.02 |         0.14 |         9.32 |       -0.01 |    0.03 |    13.85 |
|  OCDay10 |          0.20 |         12.11 |        -0.01 |         0.11 |         7.71 |       -0.02 |         0.10 |        10.43 |       -0.01 |    0.04 |    15.56 |

* 基于分钟数据的因子

| 年平均值 | annret_tbdf10 | sharpe_tbdf10 | maxdd_tbdf10 | annret_top10 | sharpe_top10 | maxdd_top10 | annret_top20 | sharpe_top20 | maxdd_top20 | mean_IC | tstat_IC |
| -------: | -------------: | -------------: | ------------: | ------------: | ------------: | -----------: | ------------: | ------------: | -----------: | -------: | --------: |
|OCDay2  | 0.22          | 5.63          | -0.02        | 0.11         | 4.90         | -0.02       | 0.09         | 5.37         | -0.01       | 0.02    | 6.96     |
|OCDay5  | 0.19          | 7.49          | -0.02        | 0.10         | 6.82         | -0.01       | 0.09         | 8.20         | -0.01       | 0.02    | 10.09    |
|OCDay10 | 0.14          | 8.17          | -0.02        | 0.08         | 7.76         | -0.01       | 0.07         | 9.51         | -0.01       | 0.03    | 11.60    |

* 简单打分法对公司因子库中的因子进行组合
<p align="left"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/score-excess-cumsum.png"/></p>

* 利用xgboost对公司因子库中的因子进行组合
<p align="left"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/xgb-excess-cumsum.png"/></p>
